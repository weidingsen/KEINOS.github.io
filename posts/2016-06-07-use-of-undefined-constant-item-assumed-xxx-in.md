---
title: Use of undefined constant item – assumed ’xxx in…
author: KEINOS
type: post
date: 2016-06-06T16:00:00+00:00
url: /20160607_954
page_type:
  - default
post_views_count:
  - 188
categories:
  - PHP
tags:
  - PHP5

---
## PHP5.xで&#8221;Use of undefined constant item &#8211; assumed &#8216;xxxx&#8217; in&#8230;&#8221;エラーが出るようになった {#outline__1}

<div class="section">
  <p>
    エラー内容としては「定義されていない定数を使用しようとしています」という意味なので当然と言えば当然なのですが、配列の添え字を指定する際にクォーテーションで囲っていない場合にでます。
  </p>
  
  <h3 id="outline__1_1">
    NGな例
  </h3>
  
  <pre>
$sample = $array[ hoge ];
</pre>
  
  <h3 id="outline__1_2">
    OKな例
  </h3>
  
  <pre>
$sample = $array[ 'hoge' ] ;
$sample = $array[ "hoge" ] ;
</pre>
  
  <p>
    ちょっとはまりました。疲れているのかも。とほほ。
  </p>
</div>