---
title: 'ClamWin Freeで autorun.inf: Worm.Autorun-1792 FOUND'
author: KEINOS
type: post
date: 2009-12-28T21:03:28+00:00
url: /20091229_808
page_type:
  - default
post_views_count:
  - 255
categories:
  - Windows
  - ウィルス情報
tags:
  - CLAMWIN
  - Worm
  - autorun.inf

---
## autorun.inf: Worm.Autorun-1792 FOUND {#outline__1}

<div class="section">
  <h4 id="outline__1_0_1">
    検知ツール
  </h4>
  
  <p>
    <a href="http://www.clamwin.com/" target="_blank">CLAMWIN Free Anti Virus</a> Ver.0.95.3
  </p>
  
  <p>
    (ウィルスDBバージョン:main 51;daily 10238)
  </p>
  
  <h4 id="outline__1_0_2">
    感染メッセージ内容
  </h4>
  
  <blockquote>
    <p>
      J:\autorun.inf: Worm.Autorun-1792 FOUND
    </p>
  </blockquote>
  
  <p>
    autorun.infファイルに&#8221;Worm.Autorun-1792&#8243;というAutorunウィルス(ワーム)を発見したという内容です。
  </p>
  
  <h4 id="outline__1_0_3">
    感染されたautorun.infの内容
  </h4>
  
  <p>
    &#8220;fcay.exe&#8221;という実行ファイル(プログラム)を、USB挿入時に実行するようにautorun.infに追記（感染）されます。
  </p>
  
  <p>
    追記内容は下記参照。
  </p>
  
  <pre>
[AutoRun]
open=fcay.exe
shell\open\Command=fcay.exe
</pre>
  
  <h4 id="outline__1_0_4">
    fcay.exeの内容
  </h4>
  
  <p>
    この、autorun.infに記載されている&#8221;fcay.exe&#8221;についてですが、今回このファイル自体はUSBにはコピーされていなかったので感染を広げることはなかったのですが、気持ち悪いので調べたところ、<a href="http://www.prevx.com/filenames/X102586447594845934-X1/FCAY.EXE.html" target="_blank">Prevxによると下記挙動をするEXE(実行ファイル)のようです</a>。
  </p>
  
  <p>
    どうやら日本で発症したもののようで、<a href="http://www.google.co.jp/search?q=%22fcay.exe%22+OR+%22xvassdf.exe%22+OR+%22ierdfgh.exe%22+OR+%22revo.exe%22&#038;lr=lang_ja&#038;ie=utf-8&#038;oe=utf-8&#038;aq=t&#038;client=firefox-a&#038;rlz=1R1MOZA_ja___JP360" target="_blank">xvassdf.exe,ierdfgh.exe,revo.exe</a>などのkaba系統と同類のようです。
  </p>
  
  <pre>
<b>動作／病症</b>
FCAY.EXE はPC起動時に特定のプログラムを実行するよう、レジストリに書き込む動作をします。
また、隠しファイルとして表示しないよう設定を変更し、隠しファイルを表示する設定にしても勝手に元に戻すため、いささか対応が面倒な一品です。
<b>初回発見</b>
<a href="http://www.prevx.com/" target="_blank">Prevx</a>によると、FCAY.EXE は2009/12/8に日本で初めて発見されたそうです。
<b>ファイル名のエイリアス（亜種）</b>
FCAY.EXE は下記名前でも使われています:
XVASSDF.EXE, AR.EXE, 58833993.EXE
</pre>
  
  <h4 id="outline__1_0_5">
    感染されたautorun.infの駆除方法
  </h4>
  
  <p>
    ClamWinの[Tools]-[Preferenses]-[Infected Files]で[Move To Quarantine Folder]にチェックを入れて、感染ファイルを&#8221;Data\Quarantine\&#8221;フォルダに隔離する設定に変更します。
  </p>
  
  <p>
    再度スキャンを実行すると感染ファイルを&#8221;autorun.inf.infected&#8221;とリネームして隔離フォルダに隔離してくれます。当然ですが、その場合はUSB挿入時の自動起動はされなくなります。
  </p>
  
  <p>
    隔離後、&#8221;autorun.inf.infected&#8221;を削除します。
  </p>
  
  <p>
    もちろん該当するファイル、&#8221;autorun.inf&#8221;と、存在するならば&#8221;fcay.exe&#8221;などを、手動で駆除（リネームや削除を）してもかまいません。
  </p>
  
  <p>
    一度駆除したのに、再度スキャンして再発しているようであれば、<a href="http://www.google.co.jp/search?hl=ja&#038;client=firefox-a&#038;rlz=1R1MOZA_ja___JP360&#038;hs=GxW&#038;q=%E9%A7%86%E9%99%A4+%22fcay.exe%22+OR+%22xvassdf.exe%22+OR+%22ierdfgh.exe%22+OR+%22revo.exe%22&#038;btnG=%E6%A4%9C%E7%B4%A2&#038;lr=lang_ja&#038;aq=f&#038;oq=" target="_blank">fcay.exe,xvassdf.exe,ierdfgh.exe,revo.exeに感染している可能性があります</a>。
  </p>
  
  <p>
    ※参考文献：<a href="http://www.clamwin.com/content/view/146/27/" target="_blank">”My computer has been compromised, what do I do?”</a>
  </p>
</div>