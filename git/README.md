# GitHub 於 Linux 的環境設定

1. 為 GitHub 產生一組 Key

    + ssh-keygen -t rsa -C "your_email@youremail.com"
    ```
    Generating public/private rsa key pair.
    Enter file in which to save the key     (/home/user/.ssh/id_rsa): id_rsa_github
    Enter passphrase (empty for no passphrase):
    Enter same passphrase again:
    Your identification has been saved in id_rsa_github.
    Your public key has been saved in id_rsa_github.pub.
    The key fingerprint is:...
    ```
1. 將 Key 設定到 GitHub 裡面

    + 登入 GitHub
    + Account Settings -> SSH Public Keys -> Add another public key
    + cat id_rsa_github.pub # 貼上這全部內容

1. 設定專給 GitHub 的 key

    1. vim ~/.ssh/config
    ```
    Host github
    HostName github.com
    User git
    Port 22
    identityfile ~/.ssh/id_rsa_github
    ```
    1. ssh github # 測試
    ```
    Warning: Permanently added 'github.com,207.97.227.239'     (RSA) to the list of known hosts.
    PTY allocation request failed on channel 0
    Hi tsung! You've successfully authenticated, but GitHub     does not provide shell access.
    Connection to github.com closed.
    ```
1. 設定自己的 Git 環境
    + git config --global user.name "Firstname Lastname"
    + git config --global user.email "your_email@youremail.com"

1. 取得 GitHub API Token 與 設定

    1. 登入 Github
    1. Account Settings -> Account Admin -> 取得 API token      (0123456789yourf0123456789token)
    1. git config --global github.user username
    1. git config --global github.token 0123456789yourf0123456789token
1. 到此即設定完成.

