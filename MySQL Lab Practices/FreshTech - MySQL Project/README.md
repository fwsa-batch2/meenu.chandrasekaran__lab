# &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```FreshTech App```

<hr>

###### Creation of database - 'FreshTech'

 ```create database FreshTech;```

###### Using database - FreshTech

```use FreshTech;``` 

<hr>

###### Creation of table 1 - 'users'

```create table users(user_id tinyint primary key auto_increment,user_name varchar(20) not null check(length(user_name)>=3),user_mailId varchar(50) not null unique check(user_mailId like("_%@gmail.com")),user_password varchar(15) not null check(validate_password_strength(user_password)=100),join_date date not null);```

<br>

```desc users;```

![describe users](https://user-images.githubusercontent.com/93571047/158520349-7827c435-6bd9-4956-93a6-c7edebde1bfc.png)

###### Insertion of Records into 'users' table

 
 ```insert into users(user_name,user_mailId,user_password,join_date) values("Chitra Muthukumaran","chitram@gmail.com","Chitra@1234","2007/09/24");```

 ```insert into users(user_name,user_mailId,user_password,join_date) values("Revathi Iyer","revathiiyer@gmail.com","Revathi@1234","1998/12/12");```
 
 ```insert into users(user_name,user_mailId,user_password,join_date) values("Prasanna Bharathi","prasannabharathi@gmail.com","Prasanna@1234","2010/12/12");```

 ```insert into users(user_name,user_mailId,user_password,join_date) values("Shyam","shanmugaanantharaman@gmail.com","Shyam@1234","2010/12/12");```

 ```insert into users(user_name,user_mailId,user_password,join_date) values("Deepak Panneerselvam","deepak@gmail.com","Deepak@1234","2021/10/04");```

 ```insert into users(user_name,user_mailId,user_password,join_date) values("Kasi Antony","kasi@gmail.com","Kasi@1234","2021-10-04"),("Keerthana","keerthana@gmail.com","Keerthi@1234","2021-10-04"),("Meenu Sowjanya","msowjanyac@gmail.com","Meenu@1234","2021-10-04");```

 ```insert into users(user_name,user_mailId,user_password,join_date) values("Pavan Raaj","pavan@gmail.com","Pavan@1234","2021-10-04"),("Venkatakkrishnan","venkat@gmail.com","Venki@1234","2021-10-04"),("Vaishnavi","vaishnavi@gmail.com","Vaishnavi@1234","2021-10-04");``` 

###### Fetching the data from 'users' table

 ```select * from users;```

![select * from users](https://user-images.githubusercontent.com/93571047/158520738-970c5a7c-6101-4782-9fff-21187a64e67f.png)

<hr>

###### Creation of table 2 - 'user_contacts'

 ```create table user_contacts(user_id tinyint not null,user_phoneNo bigint check(user_phoneNo like("__________"),foreign key(user_id) references users(user_id));```

``` desc user_contacts; ```

![describe user_contacts](https://user-images.githubusercontent.com/93571047/158522419-65fd18e1-dcf3-4d4c-be52-2f39305027e1.png)

###### Insertion of records into 'user_contacts' table

 ```insert into user_contacts values(1,9442972004);``` 

```insert into user_contacts values(1,9842448168),(2,7402066305),(3,7448354949),(4,7989899993),(4,9087654321),(4,9890988976),(5,9678876901),(6,9345678890),(7,9012345678),(8,9876543210),(9,9654321098),(10,9876900984),(11,7658904554);``` 

###### Fetching the data from 'user_contacts' table

```select * from user_contacts;```

![select * from user_contacts](https://user-images.githubusercontent.com/93571047/158523061-c03243c7-9af9-483d-8ca1-1e62d1cd24cb.png)

<hr>

###### Creation of table 3 - 'user_address'


 ``` create table user_address(user_Id tinyint unique,door_no varchar(10) not null,street varchar(30),city varchar(25) not null,state varchar(25) not null,`pin-code` int check(`pin-code` like("______")),foreign key(user_Id) references users(user_id)) ; ```
 
 ``` desc user_address; ```
 
 ![describe user_address](https://user-images.githubusercontent.com/93571047/158528840-d9e9962d-fdbe-43d1-b17f-e0b241e77efb.png)
 
 
 
 ###### Insertion of records into 'user_address' table
 
 
 
 ```insert into user_address values(1,"L-84","Police Colony","Annanagar (PO)","Trichy",620026);```
 
 ```insert into user_address values(2,"L-84","Police Colony","Annanagar (PO)","Trichy",620026);```
 
 ```insert into user_address values(3,"M-84","Police Colony","Annanagar (PO)","Chennai",620001);```
 
 ```insert into user_address values(4,"M-84","Police Colony","Annanagar (PO)","Chennai",620001),(5,"M-84","Arihant Nagar","Koyambedu (PO)","Chennai",620001),(6,"L-83","Perungudi","Kandanchavadi (PO)","Kanchipuram",620001),(7,"M-84","Police Colony","Kothagiri (PO)","Ooty",620010),(8,"M-84","Duraiappa Colony","Kayalpatinam(PO)","Thootukudi",620007),(9,"G-84","Collector Office Street","Avinasi (PO)","Tirupur",620009),(10,"P-84","Saibaba Colony","Boothamangalam (PO)","Coimbatore",620067),(11,"O-84","Police Colony","Perumangalam (PO)","Pondichery",620020);```
 
 
 
 ###### Fetching the data from 'user_address' table
 
 ```select * from user_address;```
 
 ![select * from user_address](https://user-images.githubusercontent.com/93571047/158529465-b14406e4-1506-4848-8b0b-adbab59892c7.png)
 
 <hr>
 
 ###### Creation of table 4 - 'students'
 
 ```create table students(student_id tinyint unique,gender enum("M","F") not null,qualification enum("12th","Diploma") not null,batch tinyint not null,dob date not null,foreign key(student_id) references users(user_id));```
 
 <br>
 
 ```desc students;```
 
 ![describe students](https://user-images.githubusercontent.com/93571047/158530533-91c75946-d1be-423d-bd92-b3c88bc384be.png)
 
 ###### Insertion of records into 'students' table
 
 ```insert into students values(5,"M","Diploma","02","2001-09-04"),(6,"M","12th","02","2003-11-04"),(7,"F","12th","02","2000-01-23"),(8,"F","12th","02","2003-09-23"),(9,"M","12th","02","2003-08-23"),(10,"M","12th","02","2004-04-23"),(11,"F","12th","02","2003-07-23");```
 
 ###### Fetching data from 'students' table 
 
 ```select * from students;```
 
 ![select * from students](https://user-images.githubusercontent.com/93571047/158531605-b21bf5e8-7035-47a2-b68a-ad23bd26ca3d.png)
 
 <hr>
 
 ###### Creation of table 5 - 'admins'
 
 ```create table admins(admin_id tinyint unique,gender enum("M","F") not null,`specialised in` enum("ELS","Technical","L&D","Admin") not null,dob date not null,foreign key(admin_id) references users(user_id));```
 
 <br>
 
 ```desc admins;```
 
 ![describe admins](https://user-images.githubusercontent.com/93571047/158532691-e4ea5e5f-4c59-44c5-9fe3-a475876133b9.png)
 
 ###### Insertion of records into 'admins' table
 
 ```insert into admins values(1,"F","Technical","1990-10-23"),(2,"F","ELS","1960-01-02"),(3,"F","L&D","1994-03-24"),(4,"M","Admin","1984-01-26");```
 
 ###### Fetching the data from 'admins' table
 
 ![select * from admins](https://user-images.githubusercontent.com/93571047/158533132-4a6fca67-6565-4a3e-9bad-0788df063ce2.png)
 
 <hr>
 
 ###### Creation of table 6 - 'reports'
 
 ``` create table reports(studentId tinyint not null,month enum('Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec') not null,`Self-learning` enum('Yet To Start','Good','Very Good','Excellent','Role Model') not null, `Helping peers` enum('Yet To Start','Good','Very Good','Excellent','Role Model') not null,`Interactive in Class` enum('Yet To Start','Good','Very Good','Excellent','Role Model') not null,`Takes leadership` enum('Yet To Start','Good','Very Good','Excellent','Role Model') not null,`Completes assignment on time` enum('Yet To Start','Good','Very Good','Excellent','Role Model') not null);``` 
 
 <br>
 
 ```desc reports;```
 
 ![describe reports](https://user-images.githubusercontent.com/93571047/158536903-b9d29aeb-7f05-4cf2-ab0d-631eb20503ff.png)
 
 ##### Insertion of records into 'reports' table 
 
 ```insert into reports values(5,"Jan","Excellent","Role Model","Good","Role Model","Yet To Start"),(6,"Jan","Excellent","Role Model","Good","Role Model","Yet To Start"),(7,"Jan","Excellent","Role Model","Good","Role Model","Yet To Start"),(8,"Jan","Role Model","Role Model","Role Model","Role Model","Role Model")(9,"Jan","Excellent","Role Model","Good","Role Model","Yet To Start"),(10,"Jan","Excellent","Role Model","Good","Role Model","Yet To Start"),(11,"Jan","Excellent","Role Model","Good","Role Model","Yet To Start");```
 
 ###### Fetching the data from 'reports' table 
 
 ```select * from reports;```
 
 ![select * from reports](https://user-images.githubusercontent.com/93571047/158537594-fb90b982-a70f-46b3-b1a5-1e91b8035d01.png)
 
 <hr>
 
 ###### Creation of table 7 - 'subjects'
 
 ```create table subjects(subject_id tinyint primary key,subject_name varchar(20) unique not null);```
 
 <br>
 
 ```desc subjects;```
 
 ![describe subjects](https://user-images.githubusercontent.com/93571047/158540754-3b647a30-1f25-4989-b3bb-91135ff2f641.png)
 
 ###### Insertion of records into 'subjects' table
 
 ```insert into subjects values(1,"ELS"),(2,"Technical"),(3,"L&D");```
 
 ###### Fetching the data from 'subjects' table 
 
 ```select * from subjects;```
 
 ![select * from subjects](https://user-images.githubusercontent.com/93571047/158541315-ce21b568-8dc8-4c0a-ad53-4416e72bf36d.png)
 
 <hr>
 
 ###### Creation of table 8 - 'attendance'
 
 ```create table attendance(date timestamp default current_timestamp,student_id tinyint not null,subject_id tinyint not null,status enum("P","A") default "P",foreign key(student_id) references users(user_id),foreign key(subject_id) references subjects(subject_id));```
 
 <br>
 
 ```desc attendance;```
 
 ![describe attendance](https://user-images.githubusercontent.com/93571047/158542030-9fccbbba-806e-4282-9a96-10b055fe52f3.png)
 
 ###### Insertion of records into 'attendance' table
 
 ```insert into attendance(student_id,subject_id) values(5,1),(5,2),(5,3),(6,1),(6,2),(6,3),(7,1),(7,2),(7,3),(8,1),(8,2),(8,3),(9,1),(9,2),(9,3),(10,1),(10,2),(10,3),(11,1),(11,2),(11,3);```
 
 ###### Fetching the data from 'attendance' table 
 
 ```select * from attendance;```
 
 ![select * from attendance](https://user-images.githubusercontent.com/93571047/158543531-5094c231-258b-441b-b771-afd512ad718e.png)
 
 <hr>
 
 ###### Creation of table 9 - 'assignments'
 
 ```create table assignments(ass_id tinyint primary key auto_increment,subject_Id tinyint not null,ass_name varchar(30) not null,ass_desc varchar(200) default "---------",deadline timestamp not null,foreign key(subject_Id) references subjects(subject_id));```
 
 <br>
 
 ```desc assignments;```
 
 ![describe assignments](https://user-images.githubusercontent.com/93571047/158544199-e57cd699-0477-4c42-bdda-a3df5024bd55.png)
 
 ###### Insertion of data into 'assignments' table
 
 ```insert into assignments(subject_Id,ass_name,deadline) values(2,"Sharding PPT","2022-03-14 10:30:00"),(3,"End user Persona Recoridngs","2022-03-07 10:30:00"),(1,"Calendar Scheduling","2022-03-07 08:30:00");```
 
 ###### Fetching the data from 'assignments' table
 
 ```select * from assignments;```
 
 ![select * from assignments](https://user-images.githubusercontent.com/93571047/158545007-373c770f-4184-4644-bd88-f83dd6cee7ee.png)
 
<hr>

###### Creation of table 10 - 'books'

```create table books(book_id smallint primary key auto_increment,book_name varchar(30) not null,author varchar(30) not null,no_of_views bigint not null check(no_of_views>0),star_ratings tinyint check(star_ratings>=0 and star_ratings<=5));```

<br>

```desc books;```

![describe books](https://user-images.githubusercontent.com/93571047/158545521-4d130583-7c58-4a7b-86e6-2aae20eb0cc0.png)

###### Insertion of records into 'books' table

```insert into books(book_name,author,no_of_views,star_ratings) values("Cindrella","Brothers Grimm",1983989947,5),("Macbeth","William Shakespeare",8138793983,5);```

###### Fetching the data from 'books' table 

```select * from books;```

![select * from books](https://user-images.githubusercontent.com/93571047/158546292-0188ee34-b0e3-4c43-8a46-8a16b06826cc.png)

<hr>

###### Creation of table 11 - 'notifications' 

```create table notifications(popup_id tinyint primary key auto_increment,subject_Id tinyint,foreign key(subject_Id) references subjects(subject_id),description varchar(200) not null);```

<br>

```desc notifications;```

![describe notifications](https://user-images.githubusercontent.com/93571047/158758079-0fb2d2d2-e7d7-4811-8dba-0b40565a7314.png)

###### Insertion of records into 'notifications' table 

```insert into notifications(subject_Id,description) values(2,"Complete ER Model for your project and submit tomorrow"),(1,"Attend the class tomorrow without fail. There will be an assessment tomorrow.");```

###### Fetching the data from 'notifications' table 

```select * from notifications;```

![select * from notifications](https://user-images.githubusercontent.com/93571047/158758086-8bcd7a45-f198-437e-8f62-791f7213b110.png)


<hr>
<hr>

## ER Model - FreshTech

<a href="FreshTech - ERR Model.mwb">![FreshTech - ERR Model](https://user-images.githubusercontent.com/93571047/158758823-57fec89a-e367-4c9f-8fce-c464bdc96612.png)</a>

<hr>