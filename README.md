# 個人用WEB開発用Vagrant&Ansible設定

### 使い方 (VirtualBox 5.2.0およびVagrant 2.0.1で動作確認済み)
1. VirtualBoxとVagrantをインストール
1. VagrantのプラグインとしてVirtualBox Guest Additionsをインストール
1. 使いたい環境に合わせて、Vagrantfileに記載しているパスを書きかえる。
1. Node.js等、すでに記載しているもの以外に追加したいアプリケーションがあれば、Ansible Galaxyからロールを探してきてansible/role_file/web-role.ymlに追記。
1. ansible/playbook-web.yml等に、上記で探してきたロールの設定を記載。記載済みのものについても変更があれば記載。
1. vagrant upして仮想環境作成

### ToDo
- MySQLのバージョンが5.7以上のものをインストールする際の設定を作成する。
- playbookをタスクやロール、機能ごとに分割する。

### 参考文献
- http://protagram.com/infra/ansibleのgalaxyでlamp環境を作る方法
- https://knowledge.sakura.ad.jp/3116/
- https://codereviewvideos.com/blog/ansible-php7-ubuntu/
- https://github.com/geerlingguy/ansible-role-mysql/issues/222
- http://recruit.gmo.jp/engineer/jisedai/blog/orchestration/
- https://blog.serverdensity.com/deploying-nginx-with-ansible/
- https://hack-le.com/nginx/