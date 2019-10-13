# php7-nginx-phpmyadmin
PHP7.3+Nginx+PHPMyAdmin+MySQL5.7

# 実装時に起きたエラー

docker-composeのphpmyadminでvolumes指定するとエラーになった為volumesを削除。
volumesを削除すればエラーは消えた為、「session.save_path」で指定されているディレクトリへの編集権限がないのが原因ではなさそう。  

docker-compose.yml：
```
volumes:
      - ./phpmyadmin/sessions:/sessions
```

エラー内容（PHPMyAdminをブラウザで開いたとき）：
```
phpMyAdmin - Error
Error during session start; please check your PHP and/or webserver log file and configure your PHP installation properly. Also ensure that cookies are enabled in your browser.

session_start(): Session data file is not created by your uid

session_start(): Failed to read session data: files (path: /sessions)
```
