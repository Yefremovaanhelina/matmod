---
# Front matter
lang: ru-RU
title: "Лабораторная работа 1"
subtitle: "Математическое моделирование"
author: "Ефремова Ангелина Романовна"
teacher: "Кулябов Дмитрий Сергеевич"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Цель первой лабораторной работы - научиться работать с системой git, опрерировать git bash, создавать и привязывать ssh-ключи, загружать, изменять, скачивать, удалять файлы и репозитории на GitHub, пользоваться Markdown и писать с его помощью документы.

# Задание
## Создание аккаунта на GitHub
## Создание нового репозитория на GitHub
## Первичная настройка Git Bash
## Создание и редактирование локального файла с помощью Git Bash
## Загрузка проекта на GitHub с помощью Git Bash
## Привязка к аккаунту SSH-ключа

# Выполнение лабораторной работы

## Создание аккаунта на GitHub

Для начала, я создала новый GitHub-аккаунт на корпоративную почту. В процессе регистрации ничего необычного нет. Вот так теперь выглядит мой новый аккаунт. (рис. -@fig:001)

![Созданный аккаунт на GitHub](C:\Users\NVChirkov\Pictures\1.png){ #fig:001 width=70% }

## Создание нового репозитория на GitHub

Нажав на зеленую кнопку, я создала новый публичный репозиторий для лабораторной работы. Назвала его Matmod. Пока что он пуст. (рис. -@fig:002)

![Новый репозиторий Matmod](C:\Users\NVChirkov\Pictures\2.png){ #fig:002 width=70% }

## Первичная настройка Git Bash

Для того, чтобы использовать Git Bash, необходимо задать некоторые параметры. Для начала, это установка имени и эмейла. Так как еще со вчерашнего дня я пыталась выполнять лабораторную работу, имя и эмейл у меня уже настроены. Затем, я настроила параметры установки окончаний строк и отображения unicode. Теперь я защищена от нечитаемых строк и все переводы строк текстовых файлов в главном репозитории у меня одинаковы. (рис. -@fig:003)

![Настройка Git Bash](C:\Users\NVChirkov\Pictures\3.png){ #fig:003 width=70% }

## Создание и редактирование локального файла с помощью Git Bash

Я создала папку lab01 с помощью команды mkdir. Затем, создала файл README с помощью команды touch. Командой echo, я записала в него фразу, а командой cat - посмотрела содержимое этого файла. (рис. -@fig:004)

![Созданный файл README](C:\Users\NVChirkov\Pictures\4.png){ #fig:004 width=70% }

## Загрузка проекта на GitHub с помощью Git Bash

Для загрузки файла на гит, я использовала стандартный набор команд add + commit + push. В результате, мой файл был загружен на гитхаб, о чем говорит последняя строка (рис. -@fig:005)

![Загрузка проекта на гит](C:\Users\NVChirkov\Pictures\5.png){ #fig:005 width=70% }

Далее я захожу на GitHub, чтобы убедиться, что мой проект действительно загружен. (рис. -@fig:006)

![Мой репозиторий на GitHub](C:\Users\NVChirkov\Pictures\5,1.png){ #fig:006 width=70% }

## Привязка к аккаунту SSH-ключа

С помощью команды, я сгенерировала ключ, придумала пароль и скопировала сгенерированный ключ. (рис. -@fig:007)

![Генерация ключа в Git Bash](C:\Users\NVChirkov\Pictures\6.png){ #fig:007 width=70% }

Затем, я перешла на сайт GitHub, для того, чтобы привязать созданный ключ к аккаунту. Для этого, я перешла в настройки, затем в раздел с SSH-ключами и добавила новый ключ. На странице он теперь отображается. (рис. -@fig:008)

![Привязка ключа к аккаунту](C:\Users\NVChirkov\Pictures\7.png){ #fig:008 width=70% }

И после этого я вернулась в Bash, чтобы убедиться в работоспособности ключа. Написав команду, я получила следующий ответ от программы, который говорил, что ключ активирован. (рис. -@fig:009)

![Проверка SSH-ключа](C:\Users\NVChirkov\Pictures\8.png){ #fig:009 width=70% }

# Выводы

В результате выполнения первой лабораторной работы, я научилась работать с системой git, опрерировать git bash, создавать и привязывать ssh-ключи, загружать, изменять, скачивать, удалять файлы и репозитории на GitHub, пользоваться Markdown и писать с его помощью документы.

