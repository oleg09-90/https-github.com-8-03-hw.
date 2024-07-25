# Система мониторинга Zabbix

**Перваков Олег**

## Решения заданий

### Задание 1
sudo apt install postgresql
wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-4+ubuntu20.04_all.deb
dpkg -i zabbix-release_6.0-4+ubuntu20.04_all.deb
apt update
apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts
sudo -u postgres createuser --pwprompt zabbix
sudo -u postgres createdb -O zabbix zabbix
zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
sed -i 's/# DBPassword=/DBPassword=123456789/g' /etc/zabbix/zabbix_server.conf
sudo systemctl restart zabbix-server apache2
sudo systemctl enable zabbix-server apache2
![1](https://github.com/user-attachments/assets/b951fa88-ab4a-4b4e-a936-96b3fe4acdc1)
### Задание 2
wget https://repo.zabbix.com/zabbix/6.4/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.4-1+ubuntu20.04_all.deb
dpkg -i zabbix-release_6.4-1+ubuntu20.04_all.deb
apt update
apt install zabbix-agent
systemctl restart zabbix-agent
systemctl enable zabbix-agent
systemctl status zabbix-agent
![2](https://github.com/user-attachments/assets/3ac15366-1967-48e4-b176-2e50ad551e78)
![3](https://github.com/user-attachments/assets/bd20d548-d819-4759-a9b9-9e9cfdf6c49f)
### Задание 3
![4](https://github.com/user-attachments/assets/41431baf-2380-490e-bea4-6e8280e908c5)





