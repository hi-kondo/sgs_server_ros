# sgs_server_ros

# bluetooth関係セットアップ

依存パッケージインストール

`
sudo apt-get install libbluetooth-dev

`
bluetooth設定
`sudo gedit /lib/systemd/system/bluetooth.service`

下記を追加
```
ExecStart=/usr/lib/bluetooth/bluetoothd -C
ExecStartPost=/usr/bin/sdptool add SP
```

```
sudo systemctl daemon-reload
sudo systemctl restart bluetooth.service
```

機器接続
```
bluetoothctl
connect 〇〇 AndroidのMACアドレス
unblock MACアドレス
trust MACアドレス
defaut-agent
```

動作確認方法

Androidとペアリング後
bluetoothのSDPクライアントアプリを起動し
操作手順書に沿ってコマンドを実行する
