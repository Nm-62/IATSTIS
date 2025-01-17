# Основы обработки данных с помощью R и Dplyr
mf-maill@yandex.ru
## Цель
1. Развить практические навыки использования языка программирования R для
обработки данных
2. Закрепить знания базовых типов данных языка R
3. Развить практические навыки использования функций обработки данных пакета
dplyr – функции select(), filter(), mutate(), arrange(), group_by()
## Исходные данные
Ноутбук с ОС windows 10 и программное обеспесчение RStudio
## План
Проанализировать встроенный в пакет dplyr набор данных starwars с помощью
языка R и ответить на вопросы

## Шаги
 1. Сколько строк в датафрейме?<br   />
``` n_rows <- starwars %>% nrow()
    print(n_rows)
```

 3. Сколько столбцов в датафрейме?<br   />
```  n_cols <- starwars %>% ncol()
     print(n_cols)
```

 5. Как просмотреть примерный вид датафрейма?<br   />
``` head(starwars) ```

 6. Сколько уникальных рас персонажей (species) представлено в данных?<br   />
``` unique_species <- starwars %>% 
     select(species) %>%
     distinct() %>%
     nrow()
     print(unique_species)
```
 5. Найти самого высокого персонажа.<br   />
``` tallest_character <- starwars %>% 
     filter(height == max(height, na.rm = TRUE))  
     print(tallest_character)
```
 6. Найти всех персонажей ниже 170 <br   />
``` short_characters <- starwars %>% 
    filter(height < 170)
    print(short_characters)
```
 7. Подсчитать ИМТ (индекс массы тела) для всех персонажей.<br   />
``` starwars <- starwars %>%
    mutate(BMI = mass / (height/100)^2)
    print(starwars %>% select(name, BMI))
```
 8. Найти 10 самых “вытянутых” персонажей. “Вытянутость” оценить по отношению 
массы (mass) к росту (height) персонажей.<br   />
``` elongation <- starwars %>% 
     mutate(elongation = mass / height) %>% 
    arrange(desc(elongation)) %>% 
    slice_head(n = 10)
    print(elongation)
```
 9. Найти средний возраст персонажей каждой расы вселенной Звездных войн.<br   />
``` starwars %>% filter(!is.na(species) & !is.na(birth_year)) %>% group_by(species) %>% summarise(average_age = mean(birth_year, na.rm = TRUE))
```

 10. Найти самый распространенный цвет глаз персонажей вселенной Звездных
войн.<br   />
``` most_common_eye_color <- starwars %>% 
   count(eye_color) %>% 
     arrange(desc(n)) %>% 
     slice_head(n = 1) 
     print(most_common_eye_color)
```
 11. Подсчитать среднюю длину имени в каждой расе вселенной Звездных войн.<br   />
``` average_name_length_by_species <- starwars %>% 
    mutate(name_length = nchar(name)) %>% 
    group_by(species) %>% 
    summarise(average_name_length = mean(name_length, na.rm = TRUE)) 
    print(average_name_length_by_species)
``` 
## Оценка результата
В процессе работы были даны ответы на заданные вопросы 
## Вывод
Были развиты  практические навыки использования языка программирования R для
обработки данных. Были закрепелены знания базовых типов данных языка R. Были развиты практические навыки использования функций обработки данных пакета
dplyr – функции select(), filter(), mutate(), arrange(), group_by()
