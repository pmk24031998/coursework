# Компонентная архитектура

## Обоснование выбора архитектурного стиля

Микросервисная архитектура является эффективным подходом для разработки приложений, которые должны масштабироваться и быть гибкими в изменении. Микросервисная архитектура может предоставить следующие преимущества:

- Гибкость: Микросервисы могут быть разработаны и развернуты независимо друг от друга, что позволяет быстро вносить изменения в приложение без необходимости перезапуска всего приложения.

- Масштабируемость: Микросервисы могут быть масштабированы отдельно друг от друга, что позволяет легко управлять нагрузкой на приложение и обеспечивать высокую доступность.

- Устойчивость: Если один из микросервисов не работает, остальные микросервисы могут продолжать работу, что обеспечивает устойчивость приложения в целом.

- Легкость разработки: Разработчики могут работать над отдельными микросервисами, что упрощает процесс разработки и тестирования.

- Легкость внедрения новых функций: Новые функции могут быть добавлены в виде новых микросервисов, что позволяет быстро внедрять новые возможности в приложение.

## Диаграмма компонентов

На диаграмме представлены компоненты микросервисной архитектуры системы и интеграции между данными компонентами.

![PlantUML model](http://www.plantuml.com/plantuml/png/dLNVQnj747w_lsAhlYXWcZpafL1AOjbjJPHMiHpwQ5QdHJboFyJUga6KW2CxJOi3fYLGA84qbDBNgsirhYLT_eNT_wZVt7ANvIItYWEHPsVtvljcljdPMwdYKesYqFiWYFrmr1ViazRDwwsR-wqaLZo8XVpKIny6yP1B7h4s76ey56oOXECG2sVlaUJ3huE-Ui0-ld73ypf2fadSZ7ZC1q9ki8P-gQTwWVzd-cyzDGUDQ-KPFmn4hEZ8Btgcp-cOcM3RwuvJ9QBzpMGKzxaSDtj90hY1TUFyNIuV2WKFwoHIyR1nxLkFuL_5_Tv8Z4IJ3mCSljtPOPzp9HxnSOEmVj9lT0QqkSv1QQh_CK_CH9yIFZDF62oGDT_ZbywSmqUiwG2iZ5mRJ6Vcq4miOVYFSFG2lkzWdp2OLJR0E6K8ej_2cfddm8O7H-dZ6Q4ZNwBkicz6IIy8nUtXa78jR8O5iVyi72abPCFMDTT_0eZ2Bc1FWGAYS621KbC6v3p3YHFwarEcvX1SCf1avWZsGbzOsdhEbilAY9lzgSI8qbqn258bkGgIk5Lf-9AA0FpSBHY3CTL_aGde0riZVRvK8wjWlGvo5P0rcBl7KY6_2NpHeEqFDzX7NsxlaQrVNuN9Cf6jNhFVsrsNJ9yhtkDfmQQJf6eWHVTUk-3pEm7hXQiDbe0-Da_Va-1ZhowBVbsGQT-vN0sAP9vHjm0efz0PjH0nGl3CnS9ojIX-XL9cptqVB1IpTpw2Qpr1q8cK9vOpMn5pKZ4qntfUvvV3LMTuYLYjTKXUKIY78otg74_NLSpMIFodMj09ve4T6hP4k9MhP0cJmVqTn6ed0tP_XvAu4_IGArdwbOrDCuzwgunikQsCPICDQ1YanTYbEDiXJrNWfu9B_q4H-BUwX7gwaZOsvuo6wTDwOUjC7jkHWs9j1hiYtDzQEGKkkOxw3pEfGWEk6FLlgPZcEIDbVjGlYFTNMviju9K8xrhQxPptZUPvHRHI2Lj4_RFER8tmf9nJEQXDd7vo9ZIzGM_C8NPcP9KJW21sjxjxrx_Os-iGZeMfNbZtjM3OTtEgxrPVEsxxJEfNr7b5kbabAcWLT6tcjedCCH4YBbqdwIA8NAd9h_MnjlnAPlKSdQ2-8yYBTsyO0hZZR6uEQrSHZl_7Q5iCQEMMuCogL7LoxKkRjFrIH3m87PrjXHXLaS6ULAMy01_Sm9mURVD3EUyeSlTkISTL1Ug60Lqsc_TIjvWZdIFql3uU2bJph1n6TUgtHDmVHU6_)

## Описание компонентов

| № п/п | Тип             | Наименование                       | Технологии    | Описание                                                                                  |
|-------| --------------- | ---------------------------------- |---------------| ----------------------------------------------------------------------------------------- |
| 1     | Container       | Client registration service        | C#, .NET      | Регистрация клиента                                                                       |
| 2     | Container       | Client registration database       | PostgreSQL    | Хранение данных регистрации клиентов                                                      |
| 3     | Container       | Client account management service  | C#, .NET      | Управление личным кабинетом клиента: добавление, удаление, редактирование информации      |
| 4     | Container       | Client account management database | PostgreSQL    | Хранение данных личных кабинетов клиентов                                                 |
| 5     | Container       | Mobile App                         | Flutter       | Взаимодействие между пользователями и приложением                                         |
| 6     | Container       | Logging system                     | Elasticsearch | Управление логированием и хранение логов                                                  |
| 7     | Container       | Log UI                             | Kibana        | Визуализация данных Elasticsearch                                                         |
| 8     | Container       | API Gateway                        | API           | Обеспечивает взаимодействие с внешними системами                                          |
| 9     | External system | Google Analitycs                   |               | Сбор и визуализация статистики посещения и использования сервиса                          |
| 10    | External system | E-mail server                      |               | Хранение и передача сообщений информационных писем, подтверждение аккаунта                |