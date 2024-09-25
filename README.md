# MDISUBD
Дубовик Арсений  
гр. 253504  
Тема: Зоопарк  

![DB drawio](https://github.com/user-attachments/assets/af8a2185-f3c9-4f37-84ee-d38bed85fe0f)


Таблицы:  
users:  
UserId(PK, INT, AUTO_INCREMENTED) - уникальный идентификатор пользователя  
Nikname(VARCHAR, UNIQUE, NOT NULL) - никнейм пользователя  
email(VARCHAR, UNIQUE, NOT NULL) - адрес электронной почты   
RoleID(FK, INT, NOT NULL) - роль пользователя  

Role:
RoleID(PK, INT, AUTO_INCREMENTED) - уникальный идентификатор
RoleName(VARCHAR, NOT NULL) - название роли

Department:
DepartmentID(PK, INT, AUTO_INCREMENTED) - уникальный идентификатор
DepartmentName(VARCHAR, NOT NULL) - название отдела

phone:  
PhoneID(PK, INT, AUTO_INCREMENTED) - уникальный идентификатор  
Phone(VARCHAR, UNIQUE, NOT NULL) - номер телефона  
UserID(FK, INT, NOT NULL) - уникальный идентификатор пользователя  

passwd_hash:  
HashID(PK, INT, AUTO_INCREMENTED) - уникальный идентификатор  
Hash(VARCHAR, UNIQUE, NOT NULL) - хеш пароля пользователя  
UserID(FK, INT, NOT NULL) - уникальный идентификатор пользователя  

Log:  
LogID(PK, INT, AUTO_INCREMENTED) - уникальный идентификатор  
UserID(FK, INT, NOT NULL) - уникальный идентификатор пользователя  
Data(VARCHAR, NOT NUL) - данные записи  
Date(DATETIME, NOT NULL) - дата и время записи  

BasketBy:  
BasketID(PK, INT, AUTO_INCREMENTED) - уникальный идентификатор  
Userid(FK, INT, NOT NULL) - уникальный идентификатор пользователя  
ServiceID(FK, INT, NOT NULL) - уникальный идентификатор услуги  
Serviceamount(INT, NOT NULL) - количество услуг  
Date(DATETIME, NOT NULL) - дата и время оказания услуги  

Service:  
ServiceID(PK, INT, AUTO_INCREMENTED) - уникальный идентификатор  
Title(VARCHAR, NOT NULL) - описание услуги  
Price(FLOAT, NOT NNUL) - цена за 1 единицу услуги  
amount(INT, NOT NULL) - количество оставшихся единиц  

Employees:  
EmployeeID(PK, INT, AUTO_INCREMENTED) - уникальный идентификатор  
Name(VARCHAR, NOT NULL) - Имя сотрудника  
Surname(VARCHAR, NOT NULL) - Фамилия сотрудника  
Birth date(DATE, NOT NULL) - Дата рождения  
Sex(VARCHAR, NOT NULL) - Пол  
Salary(FLOAT, NOT NULL) - Зарплата  
UserId(FK, INT, NOT NULL) - идентификатор пользователя сотрудника  

JobTitle:
JobTitleID(PK, INT, AUTO_INCREMENTED) - уникальный идентификатор
Title(VARCHAR, NOT NULL) - Название должности
DepartmentID(FK, INT, NOT NULL) - название отдела

County:  
CountryID(PK, INT, AUTO_INCREMENTED) - уникальный идентификатор  
CountryName(VARCHAR, NOT NULL, UNIQUE) - название Страны  

Family:  
FamilyID(PK, INT, AUTO_INCREMENTED)  - уникальный идентификатор  
FamilyName(VARCHAR, NOT NULL) - название семейства  

Animal:  
AnimalID(PK, INT, AUTO_INCREMENTED) - уникальный идентификатор  
Name(VARCHAR, NOT NULL) - кличка животного  
FamilyID(FK, INT, NOT NULL) - уникальный идентификатор семейства к которому принадлежит животное  
AviaryID(FK, INT, NOT NULL) - уникальный идентификатор вольера животного  
PhotoPath(VARCHAR, NOT NULL) - путь к фото животного  

Aviary:
AviaryID(PK, INT, AUTO_INCREMENTED) - уникальный идентификатор  
Number(INT, UNIQUE, NOT NULL) - номер вольера  
isPond(BOOLEAN, NOT NULL) - идентификатор наличия водоема  
SquareMeters(FLOAT, NOT NULL) - площадь вольера  

Feed:
FeedID(PK, INT, AUTO_INCREMENTED) - уникальный идентификатор  
Type(VARCHAR, NOT NULL, UNIQUE) - тип корма  
calorific_value(FLOAT, NOT NULL) - калорийность корма  
Amount(FLOAT, NOT NULL) - количество оставшегося корма в кг  

Роли:  
Администратор  
Работник  
Посетитель  
Незарегистрированный пользователь  

Функциональность:  
Незарегистрированный пользователь:  
 - Просмотр услуг зоопарка  
 - Просмотр информации о животных зоопарка  
Посетитель:  
 - Просмотр услуг зоопарка  
 - Просмотр информации о животных зоопарка  
 - Купить услугу, отменить покупку, изменить параметры услуги  
Работник:  
 - CRUD относительно животных и информации о них  
 - CRUD относительно корма  
 - CRUD относительно вольеров  
Администратор:  
 - чтение логов  
 - CRUD относительно работников  
 - CRUD относительно должностей  
 - CRUD относительно информации о пользователях  





