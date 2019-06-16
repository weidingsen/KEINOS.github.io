---
title: GoogleApps’ CardDAV Principal URL for iPhone Config Util
author: KEINOS
type: post
date: 2013-02-17T16:00:00+00:00
url: /20130218_889
page_type:
  - default
post_views_count:
  - 249
categories:
  - G Suite(GoogleApps)
  - Gmail
  - iPad/iPod/iPhone
tags:
  - CardDAV

---
## Finding GoogleApps'(Gmail&#8217;s) CardDAV Principal URL for iPhone Configuration Utility {#outline__1}

<div class="section" lang="en">
  <p>
    <div style="text-align:right; font-size:small" lang="ja">
      <a href="https://blog.keinos.com/20130227_890" target="_blank">日本語版はこちら</a>
    </div>
  </p>
  
  <p>
    So far as I know, it might be something like below.
  </p>
  
  <pre>
[Example of "myaddress@sampledomain.com"]
https://myaddress%2540sampledomain.com@google.com/m8/carddav/principals/__uids__/myaddress%40sampledomain.com/lists/default/
</pre>
  
  <h3 id="outline__1_1">
    The situation
  </h3>
  
  <ul>
    <li>
      Want several iPhones to setup the same address book via CardDAV.
    </li>
    <li>
      Want to sync with Google Apps for Business&#8217; CardDAV account.
    </li>
    <li>
      Try to use the &#8220;iPhone Configuration Utility&#8221; for convenience.
    </li>
    <li>
      Couldn&#8217;t find out what the &#8220;Principal URL&#8221; is, at the configuration profile&#8230;
    </li>
  </ul>
  
  <p>
    It&#8217;s quite easy setting up one-by-one manually as taught at &#8220;<a href="http://support.google.com/mail/bin/answer.py?hl=en&#038;answer=2753077" target="_blank">Sync contacts with your iOS device</a>&#8220;, but I wanted to make a configuration profile to do all the basic settings, such as wi-fi, calendar, and shared address book at once.
  </p>
  
  <p>
    But things weren&#8217;t that easy&#8230;
  </p>
  
  <p>
    So far, I found the info, inside the extracted backup&#8217;s SqliteDB.
  </p>
  
  <pre>
Target File: /iOS Files/Library/AddressBook/AddressBook.sqlitedb
Target Table: ABStore
Target Schema: ExternalIdentifier
</pre>
  
  <p>
    But I still haven&#8217;t found what the &#8220;__uids__&#8221; is though.
  </p>
  
  <h5 id="outline__1_1_0_1">
    Tools that I used
  </h5>
  
  <ul>
    <li>
      To extract the buckup: <a href="http://supercrazyawesome.com/" target="_blank">iPhone/iPod Touch Buckup Extractor</a>
    </li>
    <li>
      To read the &#8220;.db&#8221; file: <a href="http://menial.co.uk/base/" target="_blank">Menial’s Base2</a>
    </li>
  </ul>
</div>