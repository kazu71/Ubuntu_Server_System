# Ubuntu ServerでUFW構築から設定まで
### UFWとは？
Linuxのファイアフォールシステムであり、コマンドを使って簡単に設定ができるツールです。
<br>
<br>

### UFWのインストール
<br>
<br>

OSの更新します。
```
sudo apt update
```
```
sudo apt upgrade
```
<br>
<br>

更新システムを反映するために再起動を行います。
```
sudo reboot
```
<br>
<br>

UFWシステムをインストールします。
```
sudo apt install ufw
```
<br>
<br>

UFWシステムを有効にします。
```
sudo systemctl enable ufw
```
<br>
<br>

###### 解放したいポート番号を開放します、ここでは、簡単なポート開放設定を例として説明します。<br>※例80番ポート<br>
以下のコマンドでポートを開放します。
```
sudo ufw allow 80
```

#### ポート開放設定の種類について
<br>
<br>

特にアクセス制限を設けない場合のポート開放の場合
```
sudo ufw allow 80
```
<br>
<br>

指定のIPのみにしかアクセスを許可しない解放の場合
```
sudo ufw allow from 192.168.1.25 to any port 80
```
<br>
<br>

指定のインターフェイスのみしかアクセス許可しない場合
<br>以下の情報を例として設定した場合<br>
- インターフェイス：eth0
- ポート番号:80
```
sudo ufw allow in on eth0 to any port 80
```





