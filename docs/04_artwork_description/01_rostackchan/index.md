# ﾛｽﾀｯｸﾁｬﾝ

ﾛｽﾀｯｸﾁｬﾝはM5Stackを使用したロボットである「ｽﾀｯｸﾁｬﾝ」の派生作品です。

制御にROSを使っており、関節角度を取得できます。

![](https://cdn-ak.f.st-hatena.com/images/fotolife/R/Ray_ar/20230916/20230916195619.jpg)

<br>

## ｽﾀｯｸﾁｬﾝとは？

ｽﾀｯｸﾁｬﾝとは、ロボットエンジニアのししかわ氏が開発された手のひらサイズのオープンソースソフト・ハードウェアロボットプロジェクトです。

ディスプレイ・CPUにM5Stack社が開発・販売する開発ボードであるM5Stackを使用しており、小型なサーボ2軸を足（ただし歩けない）としています。名称も組み込まれているM5Stackから取られています。

ｽﾀｯｸﾁｬﾝの初期リリースから2年、ものづくり系のユーザを越えて広く親しまれています。

[ｽﾀｯｸﾁｬﾝのリポジトリ（GitHub）](https://github.com/meganetaaan/stack-chan)

<br>

## 技術的な特徴

この作品は、「ロボットの開発で人気のミドルウェアであるROS 2を使ってｽﾀｯｸﾁｬﾝを制御する」をコンセプトにしています。

いわゆる「手段が目的になっている」作品です。

<br>

ROS 2にあるros2_controlは制御アルゴリズムをさまざまなハードウェアに適応させやすくするための開発リソースで、複数のサーボモータをサポートするｽﾀｯｸﾁｬﾝと相性がいいと思いました。

![](https://s3.ap-northeast-1.wasabisys.com/download-raw/githubio/rostackchan_description.png)

DynamixelHardwareInterfaceをもとにFeetechSCSInterfaceを作成したことで同じプログラムが異なるアクチュエータで動くようになりました。

小型化のためにRaspberryPi4を搭載したreTerminalを採用しています。

展示ではﾛｽﾀｯｸﾁｬﾝの動作が分かりやすいようにRvizでブロードキャストされたTFを表示しています。

Ubuntu + RaspberryPiの組み合わせではGUIが重くなりがちですが、これをRaspberryPi向けの軽量LinuxであるRaspberryPi OSで動かすことで軽快な動作を実現しています。

顔の動作にはmicro-ROSを採用しました。展示では、RaspberryPi側がWi-Fiアクセスポイントになっているので、外部のルータが不要となっています。

<br>

## リポジトリ

- [rostack-chan](https://github.com/Ar-Ray-code/rostack-chan)：ﾛｽﾀｯｸﾁｬﾝを動作させるためのROS 2パッケージです。
- [rpi-bullseye-ros2](https://github.com/Ar-Ray-code/rpi-bullseye-ros2)：RaspberryPi OS Bullseye + ROS 2のdpkgを配布しています。
- [feetech_scs_ros2_driver](https://github.com/Ar-Ray-code/feetech_scs_ros2_driver)：ﾛｽﾀｯｸﾁｬﾝに搭載されたサーボモータ向けのROS 2ドライバです。

<br>

## 関連URL

- [ﾛｽﾀｯｸﾁｬﾝの顔をROS 2で動かす（micro-ROS・M5Stack）](https://ar-ray.hatenablog.com/entry/2023/08/20/212113)
- [ROS 2で動くｽﾀｯｸﾁｬﾝを作ってみた（ros2_control）](https://ar-ray.hatenablog.com/entry/2023/08/06/212152)
- [ﾛｽﾀｯｸﾁｬﾝの顔をROS 2で動かす（micro-ROS・M5Stack）](https://ar-ray.hatenablog.com/entry/2023/08/20/212113)
- [ﾛｽﾀｯｸﾁｬﾝをラズパイの上に載せる（M5Stack・reTerminal・RaspberryPi）](https://ar-ray.hatenablog.com/entry/2023/09/16/200743)

