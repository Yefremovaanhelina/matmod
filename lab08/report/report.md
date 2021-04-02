﻿---
# Front matter
lang: ru-RU
title: "Лабораторная работа 8"
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

Цель восьмой лабораторной работы - рассмотреть модель конкуренции двух фирм.

# Задание

## Построить графики изменения оборотных средств фирмы 1 и фирмы 2 без учета постоянных издержек и с веденной нормировкой для случая 1.

## Построить графики изменения оборотных средств фирмы 1 и фирмы 2 без учета постоянных издержек и с веденной нормировкой для случая 2.

# Выполнение лабораторной работы

## Теоретическая справка

Модель одной фирмы:

1. Для построения модели конкуренции хотя бы двух фирм необходимо рассмотреть модель одной фирмы. Вначале рассмотрим модель фирмы, производящей продукт долговременного пользования, когда цена его определяется балансом спроса и предложения. Примем, что этот продукт занимает определенную нишу рынка и конкуренты в ней отсутствуют. 

2. Обозначим:

N – число потребителей производимого продукта.

S – доходы потребителей данного продукта. Считаем, что доходы всех потребителей одинаковы. Это предположение справедливо, если речь идет об одной рыночной нише, т.е. производимый продукт ориентирован на определенный слой населения.

M – оборотные средства предприятия

τ – длительность производственного цикла

p – рыночная цена товара

p̃ – себестоимость продукта, то есть переменные издержки на производство единицы продукции.

δ – доля оборотных средств, идущая на покрытие переменных издержек.

κ – постоянные издержки, которые не зависят от количества выпускаемой продукции.

3. Q(S/p) – функция спроса, зависящая от отношения дохода S к цене p. Она равна количеству продукта, потребляемого одним потребителем в единицу времени.

Функцию спроса товаров долговременного использования часто представляют в простейшей форме:

$Q = q - k \frac{P}{S} = q(1 - \frac{p}{p_{cr}}),$

где q – максимальная потребность одного человека в продукте в единицу времени. Эта функция падает с ростом цены и при $p=p_{cr}$ (критическая стоимость продукта) потребители отказываются от приобретения товара. Величина $p_{cr}=Sq/k$. Параметр k – мера эластичности функции спроса по цене. Таким образом, функция спроса в форме является пороговой (то есть, Q(S/p) = 0 при $p\geq p_{cr}$) и обладает свойствами насыщения.

4. Уравнения динамики оборотных средств можно записать в виде

$\frac{\partial M}{\partial t} = -\frac{M \delta}{\tau} + NQp - \kappa = -\frac{M \delta}{\tau} + NQ(1 - \frac{p}{p_{cr}})p - \kappa$

Уравнение для рыночной цены p представим в виде

$\frac{\partial p}{\partial t} = \gamma (-\frac{M \delta}{\tau \tilde{p}} + NQ(1 - \frac{p}{p_{cr}})$

Первый член соответствует количеству поставляемого на рынок товара (то есть, предложению), а второй член – спросу. 

Параметр γ зависит от скорости оборота товаров на рынке. Как правило, время торгового оборота существенно меньше времени производственного цикла τ. При заданном M уравнение описывает быстрое стремление цены к равновесному значению цены, которое устойчиво.

5. В этом случае уравнение можно заменить алгебраическим соотношением

$-\frac{M \delta}{\tau \tilde{p}} + NQ(1 - \frac{p}{p_{cr}}) = 0$

Из этого следует, что равновесное значение цены p равно

$p = p_{cr}(1 - \frac{M \delta}{\tau \tilde{p} Nq})$

Уравнение с учетом предыдущего приобретает вид

$\frac{\partial M}{\partial t} = M \frac{\delta}{\tau}(\frac{p_{cr}}{\tilde{p}} - 1) - M^2 (\frac{\delta}{\tau \delta{p}})^2 \frac{p_{cr}}{Nq} - \kappa$

Уравнение имеет два стационарных решения, соответствующих условию $\partial M / \partial t = 0$:

$\tilde{M}_{1,2} = \frac{1}{2}a \pm \sqrt{\frac{a^2}{4} - b}$,

где

$a = Nq(1 - \frac{\tilde{p}}{p_{cr}}) \tilde{p} \frac{\tau}{\delta}, b = \kappa Nq \frac{(\tau \tilde{p})^2}{p_{cr} \delta^2}$

6. Из этого следует, что при больших постоянных издержках (в случае $a^{2}<4b$) стационарных состояний нет. Это означает, что в этих условиях фирма не может функционировать стабильно, то есть, терпит банкротство. Однако, как правило, постоянные затраты малы по сравнению с переменными (то есть, $b<<a^{2}$) и играют роль, только в случае, когда оборотные средства малы. При b << a стационарные значения M равны

$\tilde{M}_+ = Nq \frac{\tau}{\delta}(1 - \frac{\tilde{p}}{p_{cr}}) \tilde{p}, \tilde{M}_- = \kappa \tilde{p} \frac{\tau}{\delta(p_{cr} - \tilde{p})}$

7. Первое состояние $\tilde{M}_+$ устойчиво и соответствует стабильному функционированию предприятия. Второе состояние $\tilde{M}_-$ неустойчиво, так что при $M < \tilde{M}_-$ оборотные средства падают ($\partial M / \partial t < 0$), то есть, фирма идет к банкротству. По смыслу $\tilde{M}_-$ соответствует начальному капиталу, необходимому для входа в рынок.

В обсуждаемой модели параметр $\delta$ всюду входит в сочетании с $\tau$. Это значит, что уменьшение доли оборотных средств, вкладываемых в производство, эквивалентно удлинению производственного цикла. Поэтому мы в дальнейшем положим: $\delta$ = 1, а параметр $\tau$ будем считать временем цикла, с учётом сказанного.

Конкуренция двух фирм:

1. Рассмотрим две фирмы, производящие взаимозаменяемые товары одинакового качества и находящиеся в одной рыночной нише. Последнее означает, что у потребителей в этой нише нет априорных предпочтений, и они приобретут тот или иной товар, не обращая внимания на знак фирмы.

В этом случае, на рынке устанавливается единая цена, которая определяется балансом суммарного предложения и спроса. Иными словами, в рамках нашей модели конкурентная борьба ведётся только рыночными методами. То есть, конкуренты могут влиять на противника путем изменения параметров своего производства: себестоимость, время цикла, но не могут прямо вмешиваться в ситуацию на рынке («назначать» цену или влиять на потребителей каким-либо иным способом.)

2. Уравнения динамики оборотных средств запишем в виде

$\frac{\partial M_1}{\partial t} = - \frac{M_1}{\tau_1} + N_1q(1 - \frac{p}{p_{cr}})p - \kappa_1 \\ \frac{\partial M_2}{\partial t} = - \frac{M_2}{\tau_2} + N_2q(1 - \frac{p}{p_{cr}})p - \kappa_2$

где использованы те же обозначения, а индексы 1 и 2 относятся к первой и второй фирме, соответственно. Величины $N_1$ и $N_2$ – числа потребителей, приобретших товар первой и второй фирмы.

3. Учтем, что товарный баланс устанавливается быстро, то есть, произведенный каждой фирмой товар не накапливается, а реализуется по цене p. Тогда

$\frac{M_1}{\tau_1 \tilde{p}_1} = - N_1q(1 - \frac{p}{p_{cr}}) \\ \frac{M_2}{\tau_2 \tilde{p}_2} = - N_2q(1 - \frac{p}{p_{cr}})$

где $\tilde{p}_1$ и $\tilde{p}_2$ – себестоимости товаров в первой и второй фирме.

4. Представим уравнение выше в виде

$\frac{\partial M_1}{\partial t} = - \frac{M_1}{\tau_1}(1 - \frac{p}{\tilde{p}_1}) - \kappa_1 \\ \frac{\partial M_2}{\partial t} = - \frac{M_2}{\tau_2}(1 - \frac{p}{\tilde{p}_2}) - \kappa_2$

Уравнение для цены, 

$\frac{\partial p}{\partial t} = - \gamma (\frac{M_1}{\tau_1 \tilde{p}_1} + \frac{M_2}{\tau_2 \tilde{p}_2} - Nq (1 - \frac{p}{p_{cr}})$

5. Считая, как и выше, что ценовое равновесие устанавливается быстро, получим:

$p = p_{cr} (1 - \frac{1}{Nq} (\frac{M_1}{\tau_1 \tilde{p}_1} + \frac{M_2}{\tau_2 \tilde{p}_2}))$

Подставив это уравнение в предыдущее имеем:

$\frac{\partial M_1}{\partial t} = c_1 M_1 - b M_1 M_2 - a_1 M_1^2 - \kappa_1 \\ \frac{\partial M_2}{\partial t} = c_2 M_2 - b M_1 M_2 - a_2 M_2^2 - \kappa_2$

где

$a_1 = \frac{p_{cr}}{\tau_1^2 \tilde{p}_1^2 Nq}, a_2 = \frac{p_{cr}}{\tau_2^2 \tilde{p}_2^2 Nq}, b = \frac{p_{cr}}{\tau_1^2 \tilde{p}_1^2 \tau_2^2 \tilde{p}_2^2 Nq}, c_1 = \frac{p_{cr} - \tilde{p}_1}{\tau_1^2 \tilde{p}_1^2}, c_2 = \frac{p_{cr} - \tilde{p}_2}{\tau_2^2 \tilde{p}_2^2}$

6. Исследуем систему выше в случае, когда постоянные издержки ($κ_1, κ_2$) пренебрежимо малы. И введем нормировку $t = c_1 \theta$. Получим следующую систему:

$\frac{\partial M_1}{\partial \theta} = M_1 - \frac{b}{c_1} M_1 M_2 - \frac{a_1}{c_1} M_1^2 \\ \frac{\partial M_2}{\partial \theta} = \frac{c_2}{c_1} M_2 -\frac{b}{c_1} M_1 M_2 - \frac{a_2}{c_1} M_2^2$

7. Чтобы решить систему, необходимо знать начальные условия. Зададим
начальные значения $M_0^1$, $M_0^2$ и известные параметры: $p_{cr}$, 
$\tau_1$, $\tau_2$, $\tilde{p}_1$, $\tilde{p}_2$, $N$, $q$

8. Замечание: 

Значения $p_{cr}, \tilde{p}_{1,2} , N$, указаны в тысячах единиц, а значения $M_{1,2}$ указаны в млн. единиц.

## Начальные условия

1. Зададим критическую стоимость продукта (p_cr), длительность производственного цикла фирмы 1 (tau1), себестоимость продукта у фирмы 1 (p1), длительность производственного цикла фирмы 2 (tau2), себестоимость продукта у фирмы 2 (p2), число потребителей производимого продукта (N), максимальную потребность одного человека в продукте в единицу времени (q) (рис. -@fig:001).

![Начальные параметры](images\1.png){ #fig:001 width=70% }

2. Зададим коэффициенты а1, а2, в, с1, с2 для уравнений динамики изменения объемов продаж фирм (рис. -@fig:002).

![Коэффициенты а1, а2, в, с1, с2](images\2.png){ #fig:002 width=70% }

3. Зададим стационарные точки м1 и м2 (рис. -@fig:003).

![Стационарные точки](images\3.png){ #fig:003 width=70% }

## Составление систем дифференциальных уравнений и их решения

1. Напишем вектор-функцию sluchai1 для решения системы дифференциальных уравнений для случая 1 (рис. -@fig:004).

![Уравнение для случая 1](images\4.png){ #fig:004 width=70% }

2. Напишем вектор-функцию sluchai2 для решения системы дифференциальных уравнений для случая 2 (рис. -@fig:005).

![Уравнение для случая 2](images\5.png){ #fig:005 width=70% }

3. Зададим интервал, на котором будем решать задачу и шаг. Задам интервал - [0 , 20] и шаг - 0,01 (рис. -@fig:006).

![Интервал и шаг](images\6.png){ #fig:006 width=70% }

4. Зададим начальное значение объема оборотных средств x1 и х2 (рис. -@fig:007).

![Объем оборотных средств](images\7.png){ #fig:007 width=70% }

5. Следующая строка считает решения дифференциальных уравнений для случая 1 (рис. -@fig:008):

![Решения дифференциальных уравнений для случая 1](images\8.png){ #fig:008 width=70% }

6. Следующая строка считает решения дифференциальных уравнений для случая 2 (рис. -@fig:009):

![Решения дифференциальных уравнений для случая 2](images\9.png){ #fig:009 width=70% }

7. Посмотрим массив решений u1 (рис. -@fig:010):

![Массив решений u1](images\10.png){ #fig:010 width=70% }

8. Посмотрим массив решений u2 (рис. -@fig:011):

![Массив решений u2](images\11.png){ #fig:011 width=70% }

## Построение графиков решений

1. Эти строки строят график изменения оборотных средств фирмы 1 и фирмы 2 без учета постоянных издержек и с веденной нормировкой для случая 1 (рис. -@fig:012):

![График случая 1](images\12.png){ #fig:012 width=70% }

2. Эти строки строят график изменения оборотных средств фирмы 1 и фирмы 2 без учета постоянных издержек и с веденной нормировкой для случая 2 (рис. -@fig:013):

![График случая 2](images\13.png){ #fig:013 width=70% }

# Выводы

В результате выполнения восьмой лабораторной работы, я рассмотрела модель модель конкуренции двух фирм.

В процессе выполнения лабораторной работы я научилась:

- строить строить графики изменения оборотных средств фирмы 1 и фирмы 2 без учета постоянных издержек и с веденной нормировкой для случая 1.

- строить графики изменения оборотных средств фирмы 1 и фирмы 2 без учета постоянных издержек и с веденной нормировкой для случая 2.
