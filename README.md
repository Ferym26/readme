<h1 align="center">Горячие команды Git</h1>

					Начало работы:


Базовые настройки:
	Перед началом работы следует зарегистрировать себя на рабочей машине, так git сможет получать ваши данные о коммитах

	git config --global user.name "Your Name"
	git config --global user.email "your_email@whatever.com"

Создание репозитория:

	$ git init - Эта команда создаёт в текущем каталоге новый подкаталог с именем .git содержащий все необходимые файлы репозитория — основу Git-репозитория.(Появляется скрытая папка). Проще говоря создает локальный репозиторий.

	$ git clone "url" - скачивает удаленный репозиторий(например с github).
	Пример: $ git clone https://github.com/Eclerrr/readme.git





				   Базовые операции:

Рабочая схема:
	1) Создать локальный репозиторий.(клонировать удаленный или создать новый).

	2) Выбрать версию проекта. "git checkout хеш"(если нужна свежая скачанная версия, пропускаем этот пункт).

	3) Внести изменения в файлах.

	4) Проверить изменнения с помощью "git status". Если все хорошо, надписи красные , продолжаем работу.

	5) git add имя файла  - проиндексировать изменненые файлы, зафиксировать.

	6) Пришло время создать коммит git commit -m"комментарий". После этого появится новая версия вашего проекта.

	7) Проверить новый коммит командой  git log. Если все нормально переходим дальше.

	8) Самое время отправить на сервер. 
	git push https://github.com/Eclerrr/readme.git master.
	Ссылка примерная!!!


Работа с коммитами:
	После создания локального репозитория можно начинать в нем работу(создание, удаление, редактирование файлов).
	Как только вы ввели в консоль $ git init или $ git clone,
	git сразу начинает отслеживать папку в которой лежит скрытый файлик .git.
	Любые изменения фиксируются в гите.

	$ git status - Определить состояние файлов.

	$ git add - Многофунциональная команда.

	1) git add имя файла - Фиксирует измененный файл в гите. Предворительная фаза перед коммитом(подстраховка)
	git add . - фиксирует все файлы в каталоге.(Использовать с осторожностью).

	После фиксирования, файлы можно коммитеть(Сохранять).

	$ git commit -m"комментарий" - Создает коммит (версию) вашего проекта. Метка -m добавляет комментарий к комиту. Можно коммитеть без метки , но тогда git выведет редактор по умолчанию(Редактор linux). Настройка редактора будет описана в другом разделе. Лучше делать логичные комминтарии, типа "Добавлен файл index.html".

	$ git shortlog -s -n  - количество сделанных коммитов у данного пользователя

Перемещение по коммитам:
	Когда ваш проект набирает обороты и появляется большое количество коммитов, может возникнуть потребность в откате версии(или простого просмотра старых версий).

	$ git log - показывает все создынные коммиты на текущей версии.
	Отображается примерно так:

	commit 903badab46602ecfdd504e16f099f837901789b7
	Author: Eclerr <eclerrrr@yandex.ru>
	Date:   Tue Jan 19 18:24:50 2016 +0300

    Создан файл commands.txt. Добавлен абзац 'Начало работы'

    903badab46602ecfdd504e16f099f837901789b7 - хеш коммита(Имя коммита)

    $ git checkout 903ba - переходит на указанный коммит. 903ba в данном случае 5 первых символов хеша коммита. checkout возвращает вас назад во времени, а это значит что коммиты, созданные после указанного не будут отображаться в git log(их по факту еще не создали).

    $ git checkout master - переместит на последний коммит(вернет в настоящие).

Редактирование коммитов:

	Если возникла потребность изменить сделать небольшую поправочку в каком либо файле, при этом не делать новый коммит(К примеру добавить комментарий), можно перезаписать коммит:

	$ git commit --amend -m"Перезапись коммита", При этом перезапишется последний коммит.



 Работа с ветками:

 	$ git branch - просмотреть список веток

 	$ git checkout -b имя ветки -  создать ветку и срузу же перейти в нее(с помощью ключа -b)

 	$ git branch имя ветки - создать ветку

	$ git checkout имя ветки - перейти в ветку.

	$ git checkout master - перейти в начальную ветку вашего проекта.


Работа с удаленным репозиторием

	После того, как вы сделали достаточное количество коммитов, самое время отправить ваш проект со всеми сохранениями на удаленный репозиторий(к примеру GitHub).

	$ git push https://github.com/Eclerrr/readme.git master   -  отправляет проиндексированные и закоммиченные изменения вашего проекта на сервер.

	url репозитория указан тестовый

	master - начальная ветка удаленного репозитория(Можно использовать любую другую ветку)
	
	Если во время работы ваш локальный репозиторий устаревает(К примеру, кто-то другой уже запушил изменения на сервер), можно обновить вашу версию локального проекта:

	$ git ************************************************

	Для удобства url можно поместить в короткое имя:

	$ git remote add pb git://github.com/paulboone/ticgit.git

	pb - короткое имя url, в дальнейшем с ним можно работать.

	$ git remote -v - позволяет вывести все имена url.






Вопросы на будущие:
	
	Тут будут копится мои вопросы на будущие:

	1) Как удалить ветку.

	2) Обновление удаленного репозитория.
