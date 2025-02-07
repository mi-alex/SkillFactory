# Проект 2. Анализ вакансий из HeadHunter (SQL)

## Оглавление  
[1. Описание проекта](./README.md#Описание-проекта)  
[2. Какой кейс решаем?](./README.md#Какой-кейс-решаем)  
[3. Краткая информация о данных](./README.md#Краткая-информация-о-данных)  
[4. Этапы работы над проектом](./README.md#Этапы-работы-над-проектом)  
[5. Выводы](./README.md#Выводы) 

### Описание проекта    
В нашем распоряжении имеется SQL-база вакансий, выгруженная с сайта поиска вакансий hh.ru. В данном проекте мы изучаем данные о вакансиях с помощью SQL-запросов, вызываемых непосредственно из Python. 

:arrow_up:[к оглавлению](./README.md#Оглавление)

### Какой кейс решаем?    
Целью проекта является анализ вакансий в разрезе работодателей, предметных областей и регионов.

:arrow_up:[к оглавлению](./README.md#Оглавление)

### Краткая информация о данных
Структура базы данных представлена на диаграмме:

<center><img src = data/data_structure_sql.png alt="drawing" style="width:400px;"></center>

**VACANCIES**

Таблица хранит в себе данные по вакансиям и содержит следующие столбцы:

<center><img src = data/vacancies.png alt="drawing" style="width:400px;"></center>

Зарплатная вилка — это верхняя и нижняя граница оплаты труда в рублях (зарплаты в других валютах уже переведены в рубли). Соискателям она показывает, в каком диапазоне компания готова платить сотруднику на этой должности.

**AREAS**

Таблица-справочник, которая хранит код региона и его название.

<center><img src = data/areas.png alt="drawing" style="width:400px;"></center>

**EMPLOYERS**

Таблица-справочник со списком работодателей.

<center><img src = data/employers.png alt="drawing" style="width:400px;"></center>

**INDUSTRIES**

Таблица-справочник вариантов сфер деятельности работодателей.

<center><img src = data/industries.png alt="drawing" style="width:400px;"></center>

**EMPLOYERS_INDUSTRIES**

Дополнительная таблица, которая существует для организации связи между работодателями и сферами их деятельности.

<center><img src = data/employers_industries.png alt="drawing" style="width:400px;"></center>

Эта таблица нужна нам, поскольку у одного работодателя может быть несколько сфер деятельности (или работодатели могут вовсе не указать их). Для удобства анализа необходимо хранить запись по каждой сфере каждого работодателя в отдельной строке таблицы.

:arrow_up:[к оглавлению](./README.md#Оглавление)

### Этапы работы над проектом  
1. Знакомство с данными
2. Предварительный анализ данных
3. Детальный анализ вакансий
4. Анализ работодателей
5. Предметный анализ

:arrow_up:[к оглавлению](./README.md#Оглавление)

### Выводы
В результате работы над проектом установлено, что:
* Нам предоставлена выборка из около 50000 вакансий
* Крупнейшим работодателем (и по числу вакансий, и в разрезе регионов) является Яндекс (по всей видимости, к вакансиям Яндекса относятся и вакансии в его дочерних проектах, таких как такси, еда, доставка и др.)
* Почти 2000 вакансий так или иначе относятся к работе с данными, около 500 относятся к Data Science
* Начальная зарплата для специалистов DS находится на уровне нижней границы среднего диапазона зарплат по выборке в целом (чуть более 70000 рублей), однако зарплата опытных специалистов DS более чем вдвое превосходит среднюю зарплату по выборке в целом (свыше 240000 рублей)
* Справочник регионов устроен неоптимально, в нём смешаны страны, регионы и города. Для дальнейшего анализа было бы полезно преобразовать его в иерархический или разделить на три отдельных справочника.
* В дальнейшем было бы интересно изучить, какие навыки вообще требуются для специалистов DS
* Можно посмотреть, как различаются требуемые навыки в зависимости от уровня опыта

:arrow_up:[к оглавлению](./README.md#Оглавление)

Если информация по этому проекту покажется вам интересной или полезной, то я буду очень вам благодарен, если отметите репозиторий и профиль ⭐️⭐️⭐️-дами