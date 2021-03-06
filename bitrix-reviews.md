# Отзывы о битриксе

* Большинство отзывов взято из комментариев "джинсовой" статьи на хабре
  - https://habr.com/ru/post/517114/
  - (сохраенине) http://web.archive.org/web/20200831074315/https://habr.com/ru/post/517114/
 
## 
Честно говоря, тоже всегда думал, что причина популярности битрикса это маркетинг.
Когда пришлось ради нескольких проектов влезть внутрь, понял, что причина популярности - это то, что условный сайтовладелец может туда запустить любого фрилансера за 300р в день, чтоб тот что-то сделал. Это, в принципе, применимо и к веб-студиям, у которых экономика сходится только если в штат написать "вэб-мастера" на 30-40к рублей в месяц. Они просто финансово не вытянут кого-то выше формошлёпа.
Это будет криво, это будет уязвимо, это будет даже без использования API битрикса, но снаружи будет выглядеть как будто так и надо.

PHP-фрилансер не будет думать как там у битрикса роутинг работает, ведь его нет, ему достаточно либо в нужный index.php вписать свои запросы по циклу + echo, либо худо бедно найдёт шаблон компонента.
Не будет мучаться с шаблонизатором, ведь его тоже нет.
Нужные библиотеки просто инклуднет и всё, ведь композера в битриксе <s>тоже нет</s>, ладно, есть, но кто его там использует, будем честны?

Вообще, по части кода в битриксе <b>ничего нет</b>, документация есть, да, но от документации плакать хочется, у любого опенсорс-проекта она напорядок богаче.
И счастье если к доке есть комментарии от неравнодушных людей, именно из них узнаешь о недокументированном поведении и каких-нить секретных параметрах.

Что касается битрикса как фреймворка - если он такой классный, то почему всякие интеграторы золотого уровня с бравадой рассказывывают, как изобрели очередную химеру, <a href="https://blog.sibirix.ru/amp/2019/09/16/bitrix-or-framework/">скрестив Битрикс с Laravel</a> или YII?

Ну и да, в таком классном инструменте для разрабов до сих пор нет миграцией, нет нормального деплоя, написание своих мастеров - это боль и хаки ядра.

Автор в статье передёргивает некоторые факты.
Особенно повеселило про рынок труда в Битриксе.
Впрочем, подобные публикации <a href="https://vc.ru/hr/116578-samye-vostrebovannye-razrabotchiki-v-digital-agentstvah">уже были</a>. Для меня они означают кадровый голод и скорый закат этой <s>эко</s>какахосистемы

## agency
да право. Реально в профильном чате нужно писать про общепринятые стандарты подхода к программированию которые это поделие вертит на всём чём может?  Краткий список:
- управление зависимостями через композер вроде как является нормой современного веб дева а что там у битрикса с этим?
- Есть всякие нормы типа "1 точка входа в приложение" (обычно через index.php в корне и дальше роутинг) а у битрикса шлёпай файлы хоть куда и будь что будет - движок прям подстёгивает говнокодить по максимому
- ну если про современные подходы говорить - можно взять вобще весь список PSR (https://www.php-fig.org/psr/ - для ленивых) - и что там у битрикса хоть с одним из них?
- поддержку php7.3 выкатили за 2-3 месяца до того как php7.2 превратилось в тыкву. И да, не обновить без продления лицензии битрикса конечно.
- все хвалят "обмен с 1С из коробки" - тут вообще предлагаю забубенить общий опрос - сколько у вас в вашей компании было обменов из коробки? наверно около нуля - а вот потом "правки" этого чуда скорее всего были через хаканье ядра и невозможность нормально обновить движок потому что почему? да потому что никаких dependency injection в битриксе быть не может
- из всего вышесказанного если у человека только 10 лет опыта на битриксе - это примерно джун в современном вебдеве
- гляньте как классно развивается движок. Например откройте модуль "форум" и посмотрите как (никак) он изменился с 2013 года. Или как изменился любой другой модуль не связанный с екоммерцем и при чём тут вобще рассуждения о ВУЗах (вместо битрикса туда можно вообще купить нортон-антивирус - его также можно поставить на баланс как ПО а всё остальное написать прямыми руками)
- CI/CD ?
- С кэшем там какой-то лютый пизос, почитайте комменты https://dev.1c-bitrix.ru/community/blogs/howto/1786.php
- Ну а это вообще моё любимое https://dev.1c-bitrix.ru/support/forum/forum6/topic10785/ - пролистайте до конца. пост от 2008, последний коммент на момент публикации `Год 2020. Ничего не поменялось`) Тут нужно пояснить наверно что этот инструмент - это супер необходимая вещь в том случае когда вы хотите построить взрослый процесс раработки CI/CD  когда программисты работают на копии а потом выкатывают изменения на основной сайт.
##
4 года назад перевели свой интернет магазин с самописной erp на 1с УТ и битрикс. Потом между ними пришлось добавить retailCRM.

Платим примерно по 2-4 млн в год за поддержку и реализацию всяких плюшек.
В битрикс стандартно 1-2 раз в мес что-то отваливается, порой так что пол дня люди не могут оформить заказы.

При этом многие важные задачи делаем в гугл таблицах ( финансовое планирование и тд )

За это время я полностью разочаровался в этих продуктах.

    битрикс прожорлив и ему нужно не плохое железо
    битриксу нужна постоянная поддержка так как регулярно, что то ломается
    1с нужен хороший сервак
    1с сам по себе не ломается, но надо много чего дорабатывать, при этом 80% накрученного функционала в УТ совершенно не используется
    1с интерфейс просто провал
    1с не удобно пользоваться через веб интерфейс


Из всего этого набора только retailCrm работает стабильно и не вызывает ни каких проблем у сотрудников. Выходит для нас 30-40 тыс в мес.

В итоге решили снова переходить на самописную систему. На разработку потратим также 3 млн в первый год, хетцнеровского облака за 50 евро/мес хватит с гигантским запасом.
Реализуем там именно то, что будет нужно нам.
И конечно делая модули для боксберри, сдека и других, сразу нормально реализуем обработку ошибок и добьемся их отказоустойчивости.

В защиту 1с скажу то, что она изначально создавалась для того, что бы каждый сотрудник отвечал за свою узкую область из за этого есть множество операций с большим кол-вом нажиманий кнопок. Нам пришлось выделить одного сотрудника чисто на 1с.

Мало у бизнесу же нужно, что бы все делалось как можно проще, быстрее и желательно одной кнопкой)
##
Самая главная причина не описана — это феерическая мешанина отвратительного низкокачественного кода, вынуждающая писать в таком же похабном стиле. Программист, связваший свою судьбу с битриксом, не имеет никаких шансов на саморазвитие и погрязает в вечной поддержке спагетти-кода для, прямо уж скажем, малоинтересных с технической стороны проектов. А что платят нормально (хотя это кому как) — ну так за вредность.

Ну и еще немаловажная причина — за пределами ex-USSR оно вообще никому не сдалось.
##

За что программисты не любят «Битрикс»? Всё очень просто: достаточно зайти на официальный сайт, скачать демо-версию и посмотреть код. Те же стандарты разработки PSR не соблюдаются совершенно — код отвратительного качества. Конечно, программисты не хотят работать с таким «добром», ведь это деградация. После нескольких лет работы с «Битрикс» уже трудно будет трудоустроиться в фирму, где следят за качеством кода. На мой взгляд, это основная причина, почему программисты не любят «Битрикс». И это не только моё мнение.

## 
    Встроенную синхронизацию с «1С: Управление торговлей», «1С: Бухгалтерия», «1С: Зарплата и управление персоналом».
Эта поделка до полноценной синхронизации не дотягивает.

    На мой взгляд, пренебрежение к «Битриксу» у программистов PHP появилось по трем причинам...
И к битрикс программистам тоже. Я сам лично отказывал битриксоидам не раз. Видя резюме я сразу же начинал выяснять как человек пишет код. И нет вот этого омерзительного кода мне в проектах не нужно, а переучивать людей требующих с порога 6-значную зп я не желаю.

Ну и на международных проектах люди, работвашие всю жизнь только с битриксом, практически бесполезны.

    Судя по динамике последних лет, доли продуктов «1С-Битрикс» продолжат расти. 
Это просто шикарно, клиенты сидящие на битриксе уже сейчас готовы заплатить любые деньги чтобы поднять свою базу с колен, а когда их будет еще и много можно будет поставить прекрасные барьерные цены.

## 
Видел проект на Symfony, который был переписан битриксоидами.

Я за свою короткую карьеру успел поработать со сложным с точки зрения программиста кодом — весь на конфигах и описанный в виде DSL, но такого Г, написанный бывшими битриксоидами я не видел — просто тонны не понятного кода и не понятных абстракций, не понятно чего делающего. Убежал на второй день работы, очень известный проект.

…

Кейс 2: В резюме на ранней поре писал в пожеланиях пунктик «не готов работать с Битриксом» — один раз спасло, когда мне решили дать на доработку внутренний проект компании. Посмеялись и вспомнили договоренность на собесе и проект ушел другому — советую взять за основу такой прием.
##
Работаю в крупной компании, которая начинала с Битрикса, и ушла от него. Причина банальная — дикие тормоза. По мере роста приложения. Когда число клиентов стало исчисляться десятками тысяч — Битрикс лёг. И это всё что надо о нем знать.
##
Автор статьи живёт в какой-то паралельной вселенной. Как только клиент поставит типовой сайт на битрикс — всё хорошо, но каждый шаг чуть в сторону от коробки — это просто попоболь, когда ты вдруг узнаёшь что там под капотом у этой коробки.

Про это ни слова, ни слова про то, как многие годы продукт не развивался для программистов, просто добавляли новые свистульки для начальства.
##
Дорабатывал три проекта на битриксе, когда люди уже пришли отчаянные, со словами: ну сделай хоть что-нибудь.
Итак:
1) PSR нет
2) mbstring.func_overload в 2020
3) composer нет
4) куча global'ок
5) поддержки нет (см ниже)
6) документация устарела, непонятно, что сейчас с их D7, вроде бы есть, а вроде бы все на него положили.
7) если в интернет магазине 10 000 товаров и есть кастомные поля, тушите свет. Это все очень сильно тормозит
8) мне непонятно, зачем для обычного CRUD'a нужно кеширование всего и вся
9) самое главное!!! Если у тебя в запросе была ошибка, то вместо Exception тебе будет прямо через echo напечатано DB Error с форматированием.

У меня была проблема с чеками, написал на форум битрикса — тишина, написал на тостер — меня битриксоиды профессионалы мягко «опустили», сказав, что я не разбираюсь, но при этом конечно же не помогли. В итоге проблему решил, читая исходники битрикса. Внутри исходников ад, комментариев нет, без них начинаешь хоть что-то понимать, прочитав блок раза 2-3.

Далее — токсичность сообщества. Куча профессионалов, которые живут в своем мире, при этом раз в год делают набеги на другие сайты, показать, какой битрикс крутой коробочный продукт. Окей, пользуйтесь им, без проблем.

На счет синхронизации с 1С, сейчас любая школьная CMS это позволяет сделать, потому что к тебе приходит бизнес и говорит, хотим интеграцию с 1С, ок, берем любую другую CMS + модуль синхронизации и все.
##
Встроенные синхронизации никогда не работают из коробки, а системы онлайн-оплаты легко прикручиваются и без битрикса.
##
Я выскажу свой опыт только со стороны админов:
1. Натурально десятки тысяч файлов в самой цмске. Тысячи файлов просто нулевого размера. Файловый бэкап легкий такой ад, если не подготовиться к этому заранее.
2. Любая попытка решить проблемы: шлют к авторизованному партнеру, который обычно тоже ничего не знает, хвалит какой битрикс замечательный и месяцами не может решить проблемы.
3. Полгода с авторизованным партнером играли в мяч, потому что сайт клиента регулярно ловил малварю с криптомайнером. Партнер утверждал, что наш хостинг дырявый и этот сайт из-за этого регулярно ломают. При том, что там же лежали другие сайты на битрике с последней мажорной версией вообще не замеченные в взломах и обслуживаемые другой вебстудией. В итоге взяли за жабры клиента что бы он продлил техподдержку и обновил битрикс до последней мажорной версии. Проблема мгновенно исчезла.
4. Сказка по интеграции Битрикс 24 с телефонией просто бесконечна. Официальная техподдержка — поголовно лесные рогатые животные. Зачем продавать коробочное онпрем решение, внезапно, работающее исключительно через их облако непонятно.
5. Дикий ад с звонками через браузер, когда что то может внезапно отвалиться просто потому что свет Солнца прошел через кислотные облака Венеры и через окно попал на ноут менеджера. Иногда разное поведение в хроме, опере и файрфоксе в плане звонков. То слышно клиента, но клиент не слышит менеджера. То звонка не было, но появляются пропущенные. На два десятка менеджеров регулярные проблемы каждые три четыре дня.

Прям перекрестились и отпраздновали, когда клиент в итоге отказался от этого решения, взяв решение от одного из операторов большой тройки.
##
Жизнь слишком коротка, чтобы тратить ее на такие вонючие помои, как Битрикс.
##
Вот только неделю назад завершил два проекта, у заказчика были два сайта на Битриксе. И это был ад. Миллион мелких файлов, которые собираются потом в один непонятным образом, и фиг поймёшь, что откуда взялось.

Просто файловая структура:

/catalog
/bitrix/components/bitrix/catalog
/bitrix/components/bitrix/catalog/templates/.default/bitrix/catalog.compare.list/.default
/bitrix/components/bitrix/catalog/templates/.default/bitrix/catalog.section.list/.default/template.php
/bitrix/templates/general/components/bitrix/catalog/catalog/bitrix/catalog.element/.default/template.php
/bitrix/templates/.default/components/bitrix/catalog/detail_catalog/bitrix/catalog.element/.default/template.php


… и так далее. По 10 папок на каждом уровне, в каждой могут лежать свои шаблоны, скрипты и css-ки. Вот скажите, как вообще навскидку понять, в каком из последних трёх каталогов лежит нужный файл?!

У меня одно слово — издевательство. Вменяемые люди так с разработчиками не поступают. У человека должен быть Битрикс головного мозга, чтобы слово bitrix встречалось на пути к файлу три раза!!!

У каждого компонента ещё и шаблон вперемешку с php. Каждый компонент подключается с кучей опций, и там вперемешку на одном уровне будут идти и настройки кеша, и текст сообщения о пустой корзине. И ещё там находятся inline-css и inline-js!

Как вообще с этим работать?! Никогда не знаешь, какой кусок где подключится, где не подключится. Да чтоб разработчики этой архитектуры питались одной длинной лапшёй, которая у них вместо кода!!!

Естественно, всё это зверски тупит, если не включить "автокеширование". Но оно тоже написано криво и не очень хорошо работает.

В общем, исправляешь где-то кусочек и молишься, чтобы это всё не рухнуло. Ощущения от работы с этим всем — омерзительные.

P.S.: компонент Блог: 34 (!!!) папки на уровне /bitrix/components/bitrix/.
И в каждом ещё лапша.

А ещё есть сторонние компоненты...

Так что не надо сказок, что Битрикс хороший. Это дрянь, как по архитектуре, так и по коду. Я даже не углублялся в проблемы кода или а то, что официальное обновление может сломать всю работу сайта просто так, потому что "не подумали".

Этому монстру давно пора умереть, жаль, что никто не сделал скрипт автоматической миграции — озолотились бы.

Нет в одном фреймворке, что в самописных, что в известных, даже в древнейших Drupal 5 или Joomla 2, такого бардака не было. Битрикс изначально кривой и неподдерживаемый, и с годами только хуже.
##
