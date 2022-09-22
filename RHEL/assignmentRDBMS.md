# Assignment RDBMS

## 1a. Create the tables mentioned mentioned in following schema. 

### Hotel (hotelNo, name, address)
- Name needs to be changed to `hName`
```sql
-- create a table named hotel

CREATE TABLE  hotel(
hotelNo varchar(15),
hName varchar(20),
adddress varchar(25),

primary key (hotelNo)
);
```

### Room (roomNo, hotelNo, type, price) 

```sql
CREATE TABLE room (
    roomNo numeric(5),
    hotelNo varchar(15),
    type varchar(10),
    price decimal (5,2),
    primary key (roomNo, hotelNo),
    foreign key (hotelNo) REFERENCES hotel (hotelNo)
);
```

### Booking (hotelNo, guestNo, dateFrom, dateTo, roomNo)


```sql
CREATE TABLE booking(
hotelNo varchar(10),
guestno numeric(5),
dateFrom date,
dateTo date,
roomNo numeric(5),

primary key (hotelNo, guestNo, dateFrom),
foreign key (roomNo, hotelNo) REFERENCES room(roomNo, hotelNo),
foreign key (guestNo) REFERENCES guest(guestNo)

);


```

### Guest (guestNo, name, address)
- Name needs to be changed to `gName` and `gAddress`

```sql 
CREATE TABLE  guest(
guestNo numeric(5),
gName varchar(20),
gAddress varchar(50),
primary key (guestNo)
);

```
### Adding Data 
```sql 
INSERT into hotel values('fb01', 'Grosvenor', 'London');
insert into hotel values('fb02', 'Watergate', 'Paris');

INSERT into room values(101, 'fb01', 'single', 20);
insert into guest values(10001, 'John Kay', '56 High St, London');

insert into booking values('fb01', 10001, '04-04-01', '04-04-08', 501);
```

