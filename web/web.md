# Webサーバ構築マニュアル（Apache + Basic認証）

## 1. パッケージを更新する

```bash
sudo apt update
```

## 2. Apacheをインストールする

```bash
sudo apt install apache2 apache2-utils -y
```

## 3. Apacheの起動状態を確認する

```bash
sudo systemctl status apache2
```

`active (running)` と表示されれば正常！

## 4. Basic認証を行うディレクトリを作成する

```bash
sudo mkdir -p /var/www/html/private
```

## 5. ユーザ名とパスワードを作成する

```bash
sudo htpasswd -c /var/www/html/private/.htpasswd vagrant
```

## 6. .htaccessを作成する

```bash
sudo vi /var/www/html/private/.htaccess
```

以下の内容を入力します。

```text
AuthType Basic
AuthName "Private Area"
AuthUserFile /var/www/html/private/.htpasswd
Require valid-user
```

## 7. Apacheの設定を変更する

```bash
sudo vi /etc/apache2/apache2.conf
```

`<Directory /var/www/>` の `AllowOverride` を以下のように変更します。

```text
<Directory /var/www/>
    Options Indexes FollowSymLinks
    AllowOverride AuthConfig
    Require all granted
</Directory>
```

## 8. Apacheを再起動する

```bash
sudo systemctl restart apache2
```

## 9. IPアドレスを確認する

```bash
ip a
```

## 10. Webブラウザからアクセスする

ブラウザで以下にアクセス

```text
http://<IPアドレス>/private/
```

ユーザ名とパスワードを入力し、ページが表示されればBasic認証の設定は完了！

