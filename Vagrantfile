Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"

  # IPアドレス
  config.vm.network "private_network", ip: "192.168.33.10"

  # ディレクトリ共有設定
  # 開発用(サーバのルート)
  config.vm.synced_folder "./webdir", "/var/www/webdir"
  # ansible設定用
  config.vm.synced_folder "./ansible", "/vagrant/ansible"

  # MySQLを使用するならmariaDBを消す
  # ToDo: いつかansibleに移す
  config.vm.provision "shell", inline: <<-SHELL
    yum -y remove mariadb-libs
    # rm -rf /var/lib/mysql
  SHELL

  # ansible設定
  config.vm.provision "ansible_local" do |ansible|
    ansible.galaxy_role_file = "./ansible/role_file/web-role.yml"
    ansible.galaxy_roles_path  = "./ansible/roles"

    ansible.playbook = "./ansible/playbook-web.yml"
    ansible.provisioning_path = "/vagrant/"
  end
end