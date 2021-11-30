# table
Рассмотрим прямоугольную таблицу размером `n`×`m`. Занумеруем строки таблицы числами от `1` до `n`, а столбцы – числами от `1` до `m`. Будем такую таблицу последовательно заполнять числами следующим образом.

Обозначим через `a[i][j]` число, стоящее на пересечении `i`-ой строки и `j`-ого столбца. Первая строка таблицы заполняется заданными числами – `a[1][1]`, `a[1][2]`, …, `a[1][m]`. Затем заполняются строки с номерами от `2` до `n`. Число `a[i][j]` вычисляется как сумма всех чисел таблицы, находящихся в «треугольнике» над элементом `a[i][j]`. Все вычисления при этом выполняются по модулю `r`, то есть мы считает остаток от деления суммы на `r`.

![пояснение](https://github.com/py-is-hse-21/table/blob/main/image2.PNG)

Более точно, значение `a[i][j]` вычисляется по следующей формуле:

![формула](https://github.com/py-is-hse-21/table/blob/main/image1.PNG)

Например, если таблица состоит из трех строк и четырех столбцов, и первая строка состоит из чисел `2,3,4,5`, а `r = 40` то для этих исходных данных таблица будет выглядеть следующим образом (взятие по модулю показано только там, где оно приводит к изменению числа):

![пример](https://github.com/py-is-hse-21/table/blob/main/image3.PNG)

Требуется написать программу, которая по заданной первой строке таблицы `(a[1][1], a[1][2], …, a[1][m])`, вычисляет **последнюю** строку, как описано выше. Так как числа `m` и `n` достаточно большие - программа должна быть оптимальной по памяти и времени выполнения.

Примеры:

вход (n=2, m=3, r=10, a1=[1,2,3]) -> [3,6,5]

    1 2 3
    3 6 5

вход (n=3, m=3, r= 10, a1=[1,1,1]) -> [8, 0, 8]

    1 1 1
    2 3 2
    8 0 8

вход (n=3, m=4, r=40, [2,3,4,5]) -> [23,0,4,33]
