
# Домашнее задание к занятию «Микросервисы: принципы»

Вы работаете в крупной компании, которая строит систему на основе микросервисной архитектуры.
Вам как DevOps-специалисту необходимо выдвинуть предложение по организации инфраструктуры для разработки и эксплуатации.

## Задача 1: API Gateway 

Предложите решение для обеспечения реализации API Gateway. Составьте сравнительную таблицу возможностей различных программных решений. На основе таблицы сделайте выбор решения.

Решение должно соответствовать следующим требованиям:
- маршрутизация запросов к нужному сервису на основе конфигурации,
- возможность проверки аутентификационной информации в запросах,
- обеспечение терминации HTTPS.

Обоснуйте свой выбор.

| Решение |	Маршрутизация	| Аутентификация | HTTPS терминация | Дополнительные возможности | Лицензия
|:---:|:---:|:---:|:---:|:---:|:---:|
| Kong | Да |	Да | Да	| Плагины, мониторинг |	Open Source |
| NGINX	| Да | Да (с помощью Lua)	| Да | Балансировка нагрузки, кэширование |	Open Source |
| AWS API Gateway	| Да | Да | Да | Интеграция с AWS Lambda, управление версиями | Платный |
| Traefik |	Да |	Да |	Да	| Автообнаружение сервисов |	Open Source |
| Ambassador	| Да	| Да	| Да	| Kubernetes интеграция	| Open Source |

На основе таблицы, я бы выбрал Kong в качестве решения для API Gateway. Обоснование выбора:

- Маршрутизация и плагины: Kong предоставляет мощные возможности маршрутизации и поддержку плагинов, что позволяет легко расширять функциональность.
- Аутентификация: Kong имеет встроенные механизмы для проверки аутентификационной информации, что упрощает интеграцию с различными системами аутентификации.
- HTTPS терминация: Поддержка HTTPS терминации гарантирует безопасность при передаче данных.
- Сообщество и поддержка: У Kong большое сообщество и хорошая документация, что облегчает решение возникающих проблем.
- Масштабируемость: Kong хорошо масштабируется и подходит для микросервисной архитектуры.

## Задача 2: Брокер сообщений

Составьте таблицу возможностей различных брокеров сообщений. На основе таблицы сделайте обоснованный выбор решения.

Решение должно соответствовать следующим требованиям:
- поддержка кластеризации для обеспечения надёжности,
- хранение сообщений на диске в процессе доставки,
- высокая скорость работы,
- поддержка различных форматов сообщений,
- разделение прав доступа к различным потокам сообщений,
- простота эксплуатации.

Обоснуйте свой выбор.

| Брокер сообщений	| Кластеризация	| Хранение на диске	| Скорость работы	Форматы сообщений	| Разделение прав доступа	| Простота эксплуатации	|
|:---:|:---:|:---:|:---:|:---:|:---:|
| Apache Kafka |	Да |	Да |	Высокая |	JSON, Avro,Protobuf |	Да |	Средняя	|
| RabbitMQ |	Да |	Да |	Средняя |	JSON, XML, AMQP |	Да |	Высокая	|
| ActiveMQ |	Да |	Да	| Средняя	| JSON, XML, AMQP	| Да	| Средняя	|
| NATS	| Нет	| Нет	| Очень высокая	| JSON |	Нет	| Высокая	|
| Redis |	Нет	| Нет	| Очень высокая |	JSON |	Нет |	Высокая |

Я бы выбрал Apache Kafka в качестве брокера сообщений. Обоснование выбора:

- Кластеризация: Kafka поддерживает кластеризацию, что обеспечивает высокую доступность и отказоустойчивость.
- Хранение на диске: Kafka хранит сообщения на диске, что позволяет гарантировать их доставку даже в случае сбоя системы.
- Скорость работы: Kafka обеспечивает высокую скорость обработки сообщений, что критично для высоконагруженных систем.
- Форматы сообщений: Поддержка различных форматов сообщений (JSON, Avro, Protobuf) делает его универсальным инструментом для интеграции.
- Разделение прав доступа: Kafka предоставляет возможности для настройки прав доступа, что важно для обеспечения безопасности.
- Сообщество и поддержка: У Kafka большое сообщество и активная разработка, что гарантирует постоянное улучшение и поддержку.
