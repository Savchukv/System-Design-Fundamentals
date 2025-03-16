# System Design Fundamentals
База знаний по системной дизайну. Поможет подготовиться к собеседованию и освежить знания.

### Для чего это?
Собеседования в формате System Design Interview становятся все популярнее. Эти собеседования по проектированию проводят как для инженеров, так и для технических менеджеров, а их результаты влияют на оценку итогового уровня кандидата. Практически во всех компаниях BigTech сейчас есть такой этап.

### Что это такое вообще?
System design (дизайн системы) — это процесс разработки и планирования архитектуры, компонентов, модулей и интерфейсов для создания сложных программных, аппаратных или информационных систем.
Этот процесс обычно осуществляется в начале разработки проекта и направлен на определение того, как система будет функционировать в целом, как её компоненты будут взаимодействовать, какие технологии и архитектурные решения следует использовать, чтобы достичь требуемой функциональности, производительности, масштабируемости и надёжности.

### План собеседования
System Design Interview длится обычно 1 час. Основной целью системного дизайна является создание эффективной и устойчивой системы, которая будет соответствовать требованиям пользователей, а также удовлетворять ограничениям, связанным с доступностью ресурсов и техническими ограничениями. В процессе системного дизайна участвуют специалисты по различным областям, включая архитекторов, инженеров по разработке, специалистов по безопасности и других. 
1. Понять поставленную задачу, определить границы проектируемой системы. Примерно 5-10 минут.
2. Построить высокоуровневую дизайн систему. Примерно 20 минут.
3. Погрузиться в детали. Примерно 25 минут.
4. Обсудить вопросы. Примерно 5 минут.

**Важное замечание**

Постоянно общайтесь с ревьювером. Задавайте уточняющие вопросы, в ту ли стороны вы идите и это то, что он хочет услышать от вас. Спросите, нужно ли углубиться в конкретную деталь, потому что времени на все не хватит и возможно ревьюверу будет интересно обсудить что-то конкретное. Не пытайтесь умолчать, если видите какой-то корнер кейс. Вы можете сказать, что сходу не можете сейчас ответить и готовы вернуться позже, при этом выписав этот вопрос отдельно. Это покажет вас с хорошей стороны, что вы на такие вещи обращаете внимание. 
Думайте и обсуждайте не только про happy path вашей системы, но и bad path, то есть что делать в случае ошибок. 

### Структура рассказа
1. Требования. В первую очередь необходимо выяснить функциональные/нефункциональные требования. Кто является пользователем системы, основные продуктовые/технические метрики, масштабируемость, безопасность и т.п.
   * **Функциональные требования** - каковы функции системы? Насколько она должна быть надёжной? Будет ли аналитика? Online first ли подход? Нужно ли хранить информацию? и т.д.
   * **Нефункциональные требования** - производительность (тут можно задать вопрос о выборе БД). Безопасность (тут можно задать вопрос о cloudflare, например, чтобы блокировать DDOS по IP). Скорость (включить ли сервис кеша). Есть ли фото/видео (кол-во серверов и кол-во ssd, и CDN для этого).
   * **Продуктовые метрики** - Как часто пользователь заходит на страницу продукта, как долго прибывает там, какие разделы чаще открывает и т.д.
   * **Технические метрики** - Допустимое/недопустимое время простоя, сервис логов (grafana, sentry) и т.д.
  
2. Построение архитектуры. Архитектура определяет структуру системы, ее компоненты и взаимодействие между ними. Это может быть представлено в виде блок-схемы, диаграммы классов или других моделей. Советую использовать модель [С4](https://habr.com/ru/articles/778726/). Внизу приведены примеры таких систем.

### Полезные ресурсы для подготовки
1. https://habr.com/ru/companies/avito/articles/753248
2. https://themobileinterview.com/cracking-the-mobile-system-design-interview
3. https://apptractor.ru/info/articles/chto-takoe-system-design.html
4. https://github.com/weeeBox/mobile-system-design
5. https://habr.com/ru/articles/781404
6. https://tellmeabout.tech/software-design-books-743be52e4c71
7. https://habr.com/ru/articles/853652/
8. https://www.youtube.com/watch?v=jUbOm0B-eKQ
9. https://www.youtube.com/watch?v=8dG0qzNAVXI
10. Мок собеседование - https://www.youtube.com/watch?v=9_8ShTF6aQA
11. Мок собеседование - https://www.youtube.com/watch?v=Wh5Ya6UFG1k
12. Мок собеседование - https://www.youtube.com/watch?v=_K-eupuDVEc

### База
### Балансировка нагрузки
Это метод равномерного распределения сетевого трафика по пулу ресурсов, поддерживающих приложение. Современные приложения должны обрабатывать миллионы пользователей одновременно, а также быстро и надежно возвращать каждому пользователю правильный текст, видео, изображения и другие данные. Для обработки таких значительных объемов трафика в большинстве приложений используется множество серверов ресурсов с дублированием данных между ними.

Балансировщик нагрузки – это устройство, которое находится между пользователем и группой серверов и действует как невидимый посредник, обеспечивая одинаковое использование всех серверов ресурсов.

Балансировка нагрузки направляет и контролирует интернет-трафик между серверами приложений и их посетителями или клиентами. В результате повышается доступность, масштабируемость, безопасность и производительность приложения.

### CDN (Content Delivery Network)
Это географически распределённая сетевая инфраструктура, обеспечивающая быструю доставку контента пользователям веб-сервисов и сайтов. Входящие в состав CDN cерверы географически располагаются таким образом, чтобы сделать время ответа для пользователей сайта/сервиса минимальным.
При использовании CDN всё происходит по-другому: пользователь из Владивостока переадресуется к географически ближайшему кэширующему серверу в составе CDN, благодаря чему доставка статического контента происходит гораздо быстрее.

### API Gateway
Это служба для управления запросами к API веб-сервисов и приложений. Шлюз служит посредником между пользователем и онлайн-сервисами, предоставляя единую точку входа и направляя запросы от клиентов туда, куда нужно.
Он может выполнять различные задачи, такие как аутентификация, авторизация, лимитирование, кеширование данных.

**Причины использования:**
1. Централизованное управление: предоставляет единую точку входа для всех запросов клиентов. Это позволяет упростить управление, маршрутизацию и мониторинг.
2. Безопасность: API Gateway обеспечивает уровень безопасности между клиентами и вашими службами. Он может выполнять аутентификацию и авторизацию, защищая ваши данные от несанкционированного доступа.
3. Контроль нагрузки: может ограничивать количество вызовов от каждого клиента, чтобы предотвратить перегрузку ваших служб и обеспечить стабильную производительность.
4. Трансформация данных: может преобразовывать данные из одного формата в другой, что облегчает интеграцию с различными клиентами, использующими разные форматы данных.
5. Мониторинг и аналитика: предоставляет возможности мониторинга и аналитики для отслеживания использования ресурсов, производительности и других метрик вашего сервиса.

### Передача данных
1. TCP/IP - IP отвечает за передачу пакетов данных между компами, а TCP - за установление соединения между узлами.
2. HTTP - протокол для получения ресурсов, например, HTML-документов. Он лежит в основе обмена данными в Интернете и является протоколом клиент-серверного взаимодействия, что означает инициирование запросов к серверу самим получателем, обычно веб-браузером (передается строка, заголовок, тело, а сервер отдает ответ).
3. DNS - Domain Name System, система доменных имен. Это система, которая связывает между собой доменное имя сайта, то есть его название, и IP-адрес — он нужен для «общения» компьютеров по сети. Благодаря DNS-серверу вам не нужно знать IP-адрес сайта, чтобы попасть на него.
4. gRPC — это абстрактная спецификация. Она описывает абстрактную RPC (remote procedure call), то есть удаленный вызов процедуры, которая обладает определенными свойствами. Первое свойство — поддержка как одиночных вызовов, так и стриминга. То есть все сервисы, которые реализовывают эту спецификацию, поддерживают оба варианта. Следующий пункт — наличие метаданных, то есть чтобы вместе с полезной нагрузкой вы могли бы передать какие-то метаданные — условно, заголовки. И — поддержка отмены запроса и таймаутов из коробки.
5. REST - Representational State Transfer означает передачу состояния представления и описывает способ получать и модифицировать данные удаленных приложений с помощью протокола HTTP. REST достаточно легко внедряется и обеспечивает кросс-платформенную переносимость любых API. Для разработки веб служб и API. Поддерживает CRUD-операции и обмен сообщениями без сохранения состояния на бекенде. Каждое сообщение самодостаточное и содержит всю информацию, необходимую для его обработки.
6. WebSocket - двунаправленное соединение в режиме реального времени (Мы подключаем WS один раз, а затем сервер может отдавать нам ответы тогда, когда посчитает нужным).  А как сервер узнает, что мы до сих пор подключены?
* Ответ на данный вопрос достаточно легкий — сервер и клиент играют в пинг-понг.
* Сервер периодически присылает ответ по WS с просьбой о действии - послать запрос на сервер. Если клиент отвечает до истечения тайм-аута — он подключен, если нет, то происходит разрыв соединения до следующего рукопожатия👋
7. Long Polling - старая технология (на смену пришел WebSocket), грязный хак предотвратить создание нового соединения на каждый новый запрос.
8. Очереди сообщений - асинхронный обмен сообщениями между сервисами (RabbitMQ, Kafka).
9. GraphQL - язык запросов API, определяющий спецификации, по которым клиентское приложение должно запрашивать данные с удаленного сервера. В качестве альтернативы REST GraphQL позволяет разработчикам делать запросы на извлечение данных из нескольких источников данных с помощью одного вызова API.

### БД
**Реляционные vs нерялиционные БД**
Термин «реляционный» пришел из алгебры (теория множеств). В формате БД это значит, что данные реляционных баз хранятся в виде таблиц и строк. Нереляционные БД размещают информацию в документах, ключ-значение, JSON.

**Масштабируемость БД**

В большинстве случаев базы данных SQL можно масштабировать по вертикали. Что это значит? Можно увеличить нагрузку на один сервер, увеличив таким образом ЦП, ОЗУ или объем накопителя.
В отличие от SQL базы данных NoSQL масштабируются по горизонтали. Это означает, что больший трафик обрабатывается путем разделения или добавления большего количества серверов. Это делает NoSQL удобнее при работе с большими или меняющимися наборами данных.

Минусы масштабирования:
* Вы можете добавлять к своему серверу дополнительные ресурсы процессора, памяти и т. д., но аппаратные ограничения игнорировать не получится. Если у вас много пользователей, одного сервера будет недостаточно.
* Повышенный риск возникновения единой точки отказа.
* Вертикальное масштабирование имеет высокую общую стоимость. Мощные серверы очень дорогие.

**Недостатки реляционной базы данных**
* Сложность в проектировании
* Цена
* Не лучшее решение для хранения фото/видео
* Ограничение в производительности

**Преимущества реляционной базы данных**
* Согласованность и точность данных
* Целостность и безопасность данных
* Гибкость и масштабируемость
* Простота извлечения данных и манипулирования ими
* Простота запросов к данным и составления отчетов

**Преимущества нереляционной базы данных**

Если объем данных большой, лучше использовать NoSQL. Отсутствие явных структурированных механизмов ускорит процесс обработки Big Data. А еще это безопаснее — такие БД сложнее взломать.
Данные хранятся в документах, ключ-значение, JSON.
Выбирайте NoSQL, если:
* Необходимо хранить массивы в объектах JSON
* Вам нужно лишь сериализовать и десериализовать свои данные (JSON, XML, YAML и т. д.)
* Записи хранятся в коллекции с разными полями или атрибутами
* Необходимо горизонтальное масштабирование
* Так как неструктуированная БД - то более эффективное работать с большим объемом данных
* Меньше затрат на оборудование, чем в SQL

**Недостатки нереляционной базы данных**
* Не поддерживают полноценные транзакции, что может привести к проблемам с целостностью данных
* Ограниченная поддержка языка запросов
* Не лучшее решение для хранения фото/видео
* Ограничение в производительности

**БД ClickHouse**

Cтолбцовая система управления базами данных (СУБД) для онлайн-обработки аналитических запросов (OLAP).  

Позволяет создавать таблицы и базы данных во время выполнения (runtime), загружать данные и выполнять запросы без переконфигурирования и перезапуска сервера.

Колоночная база данных — это такой тип базы данных, в которой данные группируются (хранятся и извлекаются) не по строкам, а по столбцам. В традиционной строчной базе данных данные хранятся и извлекаются по строкам, что означает, что все столбцы строки должны храниться вместе.  При этом каждая колонка – это отдельная таблица.
Колоночные БД удобны для работы с большими объемами данных и отлично подходят для аналитических задач. 

Колоночные СУБД призваны решить проблему неэффективной работы традиционных СУБД в аналитических системах и системах в подавляющим большинством операций типа «чтение». Они позволяют на более дешевом и маломощном оборудовании получить прирост скорости выполнения запросов в 5, 10 и иногда даже в 100 раз, при этом, благодаря компрессии, данные будут занимать на диске в 5-10 раз меньше, чем в случае с традиционными СУБД.

У колоночных СУБД есть и недостатки — они медленно работают на запись, не подходят для транзакционных систем и как правило, ввиду «молодости» имеют ряд ограничений для разработчика, привыкшего к развитым традиционным СУБД.

**DWH**

Базы данных используются для записи и извлечения информации, а DWH — это централизованное место анализа структурированных данных для конкретных целей, связанных с бизнес-аналитикой. Можно посмотреть на это так: хранилища содержат информацию из нескольких баз данных.

В Data Lake собираются данные из различных источников, независимо от того, структурированы они или нет. Это позволяет использовать данные для искусственного интеллекта и машинного обучения. Это позволяет обрабатывать разнообразные типы данных, такие как текст, изображения, аудио и видео.

OLTP или обработка транзакций в реальном времени — это тип обработки данных, который заключается в одновременном выполнении нескольких транзакций, таких как интернет-банкинг, покупки, ввод заказов или отправка текстовых сообщений

**Cassandra БД**

Хранит данные в виде хранилищ ключей и значений. Сервис позволяет определять таблицы со строками и столбцами, но табличная структура не используется в реальном хранилище. Вместо этого используется модель базы данных, ориентированная на широкий столбец, поэтому каждая строка таблицы может содержать свой набор столбцов.

**MongoDB**

Хранит данные без схемы, используя оптимизированный формат Binary JSON (BSON). Сервис может хранить несколько типов данных в одном документе, аналогично объектам JSON, а затем сериализовать их с помощью BSON. Работа с индексами более масштабнее сделана, чем в Касандре.

**Redis** 

Это база данных, размещаемая в памяти, которая используется, в основном, в роли кеша, находящегося перед другой, «настоящей» базой данных, вроде MySQL или PostgreSQL. Кеш, основанный на Redis, помогает улучшить производительность приложений. Он эффективно использует скорость работы с данными, характерную для памяти, и смягчает нагрузку центральной базы данных приложения, связанную с обработкой следующих данных:
* Данные, которые редко меняются, к которым часто обращается приложение.
* Данные, не относящиеся к критически важным, которые часто меняются.

**Кеш**

Это участок памяти, в который временно записываются результаты ресурсоемких ответов или данных, к которым часто обращаются. Это позволяет ускорить обслуживание последующих запросов.

При каждой загрузке новой веб-страницы, к примеру, выполняется один или несколько запросов к БД для извлечения данных. Многократное обращение к базе данных существенно влияет на производительность. Кэш может смягчить эту проблему. 

Получив запрос, веб-сервер сначала проверяет наличие ответа в кэше. Если ответ есть, данные возвращаются клиенту. Если нет, то веб-сервер обращается к базе данных, сохраняет ответ в кэше и пересылает его обратно клиенту. Эта стратегия называется кэшем сквозного чтения.

Вот несколько соображений касательно использования систем кеширования:

* Определитесь с тем, когда будет использоваться кэш. Это лучше делать в ситуациях, когда чтение данных происходит часто, а изменение — редко. Поскольку кэшированные данные хранятся в энергозависимой памяти, сервер кеширования не подходит для постоянного хранения. Например, если он перезапустится, все данные, хранившиеся в памяти, будут утрачены. В связи с этим данные необходимо записывать в постоянные хранилища.
* Выбор срока действия. Рекомендуется реализовать механизм, ограничивающий срок действия кэша. Просроченные данные не- медленно удаляются. Если такого механизма нет, данные будут храниться в памяти постоянно. Срок действия лучше не делать слишком коротким, иначе система будет слишком часто обнов- лять данные, загружая их из БД. С другой стороны, из-за слишком длинного срока действия данные могут оказаться неактуальными.
* Согласованность. Это подразумевает синхронизацию данных в хранилище и кэше. Несогласованность может возникнуть из-за того, что операции изменения данных в хранилище и кэше выполняются не за одну транзакцию. При масштабировании системы в пределах нескольких регионов может быть непросто поддерживать согласованность.
* Предотвращение сбоев. Наличие лишь одного сервера кэширования может оказаться потенциальной единой точкой отказа (single point of failure, SPOF), которая имеет следующее определение: «Единая точка отказа — это компонент, выход из строя которого приводит к прекращению работы всей системы». В связи с этим, чтобы избежать SPOF, рекомендуется использовать несколько серверов кэширования, размещенных в разных центрах обработки данных (ЦОД). А еще можно выделить какой-нибудь дополнительный объем памяти - это создаст буфер на случай, если память начнет использоваться более активно.
* Политика вытеснения. Когда кэш полностью заполнен, любой запрос на добавление новых элементов может привести к удалению существующих. Это называют вытеснением кэша. Самой популярной политикой считается вытеснение давно неиспользуемых данных (least-recently-used, LRU). Для разных ситуаций могут также подойти вытеснение наименее часто используемых данных (least-frequently-used, LFU) или метод «первым пришел, первым ушел» (FIFO, first-in-first-out).

**Шардинг**

Механизм, при котором данные разбиваются на несколько фрагментов и их можно хранить на разных серверах для распределения нагрузки.

Каждый шар имеет уникальный id, по которому можно быстро найти данные. Шары могут разбиваться по критериям - по географии, id юзеров и так далее.

**Репликация БД**

Это процесс, под которым понимается копирование данных из одного источника на другой (или на множество других) и наоборот. При репликации изменения, сделанные в одной копии объекта, могут быть распространены в другие копии.

Репликация баз данных может использоваться во многих СУБД, обычно в режиме “ведущий–ведомый”, где роль ведущего сервера играет оригинал (master), а его копии являются ведомыми (slave).

Ведущая база данных обычно поддерживает только операции записи. Ведомые БД получают от ведущей копии ее содержимого и поддерживают только операции чтения. Все команды для модификации данных, такие как вставка, удаление или обновление, должны направляться ведущей базе данных. В большинстве приложений чтение происходит намного чаще, чем запись, поэтому ведомых БД обычно больше, чем ведущих. 

Преимущества репликации базы данных - повышенная производительность. В модели «ведущий–ведомый» все операции записи и обновления происходят на ведущих узлах, а операции чтения распределяются между ведомыми. Это улучшает производительность, увеличивая количество запросов, которые можно обрабатывать параллельно.

### Очереди и брокеры сообщений
**Очередь сообщений**

Это форма асинхронной коммуникации между сервисами. Очереди предоставляют буфер для временного хранения сообщений и конечные точки, которые позволяют подключаться к очереди для отправки и получения сообщений в асинхронном режиме.

В сообщениях могут содержаться запросы, ответы, ошибки и иные данные, передаваемые между программными компонентами. Компонент, называемый производителем (Producer), добавляет сообщение в очередь, где оно будет храниться, пока другой компонент, называемый потребителем (Consumer), не извлечет сообщение и не выполнит с ним необходимую операцию.

**Брокер сообщений**

Это программное обеспечение и определённый архитектурный паттерн, который позволяет выстроить действия в информационных системах таким образом, чтобы обеспечить асинхронный обмен сообщениями между сервисами. Сервис, отправляющий данные, называется продюсер (producer), а потребляющий — потребитель (consumer).

Задачи брокера (т.е. выступает в качестве посредника):

* Получить сообщение от сервиса.
* Обеспечить маршрутизацию, управление очередями.
* Гарантировать доставку сообщения потребителю.

Самыми популярными брокерами сообщений являются RabbitMQ и Apache Kafka.

**Apache Kafka**

Cчитается распределённым брокером сообщений. Работает по модели pull - получатели сами достают сообщения из топика (как вайлдберис пункт выдачи - приди и забери).

**Принцип работы:**
* Kafka собирает у приложений данные и распределяет их по топикам в своём хранилище
* Информацию из топиков читают другие программы и микросервисы
* В отличие от RabbitMQ, Kafka не отслеживает, получил ли подписчик сообщение, платформа просто хранит его в течение установленного промежутка времени. При этом она гарантирует, что сообщения находятся в той же последовательности, в которой поступили
* Подписчики сами отправляют Kafka запросы о новых сообщениях и указывают, что им нужно прочитать

Основное назначение Apache Kafka — централизованный сбор, обработка, безопасное хранение и передача сообщений от разных сервисов. Обычно систему выбирают, когда нужно работать с большим количеством неструктурированных данных.
Где может применяться: системы аналитики, финансовые системы, социальные сети, онлайн-игры. Обработка потоков данных в реальном времени. То есть работа с данными ровно в тот момент, когда они появились или поступили, практически без задержки. Например, в финансовой сфере Kafka может использоваться для отображения и анализа цен акций и изменений рынка.  В отличие от большинства систем, очередь сообщений в Kafka является постоянной. Отправленные данные хранятся до тех пор, пока не истечет указанные период. Сообщения не удаляются после получения, их можно перечитывать.

Рассмотрим, как работает брокер сообщений Apache Kafka, на примере интернет-магазина с функциями поиска товара, оформления заказа, отправки клиентам уведомлений, которые соединены Apache Kafka:

Когда в системе появляется новый товар, сервис отправки уведомлений обращается к Apache Kafka и отправляет об этом сообщение в тему «Новые товары». Сервис оформления заказа и сервис поиска товаров подписаны на эту тему, поэтому сразу получают это сообщение и добавляют новый товар к себе.
Когда клиент что-то покупает, сервис оформления заказа отправляет сообщение в тему «Новые заказы». И уведомление о нём получат все, кто подписан на эту тему.
Весь этот обмен происходит в реальном времени — сервисы постоянно «заглядывают» в нужные темы и мгновенно получают оттуда сообщения. То есть если заказали последний товар, Kafka сразу об этом сообщит.

**RabbitMQ**

Распределённый горизонтально масштабируемый брокер сообщений. Работает по модели push - когда сообщения отправляются получателям (как курьер).

Он передаёт сообщения между поставщиками и подписчиками через очереди. Фишка RabbitMQ как раз в гибкой маршрутизации — одно и то же сообщение могут получить сразу несколько подписчиков.
Где может применяться: системы бронирования билетов, логистические программы.
В RabbitMQ сообщение хранится до тех пор, пока принимающее приложение не получит его из очереди. Как только подписчик отмечает, что сообщение получено, оно удаляется.

**Принцип работы:**
* RabbitMQ принимает сообщения от поставщиков, отправляет подтверждение о приёме и перенаправляет сообщение получателям
* Получатели подтверждают, что сообщение доставлено, или сигнализируют о неудачной доставке. Во втором случае сообщение остаётся в очереди до тех пор, пока не будет доставлено
* После доставки сообщение удаляется из системы

**Разница брокеров**

RabbitMQ поддерживает несколько стандартизированных протоколов: AMQP, MQTT, STOMP и др. Это позволяет заменить его на любой брокер на основе AMQP.
Kafka использует пользовательский протокол поверх TCP/IP для связи между приложениями и кластером. Вы не сможете так просто удалить или заменить эту платформу, потому что она единственная реализует данный протокол. 

Kafka подходит для горизонтального масштабирования путём добавления большего количества машин. RabbitMQ в основном предназначается для вертикального масштабирования путём увеличения мощности.

### Монолит и микросервисная архитектура
**Монолит**

**Достоинства**

Большим преимуществом монолита является то, что его легче реализовать. В монолитной архитектуре вы можете быстро начать реализовывать свою бизнес логику, вместо того чтобы тратить время на размышления о межпроцессном взаимодействие.
Еще одна вещь — это сквозные (E2E) тесты. В монолитной архитектуре их легче выполнить.
Говоря об операциях, важно сказать, что монолит прост в развертывании и легко масштабируется

**Недостатки**

Монолиты, как правило, перерождаются из своего чистого состояния в так называемый «большой шарик грязи». Вкратце, это описывается как состояние, возникшее, потому что архитектурные правила были нарушены и со временем компоненты срослись.
Это перерождение замедляет процесс разработки: каждую будущую функцию будет сложнее развивать. Из-за того что компоненты растут вместе, их также необходимо менять вместе. Создание новой функции может означать прикосновение к 5 различным местам: 5 мест, в которых вам нужно написать тесты; 5 мест, которые могут иметь нежелательные побочные эффекты для существующих функций.

**Микросервисы** 

**Достоинства**

Микросервисы легче держать модульными. Технически это обеспечивается жесткими границами между отдельными сервисами.
В больших компаниях разные сервисы могут принадлежать разным командам. Услуги могут быть повторно использованы всей компанией. Это также позволяет командам работать над услугами в основном самостоятельно. Нет необходимости координировать развертывание между командами. Развивать сервисы лучше с увеличением количества команд.
Микросервисы меньше, и благодаря этому их легче понять и проверить.

**Недостатки**

Распределенная система имеет свою сложность: в ней вам приходится иметь дело с частичным отказом, более затруднительным взаимодействием при тестировании (тесты E2E), а также с более высокой сложностью при реализации взаимодействия между сервисами.
Транзакции легче проводить в монолите. Решением этой проблемы на микросервисах является Saga Pattern. Хорошее решение, но все же слишком громоздкое для реализации на практике.
Существуют эксплуатационные накладные расходы, а множество микросервисов сложнее в эксплуатации, чем несколько экземпляров сигнального монолита. 

**Паттерны**

**Сага паттерн** - представляет собой набор локальных транзакций. Каждая локальная транзакция обновляет базу данных и публикует сообщение или событие, инициируя следующую локальную транзакцию в саге. Если транзакция завершилась неудачей, например, из-за нарушения бизнес правил, тогда сага запускает компенсирующие транзакции, которые откатывают изменения, сделанные предшествующими локальными транзакциями. 

Существует два способа координации саг:

* Хореография (Choreography) — каждая транзакция публикует события, которые запускают транзакции в других сервисах.
* Оркестровка (Orchestration) — оркестратор говорит участникам, какие транзакции должны быть запущены.

**Circuit Breaker паттерн** - предотвращает повторные вызовы к неисправной службе, временно блокируя запросы при превышении порога сбоя. Он позволяет службе изящно обрабатывать сбои и предотвращать каскадные сбои в распределённых системах. Подходит для изоляции сбоев.

**Retry паттерн** - позволяет приложению автоматически повторять неудавшиеся операции в надежде на успех при последующих попытках. Этот шаблон полезен в сценариях, где ожидаются временные сбои, например, проблемы с сетью или временная недоступность службы. Подходит для обработки временных сбоев.

**CQRS (Command Query Responsibility Segregation) паттерн** - это архитектурный паттерн, который предлагает разделить операции записи и чтения данных в приложении на две отдельные ветки. Вместо того, чтобы использовать единый интерфейс для обеих операций, CQRS предлагает использовать различные модели данных для команд и запросов. Это позволяет оптимизировать каждую модель для конкретных задач и улучшить производительность приложения.

Применение CQRS может быть особенно полезным в системах с большим количеством операций записи или при необходимости распределенной обработки запросов. CQRS также может облегчить сопровождение приложения, так как изменения в одной части системы не будут влиять на другие части.

### Теоремы

**CAP теорема**

Согласно CAP теореме, распределённые системы имеют 3 основных состояния:
* С (Consistency) консистентность - все узлы системы работают с одинаковым набором данных. Это означает, что пользователь системы может читать или записывать на любой узел и получит одни и те же данные.
* A (Availability) доступность - любой звапрос на рабочий узел будет обработан. Это означает, что даже в случае отказа одного и более узлов система должна продолжать обрабатывать запросы.
* P (Partition tolerancy) устойчивость к распределению - в данном случае мы говорим о ситуации, когда рабочие узлы не могут общаться между собой из-за проблем с соединением. Устойчивая к распределению система должна продолжать работу даже в этом случае. Разумеется, кроме случая полного отказа сети. Данные должны быть реплицированы между наборами узлов и сетей для их работы в периоды проблем с соединением.

В любой реализации распределённых вычислений возможно обеспечить не более двух из трёх следующих свойств - то есть мы можем создать систему, которая будет AP, CP или CA.

**PACELC теорема**

* PACELC является расширением теоремы CAP. Она утвержает, что в случае разделения сети (P) в распределной компьютерной системе нужно выбирать между доступностью (А) и согласованностью (С) (как в теореме CAP), а в остальных случаях (E), даже когда система работает нормально без разделений, нужно выбирать между задержкой (L) и согласованностью (С).
* Теорема утверждает, что в распределённой системе можно обеспечить любые два из трёх свойств доступности, согласованности и устойчивости к разделению (PAC) одновременно, но нельзя обеспечить все три свойства одновременно. Это связано с тем, что в случае разделения сети неизбежно возникают конфликты между доступностью и согласованностью.
* If partitioned, then availability and consistency else latency and consistency.

### Примеры C4 модели

![](https://github.com/Savchukv/System-Design-Fundamentals/blob/main/scheme_example_3.png)

![](https://github.com/Savchukv/System-Design-Fundamentals/blob/main/scheme_example_1.jpg)

![](https://github.com/Savchukv/System-Design-Fundamentals/blob/main/scheme_example_2.jpeg)
