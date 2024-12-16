# Основы обработки данных с помощью R и Dplyr
## Цель
1. Развить практические навыки использования языка программирования R для
обработки данных
2. Закрепить знания базовых типов данных языка R
3. Развить практические навыки использования функций обработки данных пакета
dplyr – функции select(), filter(), mutate(), arrange(), group_by()
## Исходные данные
Ноутбук с ОС windows 10 и программное обеспесчение RStudio
## План
Проанализировать встроенные в пакет nycflights13 наборы данных с помощью
языка R и ответить на вопросы
## Шаги

1.Загрузить данные.  <br   />
``` install.packages("nycflights13") ```  <br   />
2.Ответить на вопросы. <br   />
2.1. Сколько встроенных в пакет nycflights13 датафреймов? <br   />
```
2.2. Сколько строк в каждом датафрейме? < br   />
```  row_counts <- sapply(ls("package:nycflights13"), function(x) nrow(get(x))) ```
2.3. Сколько столбцов в каждом датафрейме? <br   />
``` col_counts <- sapply(ls("package:nycflights13"), function(x) ncol(get(x))) ```
2.4. Как просмотреть примерный вид датафрейма? <br   />
``` glimpse(flights) ```
2.5. Сколько компаний-перевозчиков (carrier) учитывают эти наборы данных
(представлено в наборах дан- ных)? <br   />
``` unique_carriers <- unique(flights$carrier)
    num_carriers <- length(unique_carriers)
```
2.6. Сколько рейсов принял аэропорт John F Kennedy Intl в мае? <br   />
``` jfk_flights_may <- flights %>%
    filter(dest == "JFK", month == 5) %>%
    nrow()
```
2.7. Какой самый северный аэропорт? <br   />
``` northern_airport <- airports %>%
     filter(lat == max(lat, na.rm = TRUE))
```
2.8. Какой аэропорт самый высокогорный (находится выше всех над уровнем моря)? <br   />
``` 
```
2.9. Какие бортовые номера у самых старых самолетов? <br   />
```  oldest_planes <- planes %>%
     filter(year == min(year, na.rm = TRUE)) %>%
     select(tailnum)
```
2.10. Какая средняя температура воздуха была в сентябре в аэропорту John F
Kennedy Intl (в градусах Цельсия). <br   />
``` avg_temp_september_jfk <- weather %>%
     filter(month == 9, origin == "JFK") %>%
    summarise(average_temp = mean(temp, na.rm = TRUE))
    print(avg_temp_september_jfk)
```
2.11. Самолеты какой авиакомпании совершили больше всего вылетов в июне? <br   />
``` top_carrier_june <- flights %>%
    filter(month == 6) %>%
     count(carrier) %>%
     arrange(desc(n)) %>%
     slice(1)
 print(top_carrier_june)
```
2.12. Самолеты какой авиакомпании задерживались чаще других в 2013 году? <br   />
```
flights %>% filter(dep_delay > 0 & year == 2013) %>% count(carrier, sort = TRUE)
```
## Оценка результата
Были даны ответы на заданные вопросы
## Вывод
Были развиты практические навыки использования языка программирования R для
обработки данных. Были закреплены знания базовых типов данных языка R. Были развиты  практические навыки использования функций обработки данных пакета
dplyr – функции select(), filter(), mutate(), arrange(), group_by()
