# Код для построения реляционных моделей:
### Задача №1
**Вопрос**:
Почему любое отношение в реляционной схеме имеет по крайней мере один ключ?
**Ответ**:
Каждое отношение в реляционной схеме должно иметь хотя бы один ключ, так как именно он позволяет однозначно идентифицировать каждую запись в ней, то есть ключ обеспечивает уникальность записей.
### Задача №2
#### а)
```
@startuml

entity "Copy" as copy {
  * CopyID: integer
  * ISBN: integer
  --
  * ShelfLocation: integer
  ReaderID: integer
}

entity "Book" as book {
  * ISBN: integer
  --
  * Title: string
  * Author: string
  * Year: integer
  * PagesNumber: integer
  * PublishingHouse: string
}

entity "Publishing House" as publishing_house {
  * Name: string
  --
  * Address: string
}

entity "Category" as category {
  * Name: string
  --
  * SuperiorCategory: string
}

entity "Reader" as reader {
  * ReaderID: integer
  --
  * Name: string
  * Surname: string
  * Address: string
  * BirthDate: DATE
  BooksReturnDate: DATE
}

entity "Has Category" as has_category {
  * ISBN: integer
  * Category: string
}

@enduml
```
#### б)
```
@startuml

entity "Flat" {
  * FlatNumber: integer
  --
  * HouseNumber: integer
}

entity "House" {
  * HouseNumber: integer
  --
  * StreetName: string
}

entity "Street" {
  * StreetName: string
  --
  * CityName: string
}

entity "City" {
  * CityName: string
  --
  * CountryName: string
}

entity "Country" {}

@enduml
```

#### в)
```
@startuml

entity Game {
  GameID: integer
  --
  Team1_ID: integer
  Team2_ID: integer
  RefereeID: integer
}

@enduml
```

#### г)
```
@startuml

entity "Person" {
  * PersonID: integer
  --
  * MotherID: integer
  * FatherID: integer
}
```

#### д)
```
@startuml

entity "Entity" {
  * Name: string
}

entity "Entity Attribute" {
  * Name: string
  --
  * EntityName: string
  Key: dtype
  
}

entity "Relationship" {
  * Name: string
  * RelationshipAttributeName: string
  
}

entity "Relationship Attribute" {
  * Name: string
  * RelationshipName: string
}

entity "Connected to" {
  * Entity1: string
  * Entity2: string
  * Relationship: string
}

@enduml
```

### Задача №3

#### а)
```
@startuml

entity "City" {
  * Name: sting
  * Region: string
}

entity "Station" {
  * Name: string
  --
  * Tracks: integer
  * Lies_in: string
}

entity "Train" {
  * TrainNr: integer
  --
  * Length: integer
  * Start: string
  * End: string
}

entity "Connected" {
  * Departure: string
  * Arrival: string
  * TrainNr: integer
}

@enduml
```

#### б)
```
@startuml

entity "Station Personnel" {
  * PersNr: integer
  --
  * Name: string
  * StatNr: integer
}

entity "Doctor" {
  * Area: string
  * Rank: integer
}

entity "Caregiver" {
  * Qualification: string
}

entity "Category of Personnel" {
  * PersNr: integer
  * Category: string
}

entity "Patient" {
  * PatientNr: integer
  --
  * Name: string
  * Disease: string
  * DoctorNr: integer
}

entity "Station" {
  * StatNr: integer
  --
  * Name: string
}

entity "Room" {
  * StatNr: integer
  * RoomNr: integer
  --
  * Beds
}

entity "Admission" {
  * StatNr: integer
  * RoomNr: integer
  * PatientNr: integer
  --
  * From: integer
  * To: integer
}

@enduml
```
