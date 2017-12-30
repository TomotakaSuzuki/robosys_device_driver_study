# robosys_device_driver_study
RaspberryPi3(Raspbian)での簡単なGPIOの制御
## Demo
[RaspberryPi3 でLチカ](https://www.youtube.com/watch?v=EID06rcr3jk&feature=youtu.be)
## Requirement
* RaspberryPi3
* セットアップ
   * 参考: [RaspberryPiのセットアップ](https://togetter.com/li/1153861)
* LED, resistor
## Circuit example
* 画像の右からそれぞれGPIO2:3番ピン, GPIO4:5番ピン, GPIO17:7番ピンをLEDと接続(間に100Ω抵抗)
* GNDは39番ピンで共通

![回路の例](https://github.com/TomotakaSuzuki/robosys_device_driver_study/blob/master/IMG_0208.jpg)
## Installation
* リポジトリのクローン
```
git clone https://github.com/TomotakaSuzuki/robosys_device_driver_study.git
```
* コンパイルとカーネルモジュールのロード
```
cd robosys_device_driver_study
make
sudo insmod myled.ko
sudo chmod 666 /dev/myled0
```
* カーネルモジュールをアンロードする場合
```
sudo rmmod myled
```
## Usage
* 右から順番に光らせる
```
echo 1 > /dev/myled0
```
* 両端と真ん中を交互に光らせる
```
echo 2 > /dev/myled0
```
