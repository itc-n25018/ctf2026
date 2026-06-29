# FTPサーバ構築マニュアル

# 1.パッケージのインストール

```bash
sudo apt update
sudo apt install vsftpd -y
```
-yをつけておくと最初の質問を自動で「yes」で答えた状態で返信してくれる

# 2.サービスの起動

```bash
sudo systemctl start vsftpd
```
