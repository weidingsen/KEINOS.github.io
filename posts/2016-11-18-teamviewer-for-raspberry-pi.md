---
title: TeamViewer for Raspberry Pi
author: KEINOS
type: post
date: 2016-11-18T06:16:16+00:00
url: /20161118_1899
featured_image: /wp-content/uploads/2016/12/20161118083804.png
page_type:
  - default
yuzo_related_post_metabox:
  - 'a:3:{s:17:"yuzo_include_post";s:0:"";s:17:"yuzo_exclude_post";s:0:"";s:21:"yuzo_disabled_related";N;}'
post_views_count:
  - 1548
categories:
  - RaspberryPi
  - Raspbian

---
## Raspbian8.0(Jessie)で動作する公式のTeamViewer {#outline__1}

<a href="http://f.hatena.ne.jp/KEINOS/20161118083804" class="hatena-fotolife" target="_blank"><img src="http://cdn-ak.f.st-hatena.com/images/fotolife/K/KEINOS/20161118/20161118083804.png" alt="f:id:KEINOS:20161118083804p:image:w640" title="f:id:KEINOS:20161118083804p:image:w640" class="hatena-fotolife" width="640" /></a>

### ■公式 TeamViewer for Raspberry Pi V.11のダウンロード {#outline__1_1}

<div class="information">
  <del datetime="2017-07-08T10:10:30+00:00"><a href="https://pages.teamviewer.com/published/raspberrypi/" target="_blank">https://pages.teamviewer.com/published/raspberrypi/</a></del><br /> 2017/07/07追記： Ver.12からベータ版扱いから（プレビューではありますが）<a href="https://community.teamviewer.com/t5/Knowledge-Base/How-to-install-TeamViewer-Host-for-Linux/ta-p/6318">正規版に昇格した</a>ようです。
</div>

### ■debファイルのインストール・コマンド {#outline__1_2}

<del datetime="2017-07-08T10:10:30+00:00"><br /> <code>&lt;br />
  pi@raspberrypi:~ $ sudo dpkg -i teamviewer-host_armhf.deb&lt;br />
</code><br /> </del>
  
`<br />
  pi@raspberrypi:~ $ sudo apt install ./teamviewer_12.0.xxxxx_yyy.deb<br />
` 
  
2017/07/07追記： Ver.12から\`apt install\`でインストールできるようになりました。詳しくは[Qiitaに記事をあげました][1]。

### ■チームビューアーとは {#outline__1_3}

遠隔操作のアプリではダントツの使いやすさを誇る<a href="https://www.teamviewer.com/ja/" target="_blank">TeamViewer</a>。ルータの設定でポートなどを空ける必要もなく、MacOS・Windows・Linux・Android・iOS（iPadやiPhone）と環境を選ばないため遠隔でサーバーやパソコンのメンテナンスを行うのにも重宝します。

お客様先へ技術サポートのために遠隔ツールを導入（インストール）する際に、「知らぬ間に覗かれるのではないか」と、仕組みがよくわからず導入を懸念される方でも、基本的にワンタイム・パスワード制なため導入しやすく、かつ使いやすい大変すぐれたアプリです。

個人利用の場合は無料ですが、会社で導入する価値は十分にあり、チャット・音声通話・ホワイトボード・録画機能など機能が多い割には安いと思います。

さて、RaspberryPiを設置して遠隔でメンテナンスを行いたいという場合、さまざまな方法があります。しかし、ラズパイの設置先が自宅でない場合ポートを勝手にあけられなかったり、あれこれとアプリケーションを入れないといけなかったりと知識も必要なため、勉強にはなりますがRaspberryPi(LINUX)を始めたばかりの方にはハードルが高い可能性もあります。

<a href="https://www.teamviewer.com/ja/download/linux/" target="_blank">Linux版TeamViewer</a>もありますがIntel入ってる系が前提でARM対応のものを探さないといけないなど、やはり<a href="https://pages.teamviewer.com/published/raspberrypi/" target="_blank">公式にRaspbianOS対応しているTeamViewerをダウンロード</a>して入れるのがいいと思います。（日本語サイトでは対応が遅く、検索しても出てきません）

### 注意点 {#outline__1_4}

注意というより、まだ始まったばかりなためRasPi版TeamViewerはVPN接続に対応していません。

また、インストール中に下記エラーが出た場合は、下のコマンドでパッケージを最適化してみてください。

<div class="information">
  E: dpkg was interrupted, you must manually run &#8216;sudo dpkg &#8211;configure -a&#8217; to correct the probrem.
</div>

<div class="information">
  pi@raspberrypi:~ $ sudo dpkg &#8211;configure -a
</div>

 [1]: http://qiita.com/KEINOS/items/673313682c45016b06cb