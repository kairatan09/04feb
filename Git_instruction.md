# <span style="color:blue">Инструкция для работы с командами Git</span>

Git (произносится «гит») — распределённая система управления версиями. Проект был создан Линусом Торвальдсом для управления разработкой ядра Linux, первая версия выпущена 7 апреля 2005 года. [Официальный сайт](https://git-scm.com "Кликни для перехода на сайт")

![Картинка не загрузилась!](git_logo.png "Это логотип Git")

Разработка ядра Linux велась на проприетарной системе BitKeeper, которую автор — Ларри Маквой, сам разработчик Linux — предоставил проекту по бесплатной лицензии. Разработчики, высококлассные программисты, написали несколько утилит, и для одной Эндрю Триджелл произвёл реверс-инжиниринг формата передачи данных BitKeeper. В ответ Маквой обвинил разработчиков в нарушении соглашения и отозвал лицензию, и Торвальдс взялся за новую систему: ни одна из открытых систем не позволяла тысячам программистов кооперировать свои усилия (тот же конфликт привёл к написанию Mercurial). Идеология была проста: взять подход CVS и перевернуть с ног на голову, и заодно добавить надёжности.

Начальная разработка велась меньше, чем неделю: 3 апреля 2005 года разработка началась, и уже 7 апреля код Git управлялся неготовой системой. 16 июня Linux был переведён на Git, а 25 июля Торвальдс отказался от обязанностей ведущего разработчика.

Торвальдс так саркастически отозвался о выбранном им названии git (что на английском сленге означает «мерзавец»):

> I'm an egotistical bastard, so I name all my projects after myself. First Linux, now git.

Перевод
> Я эгоистичный ублюдок, и поэтому называю все свои проекты в честь себя. Сначала Linux, теперь git.

## <span style="color:blue">1. Задать имя пользователя и адрес электронной почты</span>

Имя пользователя нужно, чтобы привязывать коммиты к вашему имени. Задать или изменить имя пользователя можно с помощью команды git config. Новое имя будет автоматически отображаться в последующих коммитах. Чтобы задать имя пользователя нужно набрать следующую команду, где внутри двойных кавычек указывается имя пользователя:

> __*git config --global user.name "Иван Иванов"*__

Кроме того, командой git config можно изменять адрес электронной почты, привязанный к вашим коммитам Git. Новый адрес электронной почты будет автоматически отображаться во всех дальнейших коммитах, поданных на GitHub через командную строку.

> __*git config --global user.email "ivan@mail.ru"*__


## <span style="color:blue">2. Инициализация репозитория</span>

Создать пустой репозиторий Git или вновь инициализировать существующий можно параметром init. При инициализации он создаст скрытую папку. В ней содержатся все объекты и ссылки, которые Git использует и создаёт в истории работы над проектом.

> __*git init*__

## <span style="color:blue">3. Добавление файлов в область подготовленных файлов</span>

Добавить отдельный файл в область подготовленных файлов можно параметром add с указанием имени файла. Просто замените first.md на актуальное имя.

> __*git add first.md*__

## <span style="color:blue">4. Проверка статуса репозитория</span>

Просмотреть статус нужного репозитория можно по ключевому слову status: его действие распространяется на подготовленные, неподготовленные и неотслеживаемые файлы.

> __*git status*__


## <span style="color:blue">5. Внесение изменений однострочным сообщением</span>

При создании коммита в репозитории можно добавить однострочное сообщение с помощью параметра commit с флагом -m. Само сообщение вводится непосредственно после флага, в кавычках.

> __*git commit -m "Это первый коммит"*__

## <span style="color:blue">6. Просмотр истории коммитов с изменениями</span>

Просматривать изменения, внесённые в репозиторий, можно с помощью параметра log. Он отображает список последних коммитов в порядке выполнения. Кроме того, добавив флаг -p, вы можете подробно изучить изменения, внесённые в каждый файл.

> __*git log -p*__

## <span style="color:blue">7. Просмотр изменений до коммита</span>

Можно просматривать список изменений, внесённых в репозиторий, используя параметр diff. По умолчанию отображаются только изменения, не подготовленные для фиксации.

> __*git diff*__

## <span style="color:blue">8. Удаление отслеживаемых файлов из текущего рабочего дерева</span>

Удалять файлы из текущего рабочего дерева можно с помощью параметра rm. При этом файлы удаляются и из индекса.

> __*git rm first.md*__

## <span style="color:blue">9. Переход на ранние коммиты</span>

Для перехода на ранее сохраненным версиям необходимо сначала посмотреть командой __*git log*__ идентификатора коммита, а затем переход к ним командой: 

> __*git checkout xxxx*__

где "xxx" - это первые 4 символа идентификатора коммита.

## <span style="color:blue">Заключение</span>

Вы узнали основные команды интерфейса командной строки Git для начинающего. Теперь, при условии регулярной практики, у вас есть всё необходимое, чтобы достичь мастерства в управлении репозиториями GitHub.