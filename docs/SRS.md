# SRS

## Требования к системе NFRQ

### Производительность

**`NFPER1`** Система должна обслуживать нем менее 1000 пользователей в период пиковой активности с 13:00 до 20:00 по местному времени, со средней продолжительностью сеанса 8 минут.  

**`NFPER1`** Система должна выводить пользователю сообщение о подтверждении в среднем за 3 секунды и не более чем через 6 секунд после того, как пользователь отослал информацию системе.  

### Безопасность

**`NFSEC1`** Система должна позволять пользователям просматривать только обьявления, размещенные ими лично, но не другими пользователями.

### Масштабируемость

**`NFEXT1`** Сервис должен поддерживать ежегодный рост клиентов на 10% без потери текущей производительности.

### Надежность

**`NFROB1`** Вероятность возникновения критической ошибки должна составлять не более 10% в течение месяца.  

### Доступность

**`NFAVL1`** Система должна быть доступна 98% времени между 5:00 и полуночью по местному времени и 90% времени между полуночью и 5:00 по местному времени, за исключением времени планового обслуживания.  

**`NFAVL2`** Допустимое время простоя в сутки не более 30 минут.

### Особенности хранения данных

**`NFDT3`** Бекапы БД должны производиться каждые 60 мин.  

**`NFDT4`** Бекапы БД должны храниться 7 дней с момента создания.

### Концептуальная целостность

**`NFARC1`** Система должна соответствовать архитектурному стилю REST.  

### Поддерживаемость

**`NFSUP2`** Система должна обеспечивать мониторинг производительности с использованием графического интерфейса.

## Требования к функциям (задачам), выполняемым системой

### UseCase диаграмма

Основные функции системы представлены в виде UseCase диаграммы.  

![PlantUML model](http://www.plantuml.com/plantuml/png/fPJBQjj058RtUeg3DsaN2VHUGXS1qqLeLe4ym22DBH5vnaYZq50ASTBBeW6NqaKffUaZsBcqZfte6MRUgF-CRJIrtAJGW6FDcV__pfavHzx85SjKqKc3bBSKAKbPqeuLHKd6GvL84QnGlfk8BijOXxOImTL-bvFCL2o3W8LAPjJGN_L4Z_I5lZQ73M8v5MaGM3yJxPHZ_mVsplJ8zCoXET03ymxFVTBZogO73NeL4FvMoCUvK97paEMSxkmqL--jqp_XxjewCjxUIMk8-q1yX-RAQlM0mAZnz6WPBsGYvEdsKke3K3-Q8sYT0xWtS8zlAeyLAbv2UcX9UcmP-hJomstUe-0IjPPaoNgeHmXSL42qR8yfllMY1dq4w0bELveU3bxQav9reyeIuQlgs2L1SgfBb7f9RlCCgQwn-MikSiboph8mtXGjMKls6Cc-GEvks7rmyFzCnwD4DMMdoyJ-qfnFaFCpC4Cz06vIPKN879j-5JHz1qn4pZErpNErbFVKFyFjD9HNiUQ3_6tcFTS_qQM3FtA4CGztcwdrDknGsldvP5MtJ8w3hAwwh-Sl5HVsBQMkJ8JArrrKd-WIAOUwdFKO2qmIFkVc2BSpCST0VJ1l2UFQ0xjqcvUDO5fW2hp_wjYrFwlJHtgsjkRD0AtZGiEqYFYYfXhAlskgNjHPVX9e5mS1Ocwl8NBL-oJVu09rjJkb5VclzeAcmmHhyyo_53yuR-Iqv_R_F3BbnbBcV5D4oLuI5InjIZpQbkLL6kiHKl7PRwzitU0AfaN1vYnOlWusiC9F-6y0)

### Описание UseCase

#### Регистрация клиента

| Название                                            | UC-1: Регистрация клиента                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|-----------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Краткое описание                                    | Регистрация клиента в приложении для последующего размещения обьявлений.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Субъекты                                            | 1. Пользователь - клиент или менеджер<br/>2. Система                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Предусловие                                         | Пользователь зашел на страницу регистрации                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Основной сценарий                                   | 1. Пользователь переходит на страницу регистрации клиентов. <br/>2. Система выводит список типов бизнеса. <br/>3. Пользователь выбирает тип бизнеса из предложенного списка и нажимает кнопку - N1. <br/>4. Система выводит список стандартных тарифов. <br/>5. Пользователь выбирает стандартный тариф или N2 и нажимает кнопку - N1. <br/>6. Система выводит форму ввода контактных данных. <br/>7. Пользователь заполняет форму и нажимает кнопку - N1. <br/>8. Система проверяет корректность заполненной информации. <br/>9. Система выводит всю введенную пользователем информацию для проверки. На странице отображаются кнопки N3 и N4. <br/>    1. Если введенная пользователем информация некорректная - AF1. <br/>10. Пользователь нажимает кнопку - N3. Конец сценария. <br/>    1. Если пользователь вышел из приложения и не нажал кнопку N3 - AF2. <br/>    2. Если пользователь захотел изменить введенную информацию - AF3. |
| Альтернативный сценарий                             | AF1: Информация заполнена некорректно. <br/>1. Система выводит всю введенную пользователем информацию. Некорректно заполненная информация выделяется цветом. Кнопка N3 недоступна для нажатия. <br/>2. Пользователь нажимает кнопку N4 и корректирует информацию. <br/>3. Переход к п.8 основного сценария. <br/>AF2: Регистрация не подтверждена. <br/>    1. Система сохраняет введенные пользователем данные. <br/>    2. Система отправляет сообщение оператору о незавершенной регистрации ЮЛ. Конец сценария. <br/>AF3:  Изменение введенной информации. <br/>1. Пользователь нажимает кнопку N4 и корректирует информацию. <br/>2. Переход к п.8 основного сценария.                                                                                                                                                                                                                                                                  |
| Наименования элементов пользовательского интерфейса | N1: “Далее” <br/>N2: “Подобрать индивидуальный тариф” <br/>N3: “Подтвердить регистрацию” <br/>N4: “Изменить информацию”                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Диаграмма                                           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
 
![PlantUML model](http://www.plantuml.com/plantuml/png/bLN1QXDH5Ds_htZ4HHSX47GdKke750eknSMRpBCE9fCnCv6Y23Qr8YW6HH14gyKVYB5Zfub9V-6-F_BSkMHy9QccNSnqtjnpxhddt2HRQMPwMR_JLXiFej3g-zrk5dJtLFemYXFJCntzL6dyRPkzRPkcPjVUYPvOVRtPLC-yejG-wjkuPQLu1vHHAqfCdEsOC8pYNNsZAJJ2SRiTxSQwPUFCzi1Z-batxdS2szErMy7ctUQzcbAcbNNnJ9zeIWNbD7E3cZQfxgV0G29UVSFnJohSlXkuvpHoB_7_iAQlPJqJfn06_h9hybSFKCTIJJCgW1XfF2pHK57sIg1r1SDd54nGEdVxbEC-Pl2_U23vSTGIgj1a9Z2f1Syxg3Y50ZfXEPZmjJiiwyEWBDsusFOhM0kuCQTVx0UxKbQR954s3ZNdfjYUUhsywSPcEK6zVbFJaHkmPhGOk3SQ6ZqJt84llfAk60oIpOL-q7m4vbn6Hx5GqJdZ86kYqMJ4AjqBF8wLu8GZ3AuC3mFTyDet6c0uNgCROw3zlm3V95I-Hv0vEqE5fWagPbnF4rmH3ULUJfIBERx37C-SAN2NsPW4biDQ8U6nvSKf-u3gAGxpHVHQZd1mfaH-rKH6izAdx92p624h0CT0EFmjqRctckQNxAEN2I8f2Rz0pDbYwkh3HYEbJ3lJz9qZGizND0F9S2Ml6yfkSs3-kdWVNisZyWNDe1rd9QIIumqfkQ47MoDsYhKoi3jaDUmMmcJ7fBj79Sls0Uz-eDsuYiEVRWt19nN1T5bljJTNCGW8WVBghG-rxTHUrEOE-4kWN2GVuti5mSiZihK-qUf0l045SGI51RoONFfzkJpUUZ0RXseB5_m4_G40)

## Информационная модель

### Модель предметной области

В рамках MVP проекта были выделены основные сущности с атрибутами и определены связи между ними.

Базовыми сущностями являются:

- Тариф
- Клиент
- Обьявление

![PlantUML model](http://www.plantuml.com/plantuml/png/ZLJDYjfG5DxVfxXaAKtfl42PpRn6Xq25XfhCe74XfL2Zq8M2XGeLGQrjroLQfHhr-Whdlb6_ZrWRKqTSJBZtdEzyFtSEtjOYhnhLWugglVN3Hw_g1RhYX-MeyLZM3zNepODITs7aHmqjGzd8IfQoix5-fxGkoKWI-IrpV7Vii2O3L4Sy0J-H2Kyobi_ozL3zQJy0kv2L_IXBsvGKjxK6nG8D50uaMzlJHB4egOt5u9Im2Iw3Ze6kmIG-CpRn5wlt_znEE0dI9cOJO5SsndrZk_UI7eEWXIX7HPxa1-1Rz84vLBvn4DxQqDgnSXTuVYKd1aJ2MBPzuM66OiWBGqqovyS7W24hNS9n2sFm2NiTMT__nzq7p_wvjYtmRFWCHvzJIKc0RvAnrmCjKuQqCU65vAI3Kp1GY9Slb4Bx5srYXh9us2m80P_uhw3HOkCxPE6QrFbWOvdPhkt9F6jHEqk1pfuYnHVAd575Th9Ck1iWjc9eoNQVI6QAIjWVAacVWqJ97cLJC2k6VEfajqkkwzmyApdNxz3flFE2mwxxagSR9xST1TnV533vC1V90QO_IfnzNgLo2_FATQzTBioTOIjwlFpWwhOSliPloHy0)

### Модель данных

<p align="center">
    <img width="500" align="center" src="https://raw.githubusercontent.com/geksogen/TZ_SA_/master/SRS/diagrams/data_model.PNG" alt="demo"/>
</p>

## Компонентная архитектура

### Обоснование выбора архитектурного стиля

Микросервисная архитектура является эффективным подходом для разработки приложений, которые должны масштабироваться и быть гибкими в изменении. Микросервисная архитектура может предоставить следующие преимущества:

- Гибкость: Микросервисы могут быть разработаны и развернуты независимо друг от друга, что позволяет быстро вносить изменения в приложение без необходимости перезапуска всего приложения.

- Масштабируемость: Микросервисы могут быть масштабированы отдельно друг от друга, что позволяет легко управлять нагрузкой на приложение и обеспечивать высокую доступность.

- Устойчивость: Если один из микросервисов не работает, остальные микросервисы могут продолжать работу, что обеспечивает устойчивость приложения в целом.

- Легкость разработки: Разработчики могут работать над отдельными микросервисами, что упрощает процесс разработки и тестирования.

- Легкость внедрения новых функций: Новые функции могут быть добавлены в виде новых микросервисов, что позволяет быстро внедрять новые возможности в приложение.

### Диаграмма компонентов

На диаграмме представлены компоненты микросервисной архитектуры системы и интеграции между данными компонентами.

![PlantUML model](http://www.plantuml.com/plantuml/png/dLNVQnj747w_lsAhlYXWcZpafL1AOjbjJPHMiHpwQ5QdHJboFyJUga6KW2CxJOi3fYLGA84qbDBNgsirhYLT_eNT_wZVt7ANvIItYWEHPsVtvljcljdPMwdYKesYqFiWYFrmr1ViazRDwwsR-wqaLZo8XVpKIny6yP1B7h4s76ey56oOXECG2sVlaUJ3huE-Ui0-ld73ypf2fadSZ7ZC1q9ki8P-gQTwWVzd-cyzDGUDQ-KPFmn4hEZ8Btgcp-cOcM3RwuvJ9QBzpMGKzxaSDtj90hY1TUFyNIuV2WKFwoHIyR1nxLkFuL_5_Tv8Z4IJ3mCSljtPOPzp9HxnSOEmVj9lT0QqkSv1QQh_CK_CH9yIFZDF62oGDT_ZbywSmqUiwG2iZ5mRJ6Vcq4miOVYFSFG2lkzWdp2OLJR0E6K8ej_2cfddm8O7H-dZ6Q4ZNwBkicz6IIy8nUtXa78jR8O5iVyi72abPCFMDTT_0eZ2Bc1FWGAYS621KbC6v3p3YHFwarEcvX1SCf1avWZsGbzOsdhEbilAY9lzgSI8qbqn258bkGgIk5Lf-9AA0FpSBHY3CTL_aGde0riZVRvK8wjWlGvo5P0rcBl7KY6_2NpHeEqFDzX7NsxlaQrVNuN9Cf6jNhFVsrsNJ9yhtkDfmQQJf6eWHVTUk-3pEm7hXQiDbe0-Da_Va-1ZhowBVbsGQT-vN0sAP9vHjm0efz0PjH0nGl3CnS9ojIX-XL9cptqVB1IpTpw2Qpr1q8cK9vOpMn5pKZ4qntfUvvV3LMTuYLYjTKXUKIY78otg74_NLSpMIFodMj09ve4T6hP4k9MhP0cJmVqTn6ed0tP_XvAu4_IGArdwbOrDCuzwgunikQsCPICDQ1YanTYbEDiXJrNWfu9B_q4H-BUwX7gwaZOsvuo6wTDwOUjC7jkHWs9j1hiYtDzQEGKkkOxw3pEfGWEk6FLlgPZcEIDbVjGlYFTNMviju9K8xrhQxPptZUPvHRHI2Lj4_RFER8tmf9nJEQXDd7vo9ZIzGM_C8NPcP9KJW21sjxjxrx_Os-iGZeMfNbZtjM3OTtEgxrPVEsxxJEfNr7b5kbabAcWLT6tcjedCCH4YBbqdwIA8NAd9h_MnjlnAPlKSdQ2-8yYBTsyO0hZZR6uEQrSHZl_7Q5iCQEMMuCogL7LoxKkRjFrIH3m87PrjXHXLaS6ULAMy01_Sm9mURVD3EUyeSlTkISTL1Ug60Lqsc_TIjvWZdIFql3uU2bJph1n6TUgtHDmVHU6_)

### Описание компонентов

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