# Домашнее задание к занятию «Базовые объекты K8S» - `Горбачёв Олег`

### Задание 1. Создать Pod с именем hello-world

1. Создать манифест (yaml-конфигурацию) Pod.
2. Использовать image - gcr.io/kubernetes-e2e-test-images/echoserver:2.2.
3. Подключиться локально к Pod с помощью `kubectl port-forward` и вывести значение (curl или в браузере).

------

### Задание 2. Создать Service и подключить его к Pod

1. Создать Pod с именем netology-web.
2. Использовать image — gcr.io/kubernetes-e2e-test-images/echoserver:2.2.
3. Создать Service с именем netology-svc и подключить к netology-web.
4. Подключиться локально к Service с помощью `kubectl port-forward` и вывести значение (curl или в браузере).

------
### Решение задания 1. Создать Pod с именем hello-world

1. Написал манифест для пода.
2. Указал имя пода hello-world, указал образ gcr.io/kubernetes-e2e-test-images/echoserver:2.2:

![img_1](IMG/img_1.png)

2. Создал под и запустил его:

![img_2](IMG/img_2.png)

3. С помощью port-forward пробрасываю порт пода в локальную сеть, после чего могу подключиться к поду:

![img_3](IMG/img_3.png)

С помощью curl смотрю ответ от пода на GET запрос:

![img_4](IMG/img_4.png)

### Решение задания 2. Создать Service и подключить его к Pod

1 - 3. Пишу манифест для создания пода и сервиса, связываю их с помощью label и selector, использую образ gcr.io/kubernetes-e2e-test-images/echoserver:2.2:

![img_5](IMG/img_5.png)

Запускаю под и сервис:

![img_6](IMG/img_6.png)

4. Подключаюсь локально к Service с помощью kubectl port-forward:

![img_7](IMG/img_7.png)

С помощью curl смотрю ответ от пода на GET запрос:

![img_8](IMG/img_8.png)

При обращении к сервису netolgy-svc по проброшенному порту 8085 вижу ответ от пода netology-web, а значит, связь пода с сервисом работает.

Ссылки на манифесты:

Pod - https://github.com/RikLedger/12-Kubernetes-02/blob/main/SRC%20/pod.yaml

Service - https://github.com/RikLedger/12-Kubernetes-02/blob/main/SRC%20/service.yaml
