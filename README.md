# robosys_device_driver_study
RaspberryPi3(Raspbian)での簡単なgpioの制御
## Demo
[RaspberryPi3 でLチカ](https://www.youtube.com/watch?v=EID06rcr3jk&feature=youtu.be)
## Requirement
* RaspberryPi3
* セットアップ
   * 参考: [RaspberryPiのセットアップ](https://togetter.com/li/1153861)
* LED, resistor
## Installation
1. リポジトリのクローン
```
git clone https://github.com/TomotakaSuzuki/robosys_device_driver_study.git
```
2. コンパイルとインストール
```
cd robosys_device_driver_study
make
sudo insmod myled.ko
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
