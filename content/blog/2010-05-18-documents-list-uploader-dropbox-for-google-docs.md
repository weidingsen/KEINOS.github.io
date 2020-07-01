---
title: 'Documents List Uploader: DropBox for Google Docs?'
author: KEINOS
type: post
date: 2010-05-17T16:00:00+00:00
url: /20100518_818
page_type:
  - default
post_views_count:
  - 170
categories:
  - Dropbox
  - G Suite(GoogleApps)
  - Google
  - Windows
tags:
  - Google文書

---
<div class="section">
  <p>
    &#8220;Documents List Uploader&#8221;は、Google DocumentsにファイルをアップロードするGoogle製のアップロード・ツールです。GMail、GoogleAppsのどちらのアカウントでも使えます。
  </p>
  
  <p>
    結論から言うと、シンプルで便利ですが、DropBox程の使い勝手はありません。現在、ベターと思われる組み合わせは、<a href="#idDropBoxForGoogleApps">記事下部</a>をご覧ください。
  </p>
  
  <pre>
■Documents List Uploaderのダウンロード先
<a href="http://code.google.com/intl/ja/apis/gdata/articles/doc_list_uploader.html" title=".NET Documents List Uploader Sample - Google Data Protocol - Google Code">http://code.google.com/intl/ja/apis/gdata/articles/doc_list_uploader.html</a>
※"Download the sample executable."のリンクからダウンロードできます。
</pre>
  
  <p>
    <img src="http://code.google.com/articles/support/doclist_uploader/doclistuploader.jpg" style="float:right;padding:0 0 10px 10px;" />
  </p>
  
  <p>
    このツールは、GoogleのGDataAPI開発チームが<a href="http://code.google.com/apis/documents/overview.html" target="_blank">Documents List Data API</a>の.NETでの利用方法のサンプルとして提供している簡易的なものです。
  </p>
  
  <p>
    使い方は簡単で、起動してファイルをドラッグ＆ドロップするだけです。
  </p>
  
  <p>
    ダウンロードして起動すると、右のような画面が起動します。ログイン情報（メールアドレスとパスワード）を入力して&#8221;Login&#8221;ボタンを押すと、すでにアップロードされているドキュメント一覧が表示されます。
  </p>
  
  <p>
    また、ボタンの下にある&#8221;Add DocList Uploader to right click menu&#8221;にチェックを入れると右クリックメニュー（Shellエクテンション）に&#8221;Send to Google Docs&#8221;（送る）メニューが追加されます。
  </p>
  
  <p>
    至極シンプルで便利なのですが、プログラミングのサンプルとして作られたツールのため、
  </p>
  
  <ul>
    <li>
      アップロードできるファイルの種類に制限がある
    </li>
    <li>
      フォルダでアップロードできない
    </li>
    <li>
      複数ファイルをアップロードできない
    </li>
  </ul>
  
  <p>
    などの制限があり、いささか残念です。
  </p>
  
  <p>
    また、アチキの環境依存かもしれませんが、Windows7では、右クリックで送ることができませんでした。<br style="clear:both" />
  </p>
  
  <hr />
  
  <p>
    <a name="idDropBoxForGoogleApps"></a>
  </p>
</div>