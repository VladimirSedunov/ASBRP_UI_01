<h1 align="center">Тестирование проекта "Корпоративная система Ресурсного и бюджетного планирования" - ERPLIGHT(ASBRP)</h1>
<hr>

## Проект автотестирования реализован с использованием
Python = Pytest = Allure Report = Jenkins = Telegram = Java = PosgreSQL

![](/design/icons/Python.png)&emsp;![](/design/icons/Pytest.png)&emsp;![](/design/icons/Allure_Report.png)&emsp;![](/design/icons/Jenkins.png)&emsp;
![](/design/icons/Telegram.png)&emsp;![](/design/icons/Java.png)&emsp;![ ](/design/icons/Postgresql.png)
<hr>

## Сценарии:

### Сценарий автотеста test_ASBRP_849
Представляет собой end-to-end (e2e) тест, состоящий из последовательности логически связанных шагов с наборами бизнес-операций, выполняемых от лица разных пользователей.

При падении на каком-либо шаге тест завершается, все остальные шаги не выполняются (реализовано с использованием @pytest.mark.dependency и os.environ['prev_test_ok']).
 
* Шаг 1. ASBRP-T1 (2.0) 01.Создание процесса в системе пользователем с ролью ИП (Пользователь 1).
* Шаг 2. ASBRP-T12 (1.0) 02.Редактирование процесса в системе и отправка его на согласование пользователем с ролью ИП (Пользователь 1).
* Шаг 3. ASBRP-T183 (1.0) 03.Согласование процесса пользователем с ролью ИП (Пользователь 2),связанным с ИП (Пользователь 1) по группе продукт-проект
* Шаг 4. ASBRP-T185 (1.0) 04.Согласование самим ИП, создавшим процесс в системе (Пользователь 1)
* Шаг 5. ASBRP-T184 (1.0) 05.Согласование процесса ЛПР (Пользователь 3).
* Шаг 6. ASBRP-T197 (1.0) 06.Согласование процесса ЛПР-2 (Пользователь 4).
* Шаг 7. ASBRP-T198 (1.0) 07.Запрос позиций активов ИП (Пользователь 1) и отправка их на согласование.
* Шаг 8. ASBRP-T199 (1.0) 08.Согласование позиций активов МА (Пользователь 2) и отправка.
* Шаг 9. ASBRP-T186 - 09. Редактирование ИП (Пользователь 1) позиций активов в процессе и отправка изменений на согласование.
* Шаг 10. ASBRP-T187 - 10.Согласование позиций активов ИП (Пользователь 1).
* Шаг 11. ASBRP-T188 (1.0) 11.Согласование позиций активов ЛПР (Пользователь 3).
* Шаг 12. ASBRP-T200 (1.0) 12.Согласование позиций активов МА (Пользователь 5).
* Шаг 13. ASBRP-T201 - 13.Согласование позиций активов МА (Пользователь 6).
* Шаг 14. ASBRP-T202 (1.0) 14.Согласование позиций активов ЛПР (Пользователь 4)
* Шаг 15. ASBRP-T203 (1.0) 15.Назначение активов МА (Пользователь 5). Для автотеста
* Шаг 16. ASBRP-T204 (1.0) 16.Назначение активов МА (Пользователь 6)
* Шаг 17. ASBRP-T205 (1.0) 17.Согласование активов ИП, создавшим процесс в системе (Пользователь 1)
* Шаг 18. ASBRP-T206 (1.0) 18.Согласование активов ИП-2 (Пользователь 2)
* Шаг 19. ASBRP-T207 (1.0) 19.Согласование активов МА (Пользователь 5)
* Шаг 20. ASBRP-T208 (1.0) 20.Согласование активов МА (Пользователь 6).
* Шаг 21. ASBRP-T209 (1.0) 21.Согласование активов ЛПР (Пользователь 3)
* Шаг 22. ASBRP-T210 (1.0) 22.Согласование активов ЛПР (Пользователь 4)
* Шаг 23. ASBRP-T190 (1.0) 23.Удаление процесса из списка процессов (смена статуса на Архив)


### Сценарии автотеста test_ASBRP_964

Различные варианты отклонения согласования процесса

* Тест 1. ASBRP-T193 Отклонение ЛПР согласования процесса по дате процесса (тестовый стенд).
* Тест 2. ASBRP-T194 (1.0) Отклонение ЛПР согласования процесса по позициям актива (тестовый стенд).
* Тест 3. ASBRP-T195 Отклонение ЛПР согласования процесса по активам (тестовый стенд).
* Тест 4. ASBRP-T213 0.0 Создание процесса в системе пользователем с ролью ИП (Пользователь 1), незаполненные обязательные поля "Наименование", "Проект-источник", "Продукт". Для автотеста
* Тест 5. ASBRP-T216 Отклонение согласования самим ИП, создавшим процесс в системе (Пользователь 1)
* Тест 6. ASBRP-T217 Отклонение согласования процесса пользователем с ролью ИП (Пользователь 2), связанным с ИП Пользователь 1 по группе продукт-проект.
* Тест 7. ASBRP-T218 Отклонение согласования процесса ЛПР (Пользователь 3)
* Тест 8. ASBRP-T219 Отклонение согласования процесса ЛПР-2 (Пользователь 4).
* Тест 9. ASBRP-T220 Отклонение согласования процесса ЛПР-2 (Пользователь 4) после согласования всеми участниками процесса.
* Тест 10. ASBRP-T221 Удаление несогласованного процесса из списка процессов (смена статуса на Архив)

<hr>

## Фрагменты кода

test_ASBRP_849

![](/design/images/code1.png)

![](/design/images/code2.png)

test_ASBRP_964

![](/design/images/code3.png)

## Запуск автотестов выполняется на сервере Jenkins

Командная строка:
pytest ${SELECT_TESTS} --browser=${browser} --browser_version=${browser_version} --window-size=${window_size}

### Параметры сборки

* SELECT_TESTS - Параметр определяет выбранную группу тестов.
* browser - Браузер chrome или firefox.
* browser_version - Версия браузера на Selenoid.
* window_size - Размер окна браузера.

![](/design/images/jenkins1.png)

### Результат запуска сборки можно посмотреть в отчёте Allure Report

![](/design/images/jenkins2.png)

<hr>

## Настроено автоматическое оповещение о результатах сборки Jenkins в Telegram-бот

![](/design/images/telegram_bot.png)

<hr>

## Видеопрезентация автотеста

Фрагмент презентации в формате GIF
![](https://github.com/VladimirSedunov/erplight_asbrp/blob/main/design/video/v01.gif)

Шестиминутная видеопрезентация размещена в папке design/video в файлах : 01.mp4, 02.mp4, 03.mp4, 04.mp4

<hr>

## _Примечание:_

Проект не может быть выложен на публичный ресурс по соображениям конфиденциальности.

