# CRUD OPERATIONS -

## CREATE

### Create command for `app_customer`
CREATE TABLE IF NOT EXISTS "app_customer" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "password" varchar(128) NOT NULL, "last_login" datetime NULL, "is_superuser" bool NOT NULL, "username" varchar(150) NOT NULL UNIQUE, "first_name" varchar(150) NOT NULL, "last_name" varchar(150) NOT NULL, "email" varchar(254) NOT NULL, "is_staff" bool NOT NULL, "is_active" bool NOT NULL, "date_joined" datetime NOT NULL, "phone" varchar(15) NOT NULL, "address1" text NOT NULL, "address2" text NULL, "city" varchar(100) NULL, "state_code" varchar(2) NULL, "zip_code" varchar(10) NULL, "country" varchar(50) NULL);

INSERT INTO app_customer VALUES(1,'pbkdf2_sha256$600000$PQyCGJ3AizVBpAhTxvXJJ6$ZcdXFWoCtHzxjpOzj5G3b+IeNMverxqZd4pKqDcIE8s=','2023-11-10 17:34:50.558064',0,'maldmaklm@gmail.com','','','',0,1,'2023-11-10 17:34:50.348485','207531141','4-79','brickstone','wichita','KS','67220','USA');
INSERT INTO app_customer VALUES(2,'pbkdf2_sha256$600000$zRSfc6tJNzGbNPBInBOfBv$S3I77hypiBm3Qz2reMttyTQkzY2dXx+js8OLqqQqrI8=','2023-11-11 04:10:28.223415',0,'nadjanjk@gmail.com','','','',0,1,'2023-11-11 04:10:28.015681','1341234123','ndasjkan','andjankj','cnjsnkj','KS','67220','USA');
INSERT INTO app_customer VALUES(3,'pbkdf2_sha256$600000$6VCHG0jqrCF8NDCuMShQvu$acKa+p+wj72xxCBR15ilUxbaBW2nOhx/mU5OLpK09Bs=','2023-11-11 05:35:00.493729',0,'madkmakl@gmail.com','','','',0,1,'2023-11-11 05:35:00.284558','21341231231','123412','dsafsda','casd','KS','67220','USA');
INSERT INTO app_customer VALUES(4,'pbkdf2_sha256$600000$dK8sUdj285c1BqDjqfo90F$3iviXONTrFM435vPe+JEGbOwf4qYMlCWIM2P8/5RjI4=','2023-11-11 07:11:24.246144',1,'admin','','','adjanjk@gmail.com',1,1,'2023-11-11 06:05:29.634252','','',NULL,NULL,NULL,NULL,NULL);
INSERT INTO app_customer VALUES(5,'pbkdf2_sha256$600000$k7WgbGXmDbgbbun4cxXA8q$oErkTSHt/IPTWY3VfgSv/a+rdz19Z7PXjXhdv6nz2wg=','2023-11-11 08:53:56.400166',1,'makldmakjnkj@gmail.com','','','',1,1,'2023-11-11 08:53:56.190717','1341234123','dajkk','ajkdnjk','wichita','ks','67220','USA');
INSERT INTO app_customer VALUES(6,'pbkdf2_sha256$600000$f4hJ5PTSLWKIl3LVPICwq2$Tek4KEw5T5HuiRGDKZa2lRjHALLQk05LCWq3idRpIYI=','2023-11-11 09:15:23.418330',0,'klsdmfklnkj@gmail.com','','','',0,1,'2023-11-11 09:15:23.209597','134134123','3sda','nsdjkankj','nckjanjk','KS','67220','USA');

### Create command for `app_hotelroom`
CREATE TABLE IF NOT EXISTS "app_hotelroom" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "number" varchar(10) NOT NULL UNIQUE, "room_type" varchar(3) NOT NULL, "description" text NOT NULL, "price_per_night" decimal NOT NULL, "max_occupancy" integer NOT NULL, "is_available" bool NOT NULL);

INSERT INTO app_hotelroom VALUES(1,'1','SGL','single bed rooms are fine for one people',100,1,0);
INSERT INTO app_hotelroom VALUES(2,'2','DBL','double bed rooms for fine for two people',100,2,0);
INSERT INTO app_hotelroom VALUES(7,'3','KNG','This is basic description for king room',150,2,0);

### Create command for `app_roombooking`
CREATE TABLE IF NOT EXISTS "app_roombooking" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "check_in_date" date NOT NULL, "check_out_date" date NOT NULL, "number_of_guests" integer NOT NULL, "total_amount" decimal NOT NULL, "is_paid" bool NOT NULL, "customer_id" bigint NOT NULL REFERENCES "app_customer" ("id") DEFERRABLE INITIALLY DEFERRED, "room_id" bigint NOT NULL REFERENCES "app_hotelroom" ("id") DEFERRABLE INITIALLY DEFERRED);
CREATE INDEX "app_roombooking_customer_id_969bec7d" ON "app_roombooking" ("customer_id");
CREATE INDEX "app_roombooking_room_id_caedf380" ON "app_roombooking" ("room_id");

INSERT INTO app_roombooking VALUES(1,'2023-11-11','2023-11-12',1,100,0,3,1);
INSERT INTO app_roombooking VALUES(2,'2023-11-12','2023-11-13',1,100,1,3,2);
INSERT INTO app_roombooking VALUES(3,'2023-11-12','2023-11-13',1,100,1,6,1);
INSERT INTO app_roombooking VALUES(4,'2023-11-12','2023-11-12',1,100,1,9,2);
INSERT INTO app_roombooking VALUES(5,'2023-11-13','2023-11-12',1,100,1,9,1);
INSERT INTO app_roombooking VALUES(6,'2023-11-13','2023-11-14',1,100,1,9,1);
INSERT INTO app_roombooking VALUES(7,'2023-11-13','2023-11-14',1,100,1,9,2);
INSERT INTO app_roombooking VALUES(8,'2023-11-13','2023-11-15',1,100,1,14,1);
INSERT INTO app_roombooking VALUES(9,'2023-11-13','2023-11-14',2,150,1,19,7);

### Create command for `app_bookingservice`
CREATE TABLE IF NOT EXISTS "app_bookingservice" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "room_booking_id" bigint NOT NULL REFERENCES "app_roombooking" ("id") DEFERRABLE INITIALLY DEFERRED, "room_service_id" bigint NOT NULL REFERENCES "app_additionalservice" ("id") DEFERRABLE INITIALLY DEFERRED);
CREATE INDEX "app_bookingservice_room_booking_id_1c31c30f" ON "app_bookingservice" ("room_booking_id");
CREATE INDEX "app_bookingservice_room_service_id_6e420b66" ON "app_bookingservice" ("room_service_id");

NSERT INTO app_bookingservice VALUES(8,7,6);
INSERT INTO app_bookingservice VALUES(10,9,10);

### Create command for `app_hotelpayment`
CREATE TABLE IF NOT EXISTS "app_hotelpayment" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "amount" decimal NOT NULL, "payment_date" datetime NOT NULL, "payment_method" varchar(2) NOT NULL, "is_successful" bool NOT NULL, "customer_id" bigint NOT NULL REFERENCES "app_customer" ("id") DEFERRABLE INITIALLY DEFERRED, "room_booking_id" bigint NOT NULL UNIQUE REFERENCES "app_roombooking" ("id") DEFERRABLE INITIALLY DEFERRED);
CREATE INDEX "app_hotelpayment_customer_id_adec9912" ON "app_hotelpayment" ("customer_id");

INSERT INTO app_hotelpayment VALUES(1,125,'2023-11-11 07:14:16.154960','CC',1,3,2);
INSERT INTO app_hotelpayment VALUES(2,125,'2023-11-11 09:16:08.928964','CC',1,6,3);
INSERT INTO app_hotelpayment VALUES(3,125,'2023-11-11 19:59:00.869200','CC',1,9,4);
INSERT INTO app_hotelpayment VALUES(4,125,'2023-11-11 20:06:42.289439','CC',1,9,5);
INSERT INTO app_hotelpayment VALUES(5,125,'2023-11-11 20:09:17.625371','CC',1,9,6);
INSERT INTO app_hotelpayment VALUES(6,110,'2023-11-11 20:11:16.165280','CC',1,9,7);
INSERT INTO app_hotelpayment VALUES(7,125,'2023-11-13 14:24:48.504558','CC',1,14,8);
INSERT INTO app_hotelpayment VALUES(8,195,'2023-11-13 15:56:18.743146','DC',1,19,9);
