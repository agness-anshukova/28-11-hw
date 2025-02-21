# Домашнее задание к занятию "Базы данных, их типы" - `Аншукова Агния`


### Задание 1. СУБД

## Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для каждой предметной области. 
## Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему?


## 1.1.Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков. СУБД должна гарантировать целостность и чёткую структуру данных.

`Реляционная СУБД`

1. `Целостность данных (набор правил, поддерживающих непротиворечивое состояние базы) обеспечивается набором ограничений: 1) ограничения первичного (исключение дублей строк) и вторичного ключей (обеспечивает, что запись, на которую ссылается строка, существует в системе); 2) ограничения на столбцы (уникальность (ограничение дублей значений), not null, check)  `
2. `Язык манипулирования данными (sql) позволяет строить сложные запросы к базе данных, что позволит успешно решить задачу по построению аналитического отчета`
3. `Базовая структура - отношение. Отношение представлено таблицей. Отношение представляет модель описываемого явления или объекта. Столбцы - это существенные для моделируемого бизнес-процесса характеристики объекта или явления. Бюджетирование и финансовая аналитика - достаточно формализованные отрасли человеческой деятельности. Соответственно, данные, подвергающиеся сбору, анализу и обработке, находятся в четких взаимосвязях и обладают конкретным набором характеристик, делающих их пригодными для составления отчетности.`

`Базы данных NoSQL обычно основываются на денормализованных данных и поддерживают типы приложений, которые используют меньше таблиц (или контейнеров) и в которых отношения данных моделируются не с помощью ссылок, а как встроенные записи (или документы). Многие классические офисные бизнес-приложения в области финансов, бухгалтерского учета и планирования ресурсов предприятия используют высоконормализованные данные для предотвращения аномалий данных, а также дублирования данных. Это, как правило, те типы приложений, которые не подходят для баз данных NoSQL. Базы данных NoSQL обычно не поддерживают сложные сочленения, подзапросы и вложенные запросы в предложении WHERE`


## 1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? СУБД должны быть гибкими и быстрыми.

`Для лендингов используем базу данных NoSQL (документоориентированную БД).`

`Если исходим из того, что Лидом мы считаем тех пользователей, у которых выполнено хотя бы одно из условий:`
1. `определено имя`
2. `определен email` 
3. `определен телефон`
4. `определен user id` 
5. `пользователь хотя бы один раз общался с продавцом в диалогах`
`,то подходящей СУБД будет NoSQL. Наличие существенных характеристик покупателя важно при оформлении с ним сделки и выполнении обязательств, но не важно пока стороны не достигли согласия о вступлении в сделку.`
`Соответственно, в случае использования здесь реляционной модели придется регулярно решать проблемы с: отсутствием некоторых атрибутов, появлением характеристик, не учтенных при проектировании, дублированием информации, противоречивостью данных и т.п.` 
`В NoSQL-базах структура данных не регламентирована вообще или лишь в малой степени. Если нужно внести изменения в поля отдельного документа, для этого не потребуется декларативно менять всю структуру таблицы.` 
`Кроме того, NoSQL СУБД позволяют сгруппировать и хранить данные пообъектно, что сокращает время поиска информации о конкретном взаимодействии с пользователем.`

`Для CRM используем реляционную СУБД.`
`Если предполагается, что CRM выполняет следующие задачи:`

1. `Хранение данных о клиентах`
2. `Учет сделок и управление продажами`
3. `Управление задачами и учет рабочего времени`
4. `Аналитика и наглядные отчеты`
5. `Автоматизация бизнес-процессов`
6. `Запись клиентов на услуги`
7. `Постановка целей и KPI`
`то для нее более подходящей является реляционная модель данных, поскольку предоставляет жесткую структуру данных, механизм поддержки целостности данных, а также поддерживает сложные запросы, что существенно для аналитики. `


## 1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру

`Используем базу NoSQL вида “ключ-значение”. В таких БД для доступа к значению используется ключ. Они применяются в качестве хранилищ изображений, специализированных файловых систем, кэшей, информационных платформ для онлайн-игр и т.д. — везде, где главными требованиями являются высокая масштабируемость и минимальная задержка обработки запроса.`


## 1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать со связями.

`Используем “графовую” базу NoSQL.` 
`Графовые. Такие БД сохраняют информацию в виде сложно связанных друг с другом графов. Связанность данных упрощает их хранение, навигацию и поиск.`



### Задание 2. Транзакции

## Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы транзакция завершилась успешно. Ориентируйтесь на шесть действий.

1. `аутентификация и авторизация в личном кабинете`
2. `валидация формата номера телефона (соответствует маске ввода)`
3. `установление оператора связи`
4. `проверка наличия возможности проведения расчетов с данным оператором`
5. `существование абонента с таким номером`
6. `наличие достаточной суммы не счету пользователя`
7. `подтверждение пользователем намерения провести данную операцию`
8. `подтверждение оператором связи зачисления указанной суммы на счет абонента, указанного пользователем`


### Задание 3. SQL vs NoSQL

## Напишите пять преимуществ SQL-систем по отношению к NoSQL.

1. `у  SQL-систем есть механизмы поддержки целостности данных`
2. `у  SQL-систем есть удобный язык манипулирования данными. Он основан на алгоритмах реляционной алгебры и четкой математической структуре, что обеспечивает простоту и эффективность при оптимизации любых запросов к базе данных`
3. `таблицы являются ключевым преимуществом реляционных баз данных, так как обеспечивают интуитивно понятный, эффективный и гибкий способ хранения структурированной информации и получения к ней доступа`
4. `в реляционных базах данных используются очень детальные и строгие бизнес-правила и политики в отношении фиксации изменений в базе данных (то есть сохранения изменений в данных на постоянной основе). Транзакции реляционных баз данных определяются четырьмя основными свойствами: атомарность, согласованность, изоляция и долговечность`
5. `при решении задач, в которых имеются жесткие требования к качеству и структуре данных, в т.ч. и с точки зрения законодательства (бухгалтерский и налоговый учет, кадровый учет, деятельность кредитных и финансовых организаций и проч.), реляционная модель за счет жесткой структуры позволяет “отфильтровать”, не подходящие данные` 


### Задание 4.Кластеры

## Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу выделено 1000 машин.
## На основе какого критерия будете выбирать тип СУБД и какая модель распределённых вычислений здесь справится лучше всего и почему?

`Базы данных NoSQL основываются на процессе шардинга, чтобы обеспечить горизонтальное масштабирование, соответственно, можно добавить больше машин для обработки данных на нескольких серверах. Характер горизонтального масштабирования баз данных NoSQL позволяет обрабатывать большие объемы данных (даже по мере их роста) более эффективным способом. При вертикальном масштабировании, применяемом в других базах данных SQL, в существующую машину требуется добавлять дополнительную мощность и память, а это может сказаться на стабильности, поскольку требуется все больший и больший объем хранилища.`
