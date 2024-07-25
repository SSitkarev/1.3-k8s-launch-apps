# Домашнее задание к занятию «Запуск приложений в K8S» - Сергей Ситкарёв

## Задание 1. Создать Deployment и обеспечить доступ к репликам приложения из другого Pod

Создать Deployment приложения, состоящего из двух контейнеров — nginx и multitool. Решить возникшую ошибку.

[deployment](https://github.com/SSitkarev/1.3-k8s-launch-apps/blob/main/src/deployment.yaml)

После запуска увеличить количество реплик работающего приложения до 2.

Продемонстрировать количество подов до и после масштабирования.

![Задание1](https://github.com/SSitkarev/1.3-k8s-launch-apps/blob/main/img/1.jpg)

Создать Service, который обеспечит доступ до реплик приложений из п.1.

[service](https://github.com/SSitkarev/1.3-k8s-launch-apps/blob/main/src/service.yaml)

![Задание1](https://github.com/SSitkarev/1.3-k8s-launch-apps/blob/main/img/2.jpg)

Создать отдельный Pod с приложением multitool и убедиться с помощью curl, что из пода есть доступ до приложений из п.1.

[multitool_pod](https://github.com/SSitkarev/1.3-k8s-launch-apps/blob/main/src/multitool_pod.yaml)

![Задание1](https://github.com/SSitkarev/1.3-k8s-launch-apps/blob/main/img/3.jpg)

## Задание 2. Создать Deployment и обеспечить старт основного контейнера при выполнении условий

Создать Deployment приложения nginx и обеспечить старт контейнера только после того, как будет запущен сервис этого приложения.

[nginx-init-deployment](https://github.com/SSitkarev/1.3-k8s-launch-apps/blob/main/src/nginx-init-deployment.yaml)

Убедиться, что nginx не стартует. В качестве Init-контейнера взять busybox.

Создать и запустить Service. Убедиться, что Init запустился.

[nginx-init-service](https://github.com/SSitkarev/1.3-k8s-launch-apps/blob/main/src/nginx-init-service.yaml)

Продемонстрировать состояние пода до и после запуска сервиса.

![Задание2](https://github.com/SSitkarev/1.3-k8s-launch-apps/blob/main/img/4.jpg)