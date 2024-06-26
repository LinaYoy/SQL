# Роговая Ангелина ИС-22/9-1

## Описание 
Эта база данных разработана для хранения информации о картинной галерее. База данных содержит таблицы для хранения информации о художниках, картинах, выставках и их расположение.

![](<img src="C:\Users\IS22-9-1\Desktop\foto\image.png" style="height: 100px; width: 100px;"/>)

### Таблица "Artists" (Художники)

- **Artists_id**: уникальный идентификатор художника (PRIMARY KEY)
- **name**: имя художника (VARCHAR(30))
- **birthday**: дата рождения художника (TEXT)
- **genre**: жанр творчества художника (VARCHAR(30))

Пример вывода записей из таблицы "Artists":
SELECT * FROM Artists;


### Таблица "Exposed" (Экспозиции)

- **Exposed_id**: уникальный идентификатор экспозиции (PRIMARY KEY)
- **hall**: название зала, где проводится экспозиция (VARCHAR(30))
- **paintings_id**: идентификатор картины, выставленной на экспозиции (FOREIGN KEY REFERENCES Paintings(id))

Пример вывода записей из таблицы "Exposed":
SELECT * FROM Exposed;


### Таблица "Expositions" (Выставки)

- **Expositions_id**: уникальный идентификатор выставки (PRIMARY KEY)
- **theme**: тема выставки (VARCHAR(30))
- **begining**: дата начала выставки (DATE)
- **ending**: дата окончания выставки (DATE)
- **exposed_id**: идентификатор экспозиции на выставке (FOREIGN KEY REFERENCES Exposed(id))

Пример вывода записей из таблицы "Expositions":
SELECT * FROM Expositions;


### Таблица "Paintings" (Картины)

- **Paintings_id**: уникальный идентификатор картины (PRIMARY KEY)
- **name**: название картины (VARCHAR(30))
- **date_of_writing**: дата написания картины (DATE)
- **artists_id**: идентификатор художника, создавшего картину (FOREIGN KEY REFERENCES Artists(id))

Пример вывода записей из таблицы "Paintings":
SELECT * FROM Paintings;