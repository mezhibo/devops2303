**Задание 1. Yandex Cloud**

1. С помощью ключа в KMS необходимо зашифровать содержимое бакета:
 - создать ключ в KMS;

- с помощью ключа зашифровать содержимое бакета, созданного ранее.

2. (Выполняется не в Terraform)* Создать статический сайт в Object Storage c собственным публичным адресом и сделать доступным по HTTPS:

- создать сертификат;

- создать статическую страницу в Object Storage и применить сертификат HTTPS;

- в качестве результата предоставить скриншот на страницу с сертификатом в заголовке (замочек).



**Решение 1**

Создадим манифесты необходимых нам ресурсов 

[bucket.tf](https://github.com/mezhibo/devops2303/blob/1bd623230af516211118545cc91c5265055730a5/IMG/bucket.tf)

[network.tf](https://github.com/mezhibo/devops2303/blob/1bd623230af516211118545cc91c5265055730a5/IMG/network.tf)

[provider.tf](https://github.com/mezhibo/devops2303/blob/1bd623230af516211118545cc91c5265055730a5/IMG/provider.tf)

[vars_network.tf](https://github.com/mezhibo/devops2303/blob/1bd623230af516211118545cc91c5265055730a5/IMG/vars_network.tf)

[vars.tf](https://github.com/mezhibo/devops2303/blob/1bd623230af516211118545cc91c5265055730a5/IMG/vars.tf)



Делаем terrafrom apply и создаем наши ресурсы

![Image alt](https://github.com/mezhibo/devops2303/blob/1bd623230af516211118545cc91c5265055730a5/IMG/1.jpg)


Видим что ресурсы созданы

Зайдем в интерфейс яндекс клайд и посмотрим на наш созданый kms ключ


![Image alt](https://github.com/mezhibo/devops2303/blob/6cd427553bbb15d059c8ddffe91963c927858b18/IMG/2.jpg)


Проверим наличие бакета и загруженного в него файла

![Image alt](https://github.com/mezhibo/devops2303/blob/6cd427553bbb15d059c8ddffe91963c927858b18/IMG/3.jpg)


Убедимся что наш файл в бакете зашифрован


![Image alt](https://github.com/mezhibo/devops2303/blob/6cd427553bbb15d059c8ddffe91963c927858b18/IMG/5.jpg)



Теперьпопробуем просмотреть нашу картину

![Image alt](https://github.com/mezhibo/devops2303/blob/6cd427553bbb15d059c8ddffe91963c927858b18/IMG/4.jpg)

и видим что файл зашифрован и у нас access denied
