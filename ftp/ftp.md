# FTPサーバ構築マニュアル（vsftpd）

## 1. パッケージを更新する

```bash
sudo apt update
```

## 2. vsftpdをインストールする

```bash
sudo apt install vsftpd -y
```

## 3. サービスが起動していることを確認する

```bash
sudo systemctl status vsftpd
```

`active (running)` と表示されればOK

## 4. IPアドレスを確認する

```bash
ip a
```

接続先となるIPアドレスを確認！

## 5. FTPサーバへ接続する

```bash
ftp <IPアドレス>
```

## 6. ログインする

ユーザ名

```text
vagrant
```

パスワード

```text
vagrant
```

`230 Login successful.` と表示されればログイン成功！

## 7. 動作確認

ファイル一覧を表示

```bash
ls
```

```bash
mkdir ftp
```

接続を終了

```bash
bye
```
