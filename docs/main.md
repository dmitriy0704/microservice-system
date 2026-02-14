# Заметки по микросервисам

## Ключевые понятия:

- observibility
- нагрузка RPS
- IOPS - input output operations second

## Технологии:

- Grafana - отображает происходящее в приложении
- Prometeus - метрики
- Loki - логи
- Tempo - трейсы приложения
- балансировщик нагрузки
- SAGA(типы: оркестрация, хореография)
- Безопасность:
    - IDP сервис(identity provider)
    - keycloak
- Spring Data Envers
- API Gateway
- MAKEFILE
- NEXUS
- Автогенерация кода

## Логика приложения:

1. Сервис Persons. Для аудита сервиса: Spring Data Envers.
2. Сервис безопасности. Keycloak со своей базой данных
3. Сервис API. Обрабатывает запросы от пользователя.(API Gateway)
4. Локальный maven: Nexus - хранение библиотек
5. Alloy client - собирает данные из приложения и отправляет в Prometeos, Loki и
   Tempo.

В папке проекта содержатся три проекта:

- Person
- API
- Infrastracture

## Замечания по сервисам:

### Alloy config:

`[alloy.md](configs/alloy.md)`
для: [config.alloy](../infrastructure/alloy/config.alloy
