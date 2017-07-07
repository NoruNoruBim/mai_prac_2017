# mai_prac_2017

Добавлен гид по азам git, смотреть ниже.

<<<<<<< HEAD
# Обновление 07.06.2017 8Ж:0
Интервал в итоге менять не стал, так как готовая верстка у многих разъезжается, не хорошо заставлять людей переделывать.  
Много всего добавилось, спасибо Серегею Лихареву. Гайд по изменениям скоро будет где-то тут.


# Обновление 06.06.2017 4:40
Залетели новые шрифты с засечками, чекайте, чтобы все работало.
Поменяйте \setmainfont{DejaVuSans} на \setmainfont{DejaVuSerif} как в test_cls
=======
# Обновление 06.06.2017 4:40
Залетели новые шрифты с засечками, чекайте, чтобы все работало.
Поменяйте `\setmainfont{DejaVuSans}` на `\setmainfont{DejaVuSerif}` как в test_cls
>>>>>>> ef5e06aee90976e8b78139618d22388a594982b7
Шрифты - DejaVuSerif как проверить, установлены ли - ниже.
Просили подчеркнуть: Мы используем XeLaTeX! Не обычный Latex! Компилятор у него свой.

# Обновление 05.06.2017 17:40
Починил хрень вверху страницы
Починил newtop

# Обовление 05.06.17
Пофиксил номера глав, теперь там Римские числа.
Пофиксил номера секций, теперь там одно число. Счетчик секций увеличивается перед
вызовом `\section{}` поэтому через `setcounter{}` указывать номер на 1 меньше.
Пофиксил номера сабсекций, теперь это `номер_секции.номер_подсекции`

Перенос строк после номера главы\секции\сабсекции поправлю потом, когда пойму как, лол.
При обноружении других ошибок пишите или открывайте ошибку на гитхабе в issues.

# Обновление
Теперь в начале файла задается номер страницы и главы.
Также можно вручную менять заголовок через функцию \newtop{ЗАГОЛОВОК}

Кто хочет в коллабораторы кидайте ссылки на профили

ВК:         id319485641  
Телеграмм:  @sunny_lera

# Как использовать гитхаб.
Это очень распространенный вопрос, на него есть куча ответов. Вот пример https://githowto.com/ На гитхабе есть куча документации, часть даже на русском.
Но, тем не менее, накатаю небольшой гайд.

Как юзать гит:
1. Ставим git: `sudo aptitude git`. Это консольная утилита. Для нее есть графический интерфейс, но использовать его не стоит.
1. Создаем локальный репозиторий клонированием: `git clone https://github.com/glumpo/mai_prac_2017.git)` 
1. Создаем свою директорию /10z/xxx-yyy (Surname) и работаем **только в ней!**
1. После внесения изменений в свои файлы добавляем их в коммит: `git add *`
1. Сохраняем их в локальном репозитории: `git commit -m "Message, describing your changes or additions"`
1. Отправляем в глобальный репозиторий на github: `git push -f origin master` (ключ -f нужен, если вы не хотите постоянно синхронизировать свой локальный репозиторий с глобальным (`git pull`) и хранить на своем компьютере чужие работы)

Для тех, кто совсем не умеет в консоль есть гуевый интерфейс. Однако, если нет опыта работы с git, в коллабораторы лучше не записываться. А то мы потом охренеем в путанице из коммитов разбираться. Как отправлять коммиты написано много где, если нужно разъяснить что-то, найдите того, кто разберается. Если что, пишите мне, я поясню.


# Как использовать гитхаб.
Это очень распространенный вопрос, на него есть куча ответов. На гитхабе есть куча документации, часть даже на русском.
Но, тем не менее, накатаю небольшой гайд. У вас должен стоять git (aptitude install git). Это консольная утилита.
Для него есть графический интерфейс, но не верен, что его стоит использовать.
Суть в том, что пользователь с помощью команды `git clone https://github.com/glumpo/mai_prac_2017.git` копирует к себе весь репозиторий.
Далее, в своем локальном репе вносит любые правки. С помощь команды `git add path/file` добавляет все файлы, изменения в которых нужно закинуть на гитхаб. При необходимости, отменить эту команду можно через `git reset HEAD path/file`.
Далее, вы с помощью команды git commit формируете коммит - пакет изменений, которые будут загружены на гитхаб.
После этого откроется косольный текстовый редактор (скорее всего nano) в котором вы коротко и на англицком напишите, что поменяли (пара фраз).
Сохраните вашу писану (в nano - Ctrl+o) и выйдите (в nano - Ctrl+x)). После этого коммит сформирован и может быть загружен на гитхаб командой
git push. Возможно, потребуется сначала скачать правки, которые сделали другие участники (git напишет об этом). Тогда сделайте git pull после чего git push.


# Оформление
В /106 лежит папка Мигалева оформленная в виде `номер_перво_стр - номер_последней_стр (фамилия латиницей)`.
Вот такого стиля стоит придерживаться.

# Темплейт
ОБРАТИТЕ ВНИМАНИЕ, темплейт написан под XeLaTeX. И в дальнейшем предполагается именно его использование. Собирать нужно не latex а xelatex он долже идти в стандартной поставке. Для обычной верстки тескта разница не заметна, но шрифты подключаются по-другому, работа с локалями - другая. В частности не работает babel.

В папке template лежит два файла. Первый - mai_book.cls - и есть темплэйт. Лежать он должен рядом с файлом к которому его подключают. Как подключать смотреть в файле test_cls.tex. Там же пример использования и подключенные шрифты. Короче, первые несколько строчек ( до \begin...) нужно скопировать себе. Там подключаются шрифты и локаль. На линуксах эти шрифты должны стоять по умолчания. Если что, проверить это можно командой ~~fc-list | grep DejaVuSans~~  fc-list | grep DejaVuSerif обатите внимание, должны быть не только обычный DejaVuSerif, но и DejaVuSerif bold и DejaVuSerif italic

Для сносок используйте footnote{текст сноски}

# Первоисточник
https://yadi.sk/d/2sBzRpeB3KiZxP по ссылке лежит архив. В нем две книжки. Одна - оригинал в формате djvu. Вторая - доблестно пропущенный через ABBY доблестным Лехой Бахаревым pdf. Короче, ABBY, конечно, хорош, но ошибки все равно остаются. Поэтому берем pdf, правим ошибки, если что - сверяемся с оригиналом, верстаем. Если есть желание пропустить через тессаракт, пробуйте, может, меньше ошибок будет. О результатах отпишитесь по контактам выше.

# Немного об используемых инструментах
Полезный сайт http://www.hostmath.com/ для верстки формул.

Так как в итоге мы должны будем скомпилировать всю эту фигню в одну большую, все нужно
придерживаться одного стандарта латеха. Как этого добиться.
1. Если нет уверености, запустится ли ваша фича на другом компиляторе, не суй ее в продакшен.
1. Те, у кого Debian-подобные дистры (всякие убунты, кубунты и прочее непотребство, а также минты и прочее) ставят из репов
`sudo aptitude install texlive texlive-science texlive-lang-cyrillic texlive-xetex`
1. Пользователями форточек смотреть ссылку ниже.

Используем именно `texlive`, а не `teTeX`, так как разработка последнего прекращена, соответственно, нахрен нужно легаси.
Если кто-то ставил его, удалите и поставьте `texlive` потому что черт знает, на сколько они совместимы

Вообще, вот тут все, что нужно уже написано  
https://ru.wikibooks.org/wiki/LaTeX/%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0_LaTeX  
Короткая: https://goo.gl/msnhXF

И помните  
# ВЛАДУ НУЖНО БЫСТРЕЕ!!!!