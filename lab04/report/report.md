﻿---
# Front matter
lang: ru-RU
title: "Лабораторная работа 4"
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

Цель четвертой лабораторной работы - рассмотреть модель линейного гармонического осциллятора.

# Задание

## Построить решение уравнения гармонического осциллятора без затухания.
## Записать уравнение свободных колебаний гармонического осциллятора с затуханием, построить его решение. Построить фазовый портрет гармонических колебаний с затуханием.
## Записать уравнение колебаний гармонического осциллятора, если на систему действует внешняя сила, построить его решение. Построить фазовый портрет колебаний с действием внешней силы.

# Выполнение лабораторной работы

## Теоретическая справка

1. Движение грузика на пружинке, маятника, заряда в электрическом контуре, а также эволюция во времени многих систем в физике, химии, биологии и других науках при определенных предположениях можно описать одним и тем же дифференциальным уравнением, которое в теории колебаний выступает в качестве основной модели. Эта модель называется линейным гармоническим осциллятором.

2. Уравнение свободных колебаний гармонического осциллятора имеет следующий вид:

$\ddot{x}+2\gamma\dot{x}+\omega_{0}^{2}x=0$

где x – переменная, описывающая состояние системы (смещение грузика, заряд конденсатора и т.д.), $\gamma$ – параметр, характеризующий потери энергии (трение в механической системе, сопротивление в контуре), $\omega_{0}$ – собственная частота колебаний, t – время. 

(Обозначения $\ddot{x}=\frac{\partial^{2}x}{\partial t^{2}}$, $\dot{x}=\frac{\partial x}{\partial t}$)

3. Уравнение свободных колебаний гармонического осциллятора есть линейное однородное дифференциальное уравнение второго порядка и оно является примером линейной динамической системы. При отсутствии потерь в системе ($\gamma=0$) вместо уравнения получаем уравнение консервативного осциллятора энергия колебания которого сохраняется во времени. 

$\ddot{x}+\omega_{0}^{2}x=0$.

4. Для однозначной разрешимости уравнения второго порядка необходимо задать два начальных условия вида

$\begin{cases}x(t_{0}) = x_{0}\\\dot{x}(t_{0}) = y_{0}\end{cases}$

Уравнение второго порядка можно представить в виде системы двух уравнений первого порядка:

$\begin{cases}\dot{x} = y\\\dot{y} = -\omega^{2}_{0}x\end{cases}$

Начальные условия для системы двух уравнений первого порядка примут вид:

$\begin{cases}x(t_{0}) = x_{0}\\y(t_{0}) = y_{0}\end{cases}$

5. Независимые переменные x, y определяют пространство, в котором «движется» решение. Это фазовое пространство системы, поскольку оно двумерно, будем называть его фазовой плоскостью.

Значение фазовых координат x, y в любой момент времени полностью определяет состояние системы. Решению уравнения движения как функции времени отвечает гладкая кривая в фазовой плоскости. Она называется фазовой траекторией. Если множество различных решений (соответствующих различным начальным условиям) изобразить на одной фазовой плоскости, возникает общая картина поведения системы. Такую картину, образованную набором фазовых траекторий, называют фазовым портретом.

## Условия моего варианта 

Построить фазовый портрет гармонического осциллятора и решить уравнения гармонического осциллятора для следующих случаев 

1. Колебания гармонического осциллятора без затуханий и без действий внешней силы $\ddot{x}+8x=0$

2. Колебания гармонического осциллятора c затуханием и без действий внешней силы $\ddot{x}+4\dot{x}+3x=0$

3. Колебания гармонического осциллятора c затуханием и под действием внешней силы $\ddot{x}+3\dot{x}+6x=\sin(0,5t)$

На интервале $t\in\left[0; 45\right]$ (шаг 0.05) с начальными условиями $x_{0}=-1, y_{0}=0$.

## Начальные условия

1. Зададим частоту и затухание для 1-го случая (Колебания гармонического осциллятора без затуханий и без действий внешней силы $\ddot{x}+8x=0$): (рис. -@fig:001):

![Частота и затухание для 1-го случая](images\1.png){ #fig:001 width=70% }

Зададим частоту и затухание для 2-го случая (Колебания гармонического осциллятора c затуханием и без действий внешней силы $\ddot{x}+4\dot{x}+3x=0$): (рис. -@fig:002):

![Частота и затухание для 2-го случая](images\2.png){ #fig:002 width=70% }

Зададим частоту и затухание для 3-го случая (Колебания гармонического осциллятора c затуханием и под действием внешней силы $\ddot{x}+3\dot{x}+6x=\sin(0,5t)$): (рис. -@fig:003):

![Частота и затухание для 3-го случая](images\3.png){ #fig:003 width=70% }

2. Зададим правую часть уравнения для 1-го случая (рис. -@fig:004):

![Правая часть уравнения для 1-го случая](images\4.png){ #fig:004 width=70% }

Зададим правую часть уравнения для 2-го случая (рис. -@fig:005):

![Правая часть уравнения для 2-го случая](images\5.png){ #fig:005 width=70% }

Зададим правую часть уравнения для 3-го случая (рис. -@fig:006):

![Правая часть уравнения для 3-го случая](images\6.png){ #fig:006 width=70% }

## Составление систем дифференциальных уравнений и их решения

1. Напишем вектор-функцию для решения системы дифференциальных уравнений для 1-го случая (рис. -@fig:007)

![Вектор-функция для 1-го случая](images\7.png){ #fig:007 width=70% }

Напишем вектор-функцию для решения системы дифференциальных уравнений для 2-го случая (рис. -@fig:008)

![Вектор-функция для 2-го случая](images\8.png){ #fig:008 width=70% }

Напишем вектор-функцию для решения системы дифференциальных уравнений для 3-го случая (рис. -@fig:009)

![Вектор-функция для 3-го случая](images\9.png){ #fig:009 width=70% }

2. Зададим вектор начальных условий, $x(t_{0})=x_{0}$. Он был задан в условии для моего варианта. Для 1-го, 2-го и 3-го случая он одинаковый - [-1 , 0] (рис. -@fig:010)

![Вектор начальных условий для всех 3-х вариантов](images\10.png){ #fig:010 width=70% }

3. Зададим интервал, на котором будем решать задачу и шаг. Интервал и шаг были заданы в условии для моего варианта. Для 1-го, 2-го и 3-го случая они также одинаковы, интервал - [0 , 45], шаг - 0,05 (рис. -@fig:011)

![Интервал и шаг для всех 3-х случаев](images\11.png){ #fig:011 width=70% }

4. Следующая строка считает решения дифференциальных уравнений для случая 1. Решения уравнения с правой частью, заданной ostsilator1, с начальным условием x0_1 на интервале t1 записываются в матрицу u1. (рис. -@fig:012)

![Расчет решений дифференциальных уравнений для случая 1](images\12.png){ #fig:012 width=70% }

Эта строка считает решения дифференциальных уравнений для случая 2. Решения уравнения с правой частью, заданной ostsilator2, с начальным условием x0_2 на интервале t2 записываются в матрицу u2. (рис. -@fig:013)

![Расчет решений дифференциальных уравнений для случая 2](images\13.png){ #fig:013 width=70% }

А эта строка считает решения дифференциальных уравнений для случая 3. Решения уравнения с правой частью, заданной ostsilator3, с начальным условием x0_3 на интервале t3 записываются в матрицу u3. (рис. -@fig:014)

![Расчет решений дифференциальных уравнений для случая 3](images\14.png){ #fig:014 width=70% }

5. Посмотрим массив решений дифференциальных уравнений для варианта 1 (u1) (рис. -@fig:015):

![Массив решений дифференциальных уравнений для варианта 1](images\15.png){ #fig:015 width=70% }

Массив решений дифференциальных уравнений для варианта 2 (u2) (рис. -@fig:016):

![Массив решений дифференциальных уравнений для варианта 2](images\16.png){ #fig:016 width=70% }

И массив решений дифференциальных уравнений для варианта 3 (u3) (рис. -@fig:017):

![Массив решений дифференциальных уравнений для варианта 3](images\17.png){ #fig:017 width=70% }

6. Переписываем отдельно u1 в y1_1, u1' в y1_2 (1-й случай) (рис. -@fig:018):

![Переписывание 1-го случая](images\18.png){ #fig:018 width=70% }

Переписываем отдельно u2 в y2_1, u2' в y2_2 (2-й случай) (рис. -@fig:019):

![Переписывание 2-го случая](images\19.png){ #fig:019 width=70% }

Переписываем отдельно u3 в y3_1, u3' в y3_2 (3-й случай) (рис. -@fig:020):

![Переписывание 3-го случая](images\20.png){ #fig:020 width=70% }

## Построение графиков решений

1. Эти строки строят график красного цвета для 1-го случая - колебания гармонического осциллятора без затуханий и без действий внешней силы $\ddot{x}+8x=0$. (рис. -@fig:021)

![Построение графика колебания гармонического осциллятора без затуханий и без действий внешней силы $\ddot{x}+8x=0$](images\21.png){ #fig:021 width=70% }

2. Оранжевым цветом построен график для колебания гармонического осциллятора c затуханием и без действий внешней силы $\ddot{x}+4\dot{x}+3x=0$. (рис. -@fig:022)

![График колебания гармонического осциллятора c затуханием и без действий внешней силы $\ddot{x}+4\dot{x}+3x=0$](images\22.png){ #fig:022 width=70% }

3. Эти строки строят график зеленого цвета для Колебания гармонического осциллятора c затуханием и под действием внешней силы $\ddot{x}+3\dot{x}+6x=\sin(0,5t)$. (рис. -@fig:023)

![Построение графика боя регулярного войска и партизанского отряда](images\23.png){ #fig:023 width=70% }

## Ответы на вопросы к лабораторной работе 

1. $x=x_{m}\cos(\omega t+\phi_{0})$

2. Систему, совершающую колебания, называют осциллятором. То есть осцилляторы — это такие системы, в которых периодически повторяется какой-нибудь изменяющийся показатель или несколько показателей. Само же слово «осциллятор» происходит от латинского «oscillo» - качаюсь.

3. Уравнение динамики - $\frac{d^{2} \alpha}{d t^{2}} + \frac{g}{L} sin{\alpha} = 0$. В случае малых колебаний - $\frac{d^{2} \alpha}{d t^{2}} + \frac{g}{L} \omega^{2}\alpha = 0$, где $\omega=\sqrt{\frac{g}{L}}$ - круговая частота колебаний.

4. По методу Ранге-Кутты в дифференциальном уравнении второго порядка $\ddot {x} + w^{2}_{0}x = f(t)$ сделаем замену $y = \dot{x}$ и получим систему из двух дифференциальных уравнений первого порядка $\begin{cases} y = \dot{x} \\ \dot{y} = -w^{2}_{0}x \end{cases}$.

5. Простым языком, фазовый портрет — это то, как величины, описывающие состояние системы (динамические переменные), зависят друг от друга. В случае механического движения это координата и скорость, в электричестве это заряд и ток. След от движения изображающей точки называется фазовой траекторией. Через каждую точку фазовой плоскости проходит лишь одна фазовая траектория, за исключением особых точек. Стрелками на фазовых траекториях показывается перемещение изображающей точки с течением времени.

# Выводы

В результате выполнения четвертой лабораторной работы, я рассмотрела модель линейного гармонического осциллятора.

В процессе работы я научилась:

- строить решение уравнения гармонического осциллятора без затухания.
- строить решение уравнения свободных колебаний гармонического осциллятора с затуханием. Строить фазовый портрет гармонических колебаний с затуханием.
- строить решение уравнения колебаний гармонического осциллятора, если на систему действует внешняя сила. Строить фазовый портрет колебаний с действием внешней силы.
