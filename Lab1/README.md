# Введение в R
## Цель
1. Развить практические навыки использования языка программирования R для
обработки данных
2. Развить навыки работы в Rstudio IDE:
установка пакетов
работа с проектами в Rstudio
настройка и работа с Git
3. Закрепить знания базовых типов данных языка R и простейших операций с ними
## Исходные данные
Ноутбук с ОС Windows и доступом в  сеть интернет
## План
1. Установить интерпретатор R
2. Установить Rstudio IDE
3. Установить программный пакет swirl:
через интерфейс Rstudio IDE
или функцией R install.packages("swirl")
4. Запустить задание с помощью swirl::swirl()
5. Выбрать из меню курсов 1. R Programming: The
basics of programming in R
6. Запустить подкурсы и выполнить:
базовые структурные блоки (Basic Building
Blocks)
рабочие пространства и файлы (Workspace and
Files)
последовательности чисел (Sequences of
Numbers)
векторы (Vectors)
пропущенные значения (Missing Values)
## Шаги
1. Установить интерпретатор R

![image](https://github.com/user-attachments/assets/5f7cb29c-60ce-40f5-99cb-75a13dfa48d9)

2. Установить Rstudio IDE
![image](https://github.com/user-attachments/assets/09ee679e-430f-4304-8d6a-5b0b2848a4b9)
![image](https://github.com/user-attachments/assets/90baf604-5a26-452f-9fe9-e638d426b732)

![image](https://github.com/user-attachments/assets/06a501f1-fe76-4ffe-94ba-fb8fbb6da494)

3. Установить программный пакет swirl:
через интерфейс Rstudio IDE
или функцией R install.packages("swirl")

![image](https://github.com/user-attachments/assets/d522a48c-3a98-45f7-9b41-5c5fd7d38cc5)

![image](https://github.com/user-attachments/assets/d5961280-d892-4b2a-b0ec-67d3c1f01f9d)

4. Запустить задание с помощью swirl::swirl()    
 ![image](https://github.com/user-attachments/assets/ed9e2ba4-019a-48c8-8ef6-a80bc1a36156)

 5. Выбрать из меню курсов 1. R Programming: The
basics of programming in R
![image](https://github.com/user-attachments/assets/3b06a1b5-832e-43d7-bfaa-4daeef544d6a)

6. Запустить подкурсы и выполнить:
базовые структурные блоки (Basic Building
Blocks)

рабочие пространства и файлы (Workspace and
Files)
последовательности чисел (Sequences of
Numbers)
векторы (Vectors)
пропущенные значения (Missing Values) <br />
6.1 Выполнение  Basic Building
Blocks <br />
``` 5 + 7
    5 - 7
    5 / 7
    5 * 7
    8 + 2 - 10 / 43
    x <- 5 + 7
    x
    y <- x - 3
    y
    z <- c(1.1, 9, 3.14)
    ?c
    c(z, 555, z)
    z * 2 + 100
    my_sqrt <- sqrt(z - 1)
    my_sqrt
    my_div <- z / my_sqrt
    my_div
    c(1, 2, 3, 4) + c(0, 10)
    c(1, 2, 3, 4) + c(0, 10, 100)
    z * 2 + 1000
    my_div
```
6.2 Выполнение  Sequences of
Numbers  <br />
```  1:20
     pi:10
     ?pi
     15:1
     ?`:`
     seq(1, 20)
     seq(from = 1, to = 20)
     seq(0, 10, by = 0.5)
     my_seq <- seq(5, 10, length = 30)
     length(my_seq)
     1:length(my_seq)
     seq(along.with = my_seq)
     seq_along(my_seq)
     rep(0, times = 40)
     rep(c(0, 1, 2), times = 10)
     rep(c(0, 1, 2), each = 10)
```
6.3 Выполнение   Missing Values  <br />
``` x <- c(44, NA, 5, NA)
    x * 3
    y <- rnorm(100)
    y[y < 0] <- NA
    my_na <- is.na(y)
    my_na
    y == NA
    sum(my_na)
    TRUE
    0/0
    Inf - Inf
```
## Оценка результата
Был установлен R studio 
Были пройдены подкурсы Basic Building
Blocks, Sequences of
Numbers, Missing Values
## Вывод
Были развиты практические навыки использования языка программирования R для
обработки данных
Были развиты навыки работы в Rstudio IDE:
установка пакетов
Были закреплены знания базовых типов данных языка R и простейших операций с ними
