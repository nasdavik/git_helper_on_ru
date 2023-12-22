# Краткий справочник по работе с Git 

## Что нам нужно?

Для начала хочу описать, что вообще вас ожидает при прочтении. Это будет:

1. База. Постараюсь простыми словами сказать обо всем
2. Работа с консолью
3. Работа с Git и GitHub


## "База"

Git - это система контроля версий<br> 
Что это значит? По сути git позволяет обратиться к разным зафиксированным изменениям в вашем проекте<br>
Зачем это нужно? Предствьте что у вас есть крупный проект, котороый постепенно претерпивает изменения под вашим чутким надзором.
Каждое изменение в вашем продукте фиксируется. И вот, наступает момент когда вы внеслили что-то новое и по нелепой случайности все сломалось. 
Казалось бы, в чем проблема, нужно просто удалить последние измения. Как раз на этом этапе могут возникнуть трудности. 
Ведь если изменения содержат в себе много ручных правок, то что бы все вернуть на исходную, понадобится не мало времени.
Само собой, крупный проект также нельзя просто взять и переписать. Тут и приходит на помощь Git. Досточно просто откатить проект к предыдущей версии и все, проблема не успеет навредить)

GitHub - веб-сервис, который основан на системе Git. Некая социальная сеть, где можно хранить версии своих проектов. 
По большому счету, это логическое продолжение Git. По сути он расширяет возможности до общего пользования одним продуктом.
Как только у вас и вашего друга возникнет идея создать что-нибудь свое, общее, то GitHub позволит облегчить предстоящую работу.
Вдвоем, без лишней мароки вносить изменения во одни и те же файлы, при этом видеть что и где поменяли и иметь возможность откатится, если понадобится

Работать нужно будет через консоль. Косательно GitHub, если не ошибаюсь, есть десктопное приложение. Однако есть ряд причин, почему оно нам не понадобится.
Вот некоторые из них:

* GUI для удобной визуализации, консоль для скорости выполнения
* В GUI есть не весь функционал, который может понадобится
* Работа с консолью - универсальный навык. Привычка так взаимодествовать с необходимым софтом поможет в дальнейшем

Сразу скажу, что *GUI* - это приложение с графическим интерфейсом, т.е. те которыми вы чаще всего пользуете<br>
Исходя из выше сказано, прежде чем переходить к работе с Git, нужно понять как работать с консолью.
Стоит отметить что речь идет не о простой командной строке, которая есть на Windows. Безусловно работать можно и в ней, но лучше не надо) 
Дело в том что многие сервера рабоатют на unix-подобных системах и используется там оболочка __bash__. 
За нее и возьмемся, в угоду преобретения макимально полезного навыка при изучении


## Консоль

__Где взять то что нам нужно?__<br>
Будет достаточно скачать Git, при установке которого сразу можно установить Bash. Для этого кликай [вот сюда](https://git-scm.com/downloads "Давай, кликай уже").
При установке, достаточно будет просто оставить все по умолчанию. Если вы счастливый обладатель Windows, то для открытия Bash будет достаточно нажать ПКМ в любой папке и в выскакивающем поле возможностей вы увидите пункт __Open Git Вash here__

----

В самой консоли нужно работать за счет команд. По сути это все что нужно, знаешь команды - спокойно пользуешься функционалом

Вот некоторые из них:

* pwd - показывает в какой папке вы сейчас находитесь
* ls - показывает содержимое выбранной папки (по умолчанию, если не передавать никаких аргументов, то покажет содержимое папки, где вы сейчас находитесь)
* cd - позволяет переместиться в папку
* touch file.file - создает файл с указанием в каком оно расширение, такие как text.txt или kursach.docx
* mkdir namedir - создает папку (директорию) в той папке, где вы находитесь. Можно указать место, где вы хотите создать папку
* cp file.file ~/namedir - копирует файл в другое место. Первым аргументом вы указываете файл который хотите переместить, вторым аргументом идет путь до папки, куда переместить
* mv file.file ~/namedir - та же самая команда, что и выше, только вместо копии - она перемещает файл
* cat file.file - распечатывает содержимое файла, любого файла (забавы ради, попробуйте распечатать содержимое картинки). Само собой, эта команда используется для текста)
* rm file.file - удаляет файл
* rmdir namedir - удаляет папку
* rm -r namedir - рекурсивное удаление. Удаляет как саму папку, так и все что в ней находится

Ко многим командам можно дописывать различные дополнения, такие как:
* Буквенные -a, -m, -r и т.д. У всех их свое назначение, -a означает all, -m означает message, -r означает recursive
* Символьные ~ . .. /; ~ означает домашнюю директорию (/User/Useranme); . означает текущую директорию (как правило испоьлзуется для запуска скрпитов);
.. означает директорию выше (если вы находитесь в .../Dir1/Dir2, то это обозначение указывает на Dir1); / означает корневую директорию (речь идет о том когда символ используется как символ, а не часть текста, где прописывается путь. Чаще всего этот символ укзывает на диск С)
* Так же можно обединять несколько команд через &&. Например: Мы находимся в .../Username/Dir1. Чтобы посмотреть все файлы, которые есть в Username, мы просто можем прописать __cd .. && ls -a__

Ну и финальные парочку советов
1. Можно перемещаться в истоории команд, которые вы прописывали ранее, за счет стрелок вверх (↑) и вниз (↓)
2. Есть возможность дописывать за вас путь или команду, за счет *Tab*. Например: вы находитесь в папке, где есть файл text.txt.
Если вы хотите прочитать содержимое, то можете написать - *cat tex* и далее нажать *Tab*. На самом деле можно было вообще написать *cat t*, однако если есть варианты других файлов, которые начинаются также (по типу test.docx, tv_show.mp4), то консоль предложит вам выбрать какой из файлов вам нужен
3. При попытке что-то вставить используйте ПКМ

В конце этого блока хочу сказать, что несмотря на то что вся вышеописанная информация может показаться сухой и не понятной - ее просто нужно испробывать. 
У всего что я описал есть короткое пояснение. Опираясь на это можно придумать массу примеров, как это использовать в своих задачах. Немного фантазии и готово)

По началу все будет медленно и не ясно, каким образом это должно помочь быстрее решать задачи. Терпение, мой друг, тебе просто нужна практика. Применяй эти знания как можно чаще и результаты не заставят тебя долго ждать)


## Git и GitHub

В этом блоке не будет подробного описания как работать с данными технологиями (хотя и в предыдущих, не сказать что было все подробно). 
Я пройдусь по верхам для понимания что к чему, чтобы можно было уже начать использовть Git со своими работами

### Git

Коротко о том как происходит работа Git'а. Git может отслеживать конкретную область и фиксировать различные изменения.
Вы можете коментировать что конкретно было измененно, для того что бы когда вы возращались к истории своего проекта вам не пришлось проверять что там содержится (коментарий к этому изменению способен внести ясность)

В прошлом блоке было расказано о работе с файлами через консоль. Как не странно, но команды Git, начинаются с ключевого слова _git_

Ну и вновь несколько примеров:
* git init. Команда нужна для инициализации Git, или проще говоря для 'отслеживания' проекта. Используется крайне редко, ведь по сути просто дает возможность создать _репозиторий_. 
Для того что бы Git перестал отслеживать это папку (место инициализации), стоит просто удалить папку .git, а сделать это можно с помощью уже знакомой нам команды - rm. __rm -rf .git__.
Ключ -r позволяет удалить все задержимое папки вместе с ней. Ключ -f избавит вас от заключительных вопросов по типу: "Вы точно уверены, что хотите удалить файл X?". 
И да, вы все верно поняли, флаги можно накладывать друг на друга)
* git status. Как не сложно догодаться, показывает __статус репозитория__. Что это значит? Данная команды выводит некий отчет, который содержит в себе информацию о том:
    * в какой __ветке__ вы находитесь
    * какие изменения произошли в вашем __репозитории__
    * какие ЛОКАЛЬНЫЕ изменения сейчас у вас сохранены

* Все эти пункты будут обсуждаться дальше. Так же подмечу, что git init можно использовать в любом месте, такова его специфика. 
Но эта команда и все послдедующие могут использоваться только в месте, где создан репозиторий. 
Ведь все они направлены на прямое взаимодествие с Git репозиторием
* git add. Нужен для отслеживания состояния файлов. Если git init позволил нам выбрать область, в которой мы сможем отслеживать изменения файлов, 
то git add как раз позволяет записать что из себя представляет файл в конкретный момент времени. Например: У нас есть файл 
staff.txt, который хранит в себе список сотрудников. Чтобы мы могли его отслеживать в нашем репозитории нужно прописать в консоли 
git add staff.txt. Так же можно добавить все файлы проекта командой git add --all или git add -A. Важно подметить, что git add 
добавляет ИЗМЕНЕНИЯ. Т.к. по началу наш репозиторий пуст, то для него любой файл является новым, что само по себе изменение в проекте. 
Удаление, редактирование сюда же. Если они появлются - это изменение.
* git commit. Это команда без которой не может обойтись git add. Тут мы просто коментируем что конкретно мы поменяли/добавили/удалили. 
Никто конечно не запрещает написать полный бред, но тогда самим будет сложнее разобраться, что же я там такого наделал. Чем понятнее будет напсан коментарий - 
тем лучше для вас и других пользователей репозиотрия. Прописывается он как _git commit -m "Your change"_. На прошлом примере: Мы добавили новых людей в список сотрудников 
(staf.txt). Теперь чтобы это зафиксировать нужно выпонить компанды:
    * git add staf.txt
    * git commit -m "Added 11 people in list our team"
* коментарии можно писать и на русском, тут уже каждый решает сам. Еще раз заострю ваше внимание. git commit необходим после git add. Только так можно будет окончательно 
сохранить изменения.
* git log. Показывает историю комитов в обратном хронологическом порядке
* git push. Позволяет перенести локальные изменения на удаленный сервер. Все что мы делали до этого - это изменения, которые 
хранились на нашем устройстве. Если у вас настроен удаленный репозиторий, то после создания комита(ов) их можно 'запушить' на
сервер. Эта тема будет затронута далее.
* git pull. Позволяет 'скачать' изменения удаленного сервера себе локально. Можно сказать что это противоположная команда git push. 

----

### GitHub

Тема удаленного репозитория - это как раз про github. Это своего рода социальная сеть для программистов и других деятелей, занимающихся 
проектами с использованием контроля версий. Ранее когда речь шла о сохарнение изменений, все располагалось локально. При 
таком сценарии не получится вместе с другом/командой работать вместе над проектом. Однако если вы имеете доступ к одному удаленному репозиторию, 
то эта проблема решается. 

Хочу заметиить что удаленный репозиторий и локальный - это не одно и тоже (то что у вас названо одним именем на компьютере, не 
обязательно должно так же называться в облоке). Однако это в случае если связывать 2 этих репозитория между собой. Как правильно 
я пользуюсь более простым способом. Создаю удаленный репозиотрий, скачиваю его себе, и после могу редактировать без лишних заморочек.