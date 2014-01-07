# open-source-mouse
## sfc2013-design-strategy      
This document is made by [gitfab](http://gitfab.org)
---
#コンセプト
---
#実装 - ハードウェア
---
トラックパッドが主流となりつつある今，マウスにしかない特徴として，<b>マウスホイール</b>に着目する<br>
マウスホイールはトラックパッドには無い物理的な操作によってスクロールが可能である．スクロールによって我々は日々大量の情報を閲覧している．しかし，情報が多過ぎて，その中から必要な情報を選ぶことが，しばしば困難なことが多い．<br>
→大量の情報から必要な情報を選ぶスクロール中に，<b>マウスホイールが重くなることで，ユーザに対して情報をレコメンデーションしてくれるようなマウス"Attention Scroller"を提案する．</b><br>

具体的な仕組みとしては，マウスホイールに摩擦をかけることで，重さを変えるマウスを作る．<br>

<br>
●想定する利用シーン<br>
-Webの閲覧<br>
　検索エンジンにおけるレコメンド<br>
　ニュースサイトにおけるレコメンド<br>
　まとめサイトにおける赤字コメントの提示<br>
　facebook，Twitter等におけるLike数や親密さによる友達の投稿のレコメンド<br>

-長文の校正
　論文や文章の修正箇所の提示<br>
　プログラミングにおけるエラー部分の提示<br>
　<br>
●このマウスの利点<br>
大量にある情報から必要の無いと思われる情報を完全に除外してしまうのではなく，スクロールという行為の中で，<b>見たい情報は見逃すことなく，他の情報にも目を通すことができる．</b>注目したい情報と他の情報の前後関係を把握できる．<br>


---
<strong>●プロトタイプ（ハードウェア）</strong>
　<br>
　①<a href="http://akizukidenshi.com/catalog/g/gM-01905/">サーボモータ PICO/STD/F(GWS社製)</a>を使用<br>
　②マウスを開けて、ホイールにサーボモータのホーン（少し短く切る）が触れるようにグルーガンでしっかりと固定．<br>
　③サーボモータが入るように、電ノコでマウスの蓋を切る．<br>
　④Arduinoでサーボモータの角度を制御することでホイールの重さを制御．<br>
　　（以下のサンプルファイルで試しながらちょうどよい値を探る） <br>
[wheel_heavy.zip](https://raw.github.com/ken0324/open-source-mouse/Wheel-Heavy-Mouse/gitfab/resources/wheel_heavy.zip)

![mouse-01.jpg](https://raw.github.com/ken0324/open-source-mouse/master/gitfab/resources/mouse-01.jpg)

<iframe width="360" height="240" src="//www.youtube.com/embed/7tKLwSLQ5I0" frameborder="0"></iframe>

---
#実装 - ソフトウェア（Processing）

<strong>●ProcessingによるPCとの連携</strong>
<br>
　このマウスと連動する簡単なソフトウェアをProcessingで2つ実装<br>
　[Arduinoのコード]<br>
　[1]マウスの場所に応じてホイールの重さが変わる（画像左）→
[コード](https://raw.github.com/ken0324/open-source-mouse/Wheel-Heavy-Mouse/gitfab/resources/openmouse2.zip) 
 <br><iframe width="360" height="240" src="//www.youtube.com/embed/5L26mkcaLfo" frameborder="0"></iframe> <br>

　[2]スクロールしていくと段々重くなっていく、上に戻すと軽くなる（画像右）→[コード](https://raw.github.com/ken0324/open-source-mouse/Wheel-Heavy-Mouse/gitfab/resources/openmouse.zip)<br><iframe width="360" height="240" src="//www.youtube.com/embed/Cq4dI2Lq3Bo" frameborder="0"></iframe> <br>







---
#実装 - ソフトウェア（Web）
以下の赤塚さんのコメントを参考にJavaScriptでArduinoと連携させることを試みた．<br><font size="1">
http://www.mecha-mozilla.org/projects/arduino.js/
を使ってみてください！<br>
使い方やセットアップは同ページに書いてありますが、簡単にセットアップ方法をお伝えすると、<br>

１．https://github.com/mecha-mozilla/arduino.js/blob/master/core/sketch/CommandServer/CommandServer.ino を Arduino に焼く<br>
２．http://www.mecha-mozilla.org/projects/arduino.js/arduino-js.xpi を Firefox にドラッグ&amp;ドロップする<br></font>


①上記と同様のコードをArduinoにアップロード．<br>

②JavaScriptでスクロール位置に応じてArduinoに送るサーボモータの角度を変化させる．

以下，作成したサンプルファイル，<br>
[attentionscroller.html](https://raw.github.com/ken0324/open-source-mouse/Wheel-Heavy-Mouse/gitfab/resources/attentionscroller.html)<br>


動作の様子<br><iframe width="420" height="315" src="//www.youtube.com/embed/o6_0-ZBY39o" frameborder="0"></iframe>


---
#応用案



 − 摩擦の調整による素材感やテクスチャの提示<br>
 − 進むほどすり減るマウスホイール <br>
 − 情報量によって重くなるマウスホイール →情報の重さを感じる．<br>
・スクロールの限界を示す．ex マップのズーム限界etc <br>
・使用時間超過の提示<br>

---
