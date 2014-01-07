# open-source-mouse
## sfc2013-design-strategy      
This document is made by [gitfab](http://gitfab.org)
---
#重くなるマウスホイール
---
#実装 - ハードウェア
---
マウスホイールによるスクロール = 進むこと、歩くこと

 − 進むほどすり減るマウスホイール <br>
 − 情報量によって重くなるマウスホイール →
→どう使うか？<br>
・情報の重さを感じる．<br>
・大切な情報を見逃さない．スクロールしていくと，重要な情報，オススメの情報の上でマウスホイールが重くなる．<br>
・スクロールの限界を示す．ex マップのズーム限界etc <br>
・<br>


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
以下の赤塚さんのコメントを参考にJavaScriptでArduinoと連携させることを試みた．<br>

<font size="1">
http://www.mecha-mozilla.org/projects/arduino.js/
を使ってみてください！<br>
使い方やセットアップは同ページに書いてありますが、簡単にセットアップ方法をお伝えすると、<br>

１．https://github.com/mecha-mozilla/arduino.js/blob/master/core/sketch/CommandServer/CommandServer.ino を Arduino に焼く<br>
２．http://www.mecha-mozilla.org/projects/arduino.js/arduino-js.xpi を Firefox にドラッグ&ドロップする<br>
</font>


①上記と同様のコードをArduinoにアップロード．<br>

②JavaScriptでスクロール位置に応じてArduinoに送るサーボモータの角度を変化させる．

以下，作成したサンプルファイル，<br>
[attentionscroller.html](https://raw.github.com/ken0324/open-source-mouse/Wheel-Heavy-Mouse/gitfab/resources/attentionscroller.html)<br>


動作の様子<br>
<iframe width="420" height="315" src="//www.youtube.com/embed/o6_0-ZBY39o" frameborder="0" allowfullscreen></iframe>


---
