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

### Read command for `app_bookingservice`


1. **Retrieve All Bookings with Associated Room Services:**
   
   SELECT * FROM app_bookingservice;
   

2. **Retrieve Booking Services for a Specific Room Booking ID:**
   
   SELECT * FROM app_bookingservice WHERE "room_booking_id" = 1;
   

3. **Retrieve Booking Services for a Specific Room Service ID:**
   
   SELECT * FROM app_bookingservice WHERE "room_service_id" = 2;
   

4. **Retrieve Booking Service Details for a Specific Booking ID and Room Service ID:**
   
   SELECT * FROM app_bookingservice WHERE "room_booking_id" = 1 AND "room_service_id" = 2;
   
### Read command for `app_hotelpayment`

1. **Select all payments with their details:**
   
   SELECT * FROM app_hotelpayment;

2. **Select the total amount of successful payments:**
   
   SELECT SUM(amount) as total_amount
   FROM app_hotelpayment
   WHERE is_successful = 1;
   

3. **Select payment details for a specific customer:**
   
   SELECT *
   FROM app_hotelpayment
   WHERE customer_id = 1;
   
4. **Select successful payments made on a specific date:**
   
   
   SELECT *
   FROM app_hotelpayment
   WHERE is_successful = 1 AND DATE(payment_date) = '2023-12-01';


5. **Select payment details for a specific room booking:**
   
   SELECT *
   FROM app_hotelpayment
   WHERE room_booking_id = 1;

## Update

### Update command for `app_customer`
- Update email for a specific customer

UPDATE app_customer
SET email = 'newmail@gmail.com'
WHERE id = 10;

### Update command for `app_hotelroom`
- Update the description and price of a room with a specific number:

-- Update the description and price of room with number '101'
UPDATE app_hotelroom
SET description = 'Updated Description', price_per_night = 129.99
WHERE number = '101';

- Mark a room as unavailable:

-- Mark room with number '202' as unavailable
UPDATE app_hotelroom
SET is_available = 0
WHERE number = '202';

### Update command for `app_roombooking`

- Update room booking details:

-- Update check-in date and number of guests for a specific room booking
UPDATE app_roombooking
SET check_in_date = '2023-12-15', number_of_guests = 3
WHERE id = 1;

- Update payment status for a room booking:

-- Mark a room booking as paid
UPDATE app_roombooking
SET is_paid = 1
WHERE id = 5;

### Update command for `app_bookingservice`

- Update Statement:

-- Update the room_service_id for a specific booking:

UPDATE app_bookingservice
SET room_service_id = 5
WHERE room_booking_id = 3;

### Update command for `app_hotelpayment`
-- Update payment amount for a specific payment ID:

UPDATE app_hotelpayment
SET amount = 150.00
WHERE id = 1

