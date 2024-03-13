# Домашнее задание к занятию «Как работает сеть в K8s»

### Цель задания

Настроить сетевую политику доступа к подам.

### Чеклист готовности к домашнему заданию

1. Кластер K8s с установленным сетевым плагином Calico.

### Инструменты и дополнительные материалы, которые пригодятся для выполнения задания

1. [Документация Calico](https://www.tigera.io/project-calico/).
2. [Network Policy](https://kubernetes.io/docs/concepts/services-networking/network-policies/).
3. [About Network Policy](https://docs.projectcalico.org/about/about-network-policy).

-----

### Задание 1. Создать сетевую политику или несколько политик для обеспечения доступа

1. Создать deployment'ы приложений frontend, backend и cache и соответсвующие сервисы.
2. В качестве образа использовать network-multitool.
3. Разместить поды в namespace App.
4. Создать политики, чтобы обеспечить доступ frontend -> backend -> cache. Другие виды подключений должны быть запрещены.
5. Продемонстрировать, что трафик разрешён и запрещён.

### Ответы на пункты 1-3:

![](pic/1.png)
![](pic/2.png)
![](pic/3.png)
![](pic/4.png)
![](pic/5.png)

[Frontend](main/frontend.yaml) 

[Backend](main/backend.yaml)

[Cache](main/cache.yaml)

### Ответ на пункт 4:

![](pic/6.png)
![](pic/7.png)
![](pic/8.png)

[np-1](main/np-1.yaml)

[np-2](main/np-1.yaml)

[np-3](main/np-1.yaml)

### Ответ на пункт 5:

- frontend -> backend 
- frontend x cache
- backend x frontend
- cache x frontend 
- backend -> cache
- cache x backend 

![](pic/9.png)
![](pic/10.png)
![](pic/11.png)

### Правила приёма работы

1. Домашняя работа оформляется в своём Git-репозитории в файле README.md. Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.
2. Файл README.md должен содержать скриншоты вывода необходимых команд, а также скриншоты результатов.
3. Репозиторий должен содержать тексты манифестов или ссылки на них в файле README.md.