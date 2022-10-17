Установка Elasticsearch
=========

Роль установки Elasticsearch из локального архива дистрибутива. Роль копирует архив с дистрибутивом на указанные машины, распаковывает его и устанавливает в `/etc/profile.d/` файл `elk.sh`, содержащий скрипт для установки переменной `ES_HOME` на каталог установки Elasticsearch и добавления `$ES_HOME/bin` к `PATH`.

Переменные
--------------

- elastic_version: версия Elasticsearch, по умолчанию 8.4.3
- elastic_home: каталог, Elasticsearch, по умолчанию `/opt/elastic/8.4.3`
- elastic_archive: имя архива с дистрибутивом Elasticsearch, по умолчанию `elasticsearch-8.4.3-linux-x86_64.tar.gz`

Тестирование
----------------

В каталоге `molecule` имеются скрипты для тестирования роли с помощью Docker на трех платформах:

- docker.io/pycontribs/ubuntu:latest
- docker.io/pycontribs/centos:8
- docker.io/pycontribs/centos:7

Пример Playbook
----------------
```yaml
- hosts: elastic
  roles:
    - martynov-andrey.elastic-role
```