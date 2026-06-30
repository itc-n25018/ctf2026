# telnetのマニュアル

# 1 telnetサーバをダウンロードする
```bash
sudo apt update
sudo apt install inetutils-telnetd xinetd -y
```

# 2 インストールが終わったら、statusで確認する
```bash
sudo systemctl status xinetd
```

# 3 telnetの設定ファイルの作成
```bash
sudo vi /etc/xinetd.d/telnet
```
以下の内容を入力する

```bash
service telnet
{
    disable = no
    flags = REUSE
    socket_type = stream
    wait = no
    user = root
    server = /usr/sbin/in.telnetd
    log_on_failure += USERID
}
```

# 4 xinetdを再起動

```bash
sudo systemctl restart xinetd
```

# 5 xinetdの起動状態を確認する
```bash
sudo systemctl status xinetd
```

# 6 IPアドレスを確認する
```bash
ip a
```

# 7 telnetサーバへ接続する
```bash
telnet <IPアドレス>
```

# 8 ログインする
ログイン名  vagrant
パスワード　vagrant

 
