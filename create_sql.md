### Create Statement for `app_customer`

CREATE TABLE IF NOT EXISTS "app_customer" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "password" varchar(128) NOT NULL, "last_login" datetime NULL, "is_superuser" bool NOT NULL, "username" varchar(150) NOT NULL UNIQUE, "first_name" varchar(150) NOT NULL, "last_name" varchar(150) NOT NULL, "email" varchar(254) NOT NULL, "is_staff" bool NOT NULL, "is_active" bool NOT NULL, "date_joined" datetime NOT NULL, "phone" varchar(15) NOT NULL, "address1" text NOT NULL, "address2" text NULL, "city" varchar(100) NULL, "state_code" varchar(2) NULL, "zip_code" varchar(10) NULL, "country" varchar(50) NULL);

### Create Statement for `app_hotelroom`

CREATE TABLE IF NOT EXISTS "app_hotelroom" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "number" varchar(10) NOT NULL UNIQUE, "room_type" varchar(3) NOT NULL, "description" text NOT NULL, "price_per_night" decimal NOT NULL, "max_occupancy" integer NOT NULL, "is_available" bool NOT NULL);

### Create Statement for `app_roombooking`

CREATE TABLE IF NOT EXISTS "app_roombooking" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "check_in_date" date NOT NULL, "check_out_date" date NOT NULL, "number_of_guests" integer NOT NULL, "total_amount" decimal NOT NULL, "is_paid" bool NOT NULL, "customer_id" bigint NOT NULL REFERENCES "app_customer" ("id") DEFERRABLE INITIALLY DEFERRED, "room_id" bigint NOT NULL REFERENCES "app_hotelroom" ("id") DEFERRABLE INITIALLY DEFERRED);
CREATE INDEX "app_roombooking_customer_id_969bec7d" ON "app_roombooking" ("customer_id");
CREATE INDEX "app_roombooking_room_id_caedf380" ON "app_roombooking" ("room_id");

### Create Statement for `app_bookingservice`

CREATE TABLE IF NOT EXISTS "app_bookingservice" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "room_booking_id" bigint NOT NULL REFERENCES "app_roombooking" ("id") DEFERRABLE INITIALLY DEFERRED, "room_service_id" bigint NOT NULL REFERENCES "app_additionalservice" ("id") DEFERRABLE INITIALLY DEFERRED);
CREATE INDEX "app_bookingservice_room_booking_id_1c31c30f" ON "app_bookingservice" ("room_booking_id");
CREATE INDEX "app_bookingservice_room_service_id_6e420b66" ON "app_bookingservice" ("room_service_id");

### Create Statement for `app_hotelpayment`

CREATE TABLE IF NOT EXISTS "app_hotelpayment" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "amount" decimal NOT NULL, "payment_date" datetime NOT NULL, "payment_method" varchar(2) NOT NULL, "is_successful" bool NOT NULL, "customer_id" bigint NOT NULL REFERENCES "app_customer" ("id") DEFERRABLE INITIALLY DEFERRED, "room_booking_id" bigint NOT NULL UNIQUE REFERENCES "app_roombooking" ("id") DEFERRABLE INITIALLY DEFERRED);
CREATE INDEX "app_hotelpayment_customer_id_adec9912" ON "app_hotelpayment" ("customer_id");
