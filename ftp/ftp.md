# vsftpdインストール

# 1 vsftpdをインストールする
```bash
sudo apt update
sudo apt install vsftpd -y
```

# 2 ダウンロードをしたらvsftpdの起動を確認する
```bash
sudo systemctl status vsftpd
```
この時、実行結果後「active」と表示されていたらOK

# 3 IPアドレスの確認
```bash
ip a
```
# 4 接続する
```bash
ftp IPアドレス
```

# 5 ユーザ名、パスワードを聞かれるので両方とも「vagrant」と答える
```bash
vagrant
```

