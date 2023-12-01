## CRUD OPERATIONS

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

## READ

### Read command for `app_customer`

1. **Select All Customers:**
   
   SELECT * FROM app_customer;

2. **Select Customer by Username:**
   
   SELECT * FROM app_customer WHERE username = 'admintest';
   

3. **Select Active Customers:**
   
   SELECT * FROM app_customer WHERE is_active = true;
   

4. **Select Customers in a Specific City:**
   
   SELECT * FROM app_customer WHERE city = 'wichita';
   

5. **Select Customers with a Specific Email Domain:**
   
   SELECT * FROM app_customer WHERE email LIKE '%@gmail.com';
   

### Read command for `app_hotelroom`

1. **Select all rooms:**

SELECT * FROM app_hotelroom;


2. **Select rooms with a specific room type (e.g., 'DBL' for Double Rooms):**

SELECT * FROM app_hotelroom" WHERE "room_type" = 'DBL';


3. **Select available rooms with a maximum occupancy of 2:**

SELECT * FROM app_hotelroom WHERE "is_available" = 1 AND "max_occupancy" = 2;


4. **Select rooms with a price per night less than $150:**

SELECT * FROM app_hotelroom WHERE "price_per_night" < 150.00;


5. **Select rooms with a description containing the word 'Suite':**

SELECT * FROM app_hotelroom WHERE LOWER("description") LIKE '%suite%';


### Read command for `app_roombooking`

1. **Retrieve all room bookings with customer details:**

SELECT rb.id, rb.check_in_date, rb.check_out_date, rb.number_of_guests, rb.total_amount, rb.is_paid,
       c.username AS customer_username, c.first_name AS customer_first_name, c.last_name AS customer_last_name,
       hr.number AS room_number, hr.room_type AS room_type
FROM app_roombooking rb
JOIN app_customer c ON rb.customer_id = c.id
JOIN app_hotelroom hr ON rb.room_id = hr.id;


2. **Retrieve unpaid room bookings:**

SELECT id, check_in_date, check_out_date, number_of_guests, total_amount
FROM app_roombooking
WHERE is_paid = 0;


3. **Retrieve room bookings for a specific customer:**

SELECT id, check_in_date, check_out_date, number_of_guests, total_amount, is_paid
FROM app_roombooking
WHERE customer_id = <customer_id>;


4. **Retrieve available rooms for a specific date range:**

SELECT hr.id AS room_id, hr.number AS room_number, hr.room_type, hr.price_per_night, hr.max_occupancy
FROM app_hotelroom hr
LEFT JOIN app_roombooking rb ON hr.id = rb.room_id
AND ('<check_in_date>' BETWEEN rb.check_in_date AND rb.check_out_date
   OR '<check_out_date>' BETWEEN rb.check_in_date AND rb.check_out_date
   OR rb.id IS NULL);
