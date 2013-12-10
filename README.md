# Wheel-Heavy-Mouse
## sfc2013-design-strategy      
This document is made by [gitfab](http://gitfab.org)
---
#すり減るマウス

使った分だけすり減るパーソナルなマウス．<br>
　−仕事量が見える．<br>
　−自分の手に馴染んでくる．<br>
　−愛着が湧いてくる．<br>
　−使いながら形が変わる／形を気にしながら使い方が変わる．<br>
　−自分のクセが見える．<br>

![mouse--01.jpg](https://raw.github.com/ken0324/open-source-mouse/master/gitfab/resources/mouse--01.jpg)
---

---
#マウスホイール

マウスホイールによるスクロール = 進むこと、歩くこと

 − 進むほどすり減るマウスホイール <br>
 − 情報量によって重くなるマウスホイール →プロトタイプ作成しました(12/3)<br><strong>●プロトタイプ（ハードウェア）</strong>
　<br>
　①<a href="http://akizukidenshi.com/catalog/g/gM-01905/">サーボモータ PICO/STD/F(GWS社製)</a>を使用<br>
　②マウスを開けて、ホイールにサーボモータのホーンが触れるようにグルーガンでしっかりと固定．<br>
　③サーボモータが入るように、電ノコでマウスの蓋を切る．<br>
　④Arduinoでサーボモータの角度を制御することでホイールの重さを制御．<br>


![mouse-01.jpg](https://raw.github.com/ken0324/open-source-mouse/master/gitfab/resources/mouse-01.jpg)

<iframe width="560" height="315" src="//www.youtube.com/embed/7tKLwSLQ5I0" frameborder="0"></iframe>

<strong>●プロトタイプ（ソフトウェア）</strong>
<br>
　このマウスと連動する簡単なソフトウェアをProcessingで2つ実装<br>
　[Arduinoのコード]<br>
　[1]マウスの場所に応じてホイールの重さが変わる（画像左）→[コード]  <br><iframe width="560" height="315" src="//www.youtube.com/embed/5L26mkcaLfo" frameborder="0"></iframe> <br>

　[2]スクロールしていくと段々重くなっていく、上に戻すと軽くなる（画像右）→[コード] <br><iframe width="560" height="315" src="//www.youtube.com/embed/Cq4dI2Lq3Bo" frameborder="0"></iframe> <br>
---
