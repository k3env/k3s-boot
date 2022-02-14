# K3s Boot

![Ansible](https://img.shields.io/badge/Ansible-v2.12.2-%231A1918.svg?style=flat-square&logo=ansible&logoColor=white)

Плейбук для развертывания K3s

Был написан под собственные нужды.

## Подготовка

- установить зависимости плейбука:
  - `ansible-galaxy collection install community.docker`
- Заполнить инвентарь по аналогии с `inventory.yaml.example`

### etcd

- Сгенерировать ссылку для etcd autodiscovery (например, через публичный discovery `curl -X GET https://discovery.etcd.io/new?size=$CLUSTER_SIZE`)
- Сгенерировать токен кластера etcd
- При необходимости, указать необходимую версию etcd

### k3s

- Сгенерировать токен кластера k3s
- Указать подсети для подов и сервисов кластера
- Указать адрес для подключения к кластеру

## Использование

### Развертывание

Запустить плейбук `ansible-playbook -i your-inventory-file.yaml up.yaml`

### Удаление

Запустить плейбук `ansible-playbook -i your-inventory-file.yaml down.yaml`
