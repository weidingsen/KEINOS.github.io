---
title: PHPの正規表現で1文字スペースだけ置換する
author: KEINOS
type: post
date: 2012-02-15T16:54:56+00:00
url: /20120216_861
page_type:
  - default
post_views_count:
  - 279
categories:
  - PHP
  - 正規表現
tags:
  - preg_replace

---
## How to replace a single space using preg_replace in PHP {#outline__1}

<div class="section">
  <p>
    <a href="http://php.net/manual/ja/function.preg-replace.php" target="_blank">preg_replace</a>で、空白文字１つだけをマッチさせて置換させるための正規表現
  </p>
  
  <pre class="syntax-highlight">
<span class="synSpecial">&#60;?php</span>
<span class="synStatement">$</span><span class="synIdentifier">sResult</span> <span class="synStatement">=</span> <span class="synIdentifier">str_replace</span><span class="synSpecial">(</span>&#34;<span class="synConstant">#(\S)(\s)(\S)#</span>&#34; , &#34;<span class="synSpecial">\\</span><span class="synConstant">1●</span><span class="synSpecial">\\</span><span class="synConstant">3</span>&#34;, <span class="synStatement">$</span><span class="synIdentifier">str</span><span class="synSpecial">)</span>;
<span class="synSpecial">?&#62;</span>
</pre>
  
  <p>
    以下はコメントとスペースを削除する関数の例
  </p>
  
  <pre class="syntax-highlight">
<span class="synSpecial">&#60;?php</span>
<span class="synPreProc">function</span> fCallbackStrip<span class="synSpecial">(</span><span class="synStatement">$</span><span class="synIdentifier">sScript</span><span class="synSpecial">){</span>
<span class="synStatement">$</span><span class="synIdentifier">aReplace</span> <span class="synStatement">=</span> <span class="synType">array</span><span class="synSpecial">(</span>
&#34;<span class="synConstant">#(\S)(\s)(\S)#</span>&#34; <span class="synStatement">=&#62;</span> &#34;<span class="synSpecial">\\</span><span class="synConstant">1X●●●●●X</span><span class="synSpecial">\\</span><span class="synConstant">3</span>&#34;, <span class="synComment">/* ここで空白文字をマーキング（置換） */</span>
&#34;<span class="synConstant">#</span><span class="synSpecial">\t</span><span class="synConstant">#</span>&#34; <span class="synStatement">=&#62;</span> &#34;&#34;,
&#34;<span class="synConstant">#</span><span class="synSpecial">\n</span><span class="synConstant">#</span>&#34; <span class="synStatement">=&#62;</span> &#34;&#34;,
&#34;<span class="synConstant">#/\*.*?\*/#s</span>&#34; <span class="synStatement">=&#62;</span> &#34;&#34;,  <span class="synComment">/* C言語風コメントを削除 */</span>
&#34;<span class="synConstant">#\s\s+#</span>&#34;      <span class="synStatement">=&#62;</span> &#34;&#34;, <span class="synComment">/* 過剰なスペースを削除 */</span>
<span class="synSpecial">)</span>;
<span class="synStatement">$</span><span class="synIdentifier">aSearch</span> <span class="synStatement">=</span> <span class="synIdentifier">array_keys</span><span class="synSpecial">(</span><span class="synStatement">$</span><span class="synIdentifier">aReplace</span><span class="synSpecial">)</span>;
<span class="synStatement">$</span><span class="synIdentifier">sScript</span> <span class="synStatement">=</span> <span class="synIdentifier">preg_replace</span><span class="synSpecial">(</span><span class="synStatement">$</span><span class="synIdentifier">aSearch</span>, <span class="synStatement">$</span><span class="synIdentifier">aReplace</span>, <span class="synStatement">$</span><span class="synIdentifier">sScript</span><span class="synSpecial">)</span>;
<span class="synComment">/* 置換用配列 */</span>
<span class="synStatement">$</span><span class="synIdentifier">aReplace</span> <span class="synStatement">=</span> <span class="synType">array</span><span class="synSpecial">(</span>
&#34;<span class="synConstant">X●●●●●X</span>&#34;  <span class="synStatement">=&#62;</span> &#34;<span class="synConstant"> </span>&#34;, <span class="synComment">/* ここで戻す */</span>
&#34;<span class="synConstant">: </span>&#34;  <span class="synStatement">=&#62;</span> &#34;<span class="synConstant">:</span>&#34;,
&#34;<span class="synConstant">; </span>&#34;  <span class="synStatement">=&#62;</span> &#34;<span class="synConstant">;</span>&#34;,
&#34;<span class="synConstant"> {</span>&#34;  <span class="synStatement">=&#62;</span> &#34;<span class="synConstant">{</span>&#34;,
&#34;<span class="synConstant"> }</span>&#34;  <span class="synStatement">=&#62;</span> &#34;<span class="synConstant">}</span>&#34;,
&#34;<span class="synConstant">, </span>&#34;  <span class="synStatement">=&#62;</span> &#34;<span class="synConstant">,</span>&#34;,
&#34;<span class="synConstant">{ </span>&#34;  <span class="synStatement">=&#62;</span> &#34;<span class="synConstant">{</span>&#34;,
&#34;<span class="synConstant">;}</span>&#34;  <span class="synStatement">=&#62;</span> &#34;<span class="synConstant">}</span>&#34;, <span class="synComment">/* 末行のセミコロン削除 */</span>
&#34;<span class="synConstant">,</span><span class="synSpecial">\n</span>&#34; <span class="synStatement">=&#62;</span> &#34;<span class="synConstant">,</span>&#34;, <span class="synComment">/* セレクタの改行を削除 */</span>
&#34;<span class="synSpecial">\n</span><span class="synConstant">}</span>&#34; <span class="synStatement">=&#62;</span> &#34;<span class="synConstant">}</span>&#34;, <span class="synComment">/* 大括弧前の改行を削除 */</span>
&#34;<span class="synConstant">} </span>&#34;  <span class="synStatement">=&#62;</span> &#34;<span class="synConstant">}</span><span class="synSpecial">\n</span>&#34;, <span class="synComment">/* 大括弧ごとに1行にまとめる */</span>
<span class="synSpecial">)</span>;
<span class="synStatement">$</span><span class="synIdentifier">aSearch</span> <span class="synStatement">=</span> <span class="synIdentifier">array_keys</span><span class="synSpecial">(</span><span class="synStatement">$</span><span class="synIdentifier">aReplace</span><span class="synSpecial">)</span>;
<span class="synStatement">$</span><span class="synIdentifier">sScript</span> <span class="synStatement">=</span> <span class="synIdentifier">str_replace</span><span class="synSpecial">(</span><span class="synStatement">$</span><span class="synIdentifier">aSearch</span>, <span class="synStatement">$</span><span class="synIdentifier">aReplace</span>, <span class="synStatement">$</span><span class="synIdentifier">sScript</span><span class="synSpecial">)</span>;
<span class="synStatement">return</span> <span class="synIdentifier">trim</span><span class="synSpecial">(</span><span class="synStatement">$</span><span class="synIdentifier">sScript</span><span class="synSpecial">)</span>;
<span class="synSpecial">}</span>
<span class="synSpecial">?&#62;</span>
</pre>
  
  <p>
    ソースコードをMINIMIZE化（軽量化）する場合などで、連続スペースを１つの空白文字（スペース）に置換する処理を行うことがあります。
  </p>
  
  <p>
    しかし、ソースコード上のインデントをタブでなくスペースで行っていた場合、余計なシングル・スペースが出来ることになります。
  </p>
  
  <p>
    回避方法としては、予め１つのみの空白文字を別の文字に置き換えておいて、連続するスペースだけを削除した後にスペースに置き換えます。
  </p>
  
  <pre>
■流れ
&#34;   &#60;meta charset=&#39;UTF-8&#39;&#62;&#34;
↓
&#34;   &#60;meta●charset=&#39;UTF-8&#39;&#62;&#34;
↓
&#34;&#60;meta●charset=&#39;UTF-8&#39;&#62;&#34;
↓
&#34;&#60;meta charset=&#39;UTF-8&#39;&#62;&#34;
</pre>
</div>