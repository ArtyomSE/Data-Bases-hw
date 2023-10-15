# Построение реляционных моделей:
### Задача №1
**Вопрос**: почему любое отношение в реляционной схеме имеет по крайней мере один ключ?

**Ответ**: каждое отношение в реляционной схеме должно иметь хотя бы один ключ, так как именно он позволяет однозначно идентифицировать каждую запись в ней, то есть ключ обеспечивает уникальность записей.
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
![2 1](https://github.com/ArtyomSE/Data-Bases-hw/assets/99038798/1f65b9bd-07f2-489c-9eb4-fc684c798f7f)

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

entity "Country" {
  * CountryName: string
}

@enduml
```
![2 2](https://github.com/ArtyomSE/Data-Bases-hw/assets/99038798/ca3cf22d-4c4d-4b1f-b7d5-c07b1dcb482e)

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
![2 3](https://github.com/ArtyomSE/Data-Bases-hw/assets/99038798/56ee8507-b8cc-411e-be14-2711abf3d3fe)

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
![2 4](https://github.com/ArtyomSE/Data-Bases-hw/assets/99038798/6e535048-88fc-4518-9608-3bf8ca17f4b1)

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
![2 5](https://github.com/ArtyomSE/Data-Bases-hw/assets/99038798/341fcea1-2a82-4007-ac99-fbf4f5bd55c7)

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
![3 1](https://github.com/ArtyomSE/Data-Bases-hw/assets/99038798/932bcb36-1830-4868-9a3d-d0e060209701)

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
![3 2](https://github.com/ArtyomSE/Data-Bases-hw/assets/99038798/556e7fe3-1ac4-4a5d-a349-70103639c809)
