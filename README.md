Vagrant-стенд для обновления ядра и создания образа системы

    Обновить ядро ОС из репозитория ELRepo
    Создать Vagrant box c помощью Packer
    Загрузить Vagrant box в Vagrant Cloud

Для запуска ВМ из образа в Vagrant Cloud необходимо скачать вагрант-файл и ввести команду vagrant up
Для подключения к ВМ необходимо ввести команду vagrant ssh

Для выполнения задания потребовались следующие действия:

    Создание файла с конфигурацией для Packer в формате json, включающий:
        Ссылку на файл ks.cfg в разаделе boot_command
        Ссылку на базовый iso образ
        Ссылку на скрипты для запуска внутри образа
    Создание файла конфигурации ks.cfg в качестве kickstart для установки CentOS Stream 8
    Создание файлов со скриптами, обновляющих ядро Linux с использованием последней стабильной версии из репозитория elrepo-kernel
    Сборка образа с использованием команды packer build centos.json
    Добавление образа в Vagrant Cloud
    Инициализация Vagrantfile и его публикация в репозиторий git
