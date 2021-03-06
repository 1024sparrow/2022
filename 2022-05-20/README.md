# 2022-05-20 - Знакомство с системой контроля версий GIT

## Некоторые команды оболочки bash

`cd <куда>` - перейти в директорию (`.` - текущая директория, `..` - директория уровнем выше)

`cd -` - вернуться после последней смены текущей директории

`ls` - вывести содержимое текущей директории

`cp <путь до файла, который копируем> <путь, по которому этот файл должен быть, или путь до директории назначения>` - скопировать файл. Директория - это файл. Если надо скопировать директорию (со всем её содержимым, даже если эта директория пуста), требуется ключ `-r` (recusrsive)

`mv <путь до файла, который перемещаем> <путь, по которому этот файл должен быть, или путь до директории назначения>` - переместить (или просто переименовать) файл (или директорию). Можно одной командой и переместить в другую директорию, и переименовать.

## Работа с удалённым репозиторием

`git clone https://github.com/<username>/<repository_name>.git` - склонировать имеющися репозиторий себе на машину

`git pull` - затянуть в текущую ветку изменения с удалённого репозитория

`git push` - залить текущее состояние текущей ветки из локального клона репозитория в удалённый репозиторий

## Работа с локальным репозиторием

`git status` - получить текущее состояние локального репозитория

`git add <путь до (одного или нескольких) файла(ов) (абсолютный или относительный)>` - добавить изменения в файле на учёт в системе контроля версий (`git`). После этого, если будете делать коммит, изменения в этом(их) файле(ах) попадут в коммит.

`git reset <путь до (одного или нескольких) файла(ов) (абсолютный или относительный)>` - снять изменения в файле с учёта в системе контроля версий. После этого, если будете делать коммит, изменения в этом(их) файле(ах) не попадут в коммит.

`git commit -m <комментарий к коммиту>` - сделать коммит. Этот коммит - только на локальном клоне репозитория. Он не попадёт на удалённый репозиторий, пока не сделаете `git push`.

`git diff` - показывает изменения в файле относительно того, как было на момент последнего коммита. Если после этого не указать имя файла(ов), то выведет изменения во всём репозитории. Если указать кокретный(ые) файл(ы), то выведет изменения тлько в указанном(ых) файле(ах). Если вы уже выполнили `git add` к какому-то файлу, то изменения в них `git` уже не покажет (используйте `git diff --cached ...`, если хотите посмотреть изменения, проиндексированные для коммита)
