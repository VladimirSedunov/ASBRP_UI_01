# erplight-autotest

Проект ERPLIGHT(ASBRP)

ERPLight

Корпоративная система Ресурсного и бюджетного планирования

<h1 align="center">Проект по тестированию процесса получения и обработки поступающих сообщений в Систему персонифицированного учета (СПУ) из ГИС ЕЦП (Анкетная часть ВС1)</h1>
<hr>

## Проект реализован с использованием
Python = Pytest = Allure Report = Jenkins = Telegram = Java = IBM WAS = PosgreSQL = DB2 for z/OS

![](/design/icons/Python.png)&emsp;![](/design/icons/Pytest.png)&emsp;
![](/design/icons/Allure_Report.png)&emsp;![](/design/icons/Jenkins.png)&emsp;![](/design/icons/Telegram.png)&emsp;![](/design/icons/Java.png)&emsp;
![ ](/design/icons/was.png)&emsp;![ ](/design/icons/Postgresql.png)&emsp;![ ](/design/icons/db2.png)
<hr>

## Основной шаблон выполнения шагов тест-кейса:
* Подготовка Базы Данных (удаление сведений по ИЛС, записей о ЕЦП, задач в очереди на выполнение)
* Чтение файла JSON с анкетой и получение из него параметров теста
* Выполнение SQL-запроса INSERT для заполнения соответствующей таблицы ЕЦП
* Выполнение SQL-запроса INSERT для помещения задачи в очередь на выполнение
* Ожидание выполнения задачи подсистемой
* Проверка значений набора полей заданных таблиц
* Создание отчёта о расхождениях между ожидаемым и фактическим результатом
<hr>
 
## Файл КП для автотестов:
* /data/КП ЕЦП ВС1 Анкетная часть.xlsx

<hr>

## Запуск автотестов выполняется на сервере Jenkins

Командная строка:
pytest ${SELECT_TESTS} --bd_name=${bd_name}

### Параметры сборки

* SELECT_TESTS - Параметр определяет выбранную группу тестов.
* bd_name - База данных (тестовый стенд)

![](/design/images/jenkins1.png)

### Результат запуска сборки можно посмотреть в отчёте Allure Report

![](/design/images/jenkins2.png)

<hr>

## Настроено автоматическое оповещение о результатах сборки Jenkins в Telegram-бот

![](/design/images/telegram_bot.png)

<hr>

## _Примечание:_

Проект не может быть выложен на публичный ресурс по соображениям конфиденциальности.

