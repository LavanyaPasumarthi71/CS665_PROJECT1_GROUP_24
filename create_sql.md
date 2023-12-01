### Create Statement for `app_customer`

CREATE TABLE IF NOT EXISTS "app_customer" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "password" varchar(128) NOT NULL, "last_login" datetime NULL, "is_superuser" bool NOT NULL, "username" varchar(150) NOT NULL UNIQUE, "first_name" varchar(150) NOT NULL, "last_name" varchar(150) NOT NULL, "email" varchar(254) NOT NULL, "is_staff" bool NOT NULL, "is_active" bool NOT NULL, "date_joined" datetime NOT NULL, "phone" varchar(15) NOT NULL, "address1" text NOT NULL, "address2" text NULL, "city" varchar(100) NULL, "state_code" varchar(2) NULL, "zip_code" varchar(10) NULL, "country" varchar(50) NULL);

### Create Statement for `app_hotelroom`

CREATE TABLE IF NOT EXISTS "app_hotelroom" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "number" varchar(10) NOT NULL UNIQUE, "room_type" varchar(3) NOT NULL, "description" text NOT NULL, "price_per_night" decimal NOT NULL, "max_occupancy" integer NOT NULL, "is_available" bool NOT NULL);
