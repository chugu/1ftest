# 1ftest
1factor interview test

haproxy > app1, app2 (python simplewebserver)

проверено на 
macos 10.13.6 
vagrant 2.2.4
virtual box 6.0.6
ansible 2.7.10

Установка:
ansible-galaxy install -r requirements.yml 
vagrant up

Обновление:
deploy:
ansible-playbook playbooks/deploy.yml  -i inventory --extra-vars "app_version=v1.13"
update:
ansible-playbook playbooks/deploy.yml  -i inventory --extra-vars "app_version=v1.14"
rollback:
ansible-playbook playbooks/deploy.yml  -i inventory --extra-vars "app_version=v1.13"

Проверка доступности
while :;   do curl -Is http://192.168.4.2/ | grep Cookie;  done
