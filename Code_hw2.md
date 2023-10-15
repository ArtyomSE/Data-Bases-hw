# Код для построения ER-диаграмм:

### Задача №1:
```
@startuml

entity "Экземпляр" as copy {
  * ID_копии
  * ISBN
  --
  * Положение на полке
  
}

entity "Книга" as book {
  * ISBN
  --
  * Название
  * Автор
  * Год
  * Количество страниц
}

entity "Издательство" as publishing_house {
  * Название
  --
  * Адрес
}

entity "Категория" as category {
  * Название
}

entity "Читатель" as reader {
  * ID_читателя
  --
  * Имя
  * Фамилия
  * Адрес
  * День рождения
  Даты возврата книг
}

category ||--|{ category: подчиняет
book }|--|{ category: имеет
book ||--|{ copy: представлена в
reader ||--|{ copy: берёт
publishing_house ||--|{ book: издаёт

@enduml
```

### Задача №2:
#### а)
```
@startuml

entity "Квартира" as flat {}

entity "Дом" as house {}

entity "Улица" as street {}

entity "Город" as city {}

entity "Страна" as country {}

flat }|--|| house: расположена

house }|--|| street: расположен

street }|--|| city: расположена

city  }|--|| country: расположен

@enduml
```

#### б)
```
@startuml

entity "Арбитр" as referee {}

entity "Команда №1" as team1 {}

entity "Команда №2" as team2 {}

team1 ||--|| team2: играет против
referee ||--|| team1: судит
referee ||--|| team2: судит

@enduml
```

#### в)
```
@startuml

entity "Человек" as man {}

entity "Мать" as mother {}

entity "Отец" as father {}

mother ||--|{ man: имеет
father ||--|{ man: имеет

@enduml
```

### Задача №3:
```
@startuml

entity "Сущность" as entity {}

entity "Связь" as relationship {}

entity "Атрибут" as attribute {}

entity ||--|{ attribute: обладает

entity ||--|{ relationship: имеет

@enduml
```
