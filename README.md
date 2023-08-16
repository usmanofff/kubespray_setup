# Автоматизация установки Kubernetes кластера с помощью Kubespray и Terraform в Yandex Cloud

Инструкция была основана на базе видео "Установка кластера Kubernetes с помощью Kubespray" в Youtube. 

https://www.youtube.com/watch?v=WFXlr0bVTAQ

Перед установкой кластера необходимо проверить зависимости: kube_version: v1.26.7

- ansible==7.6.0
- ansible-core==2.14.6
- cryptography==41.0.1
- jinja2==3.1.2
- jmespath==1.0.1
- MarkupSafe==2.1.3
- netaddr==0.8.0
- pbr==5.11.1
- ruamel.yaml==0.17.31
- ruamel.yaml.clib==0.2.7

![image](https://github.com/usmanofff/kubespray_setup/assets/74288450/97deceeb-eaae-4dd9-a458-1081e49713e3)

Запускаем установку кластера с помощью подготовленной конфигурации terraform и ansible.

``` ./cluster_install.su```

Процесс установки занимает примерно 20 минут можно попить кофе...

Результат :

![image](https://github.com/usmanofff/kubespray_setup/assets/74288450/64020284-a8fd-4392-854a-9bc75ba1bbdc)


![kube_create](https://github.com/usmanofff/kubespray_setup/assets/74288450/1a35cba6-b97b-41e3-a54f-e5bde488d159)

В качестве сетевого взаимодействия выбран плагин flannel :

- kube_network_plugin: flannel # Хорошо работает до 50 узлов, простой

- flannel_interface_regexp: '192\\.168\\.20\\.\\d{1,3}' ( нужно указать диапазон  локальной сети кластера)

- kube_service_addresses: 10.233.0.0/18

- kubeconfig_localhost: true (создание файла для подключение к кластеру)

- docker_storage_options: -s overlay2 # Докер должен запускается с драйвером overlay2(рекомендуется использовать и он самый быстрый)














