# Автоматизация установки Kubernetes кластера с помощью Kubespray и Terraform в Yandex Cloud

Инструкция была основана на базе видео "Установка кластера Kubernetes с помощью Kubespray" в Youtube.

Код был форкнут из репозитория https://git.cloud-team.ru/lections/kubernetes_setup и добавлен с патчами в репозиторий https://github.com/patsevanton/kubespray_terraform_yandex_c

Запускаем установку кластера с помощью подготовленной конфигурации terraform и ansible.

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

Параметры кластера :
- master node
- worker node



``` ../cluster_install.su```


















