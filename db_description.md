## DATABASE DESCRIPTION FOR - HOTEL MANAGEMENT SYSTEM:
--------------------------------------------------

Our database management system project encompasses a Hotel Management System with distinct modules for both administrators and customers. Both modules facilitate CRUD (Create, Read, Update, Delete) operations. 
The customer module empowers users to view their profiles, create reservations, verify room availability and access receipt information. Simultaneously, the admin module allows administrators to view their profiles, 
manage room additions or deletions, and verify room availability.

## Table 1 : `app_customer`
### Attributes : `id`, `password`, `last_login`,`is_superuser`,`username`, `first_name`, `last_name`, `email`, `is_staff`, `is_active`, `date_joined`, `phone`, `address1`, `address2`, `city`, `state_code`, `zip_code`, `country`
### Primary Key : `id`
### Sample Data :

INSERT INTO "app_customer" ("password", "last_login", "is_superuser", "username", "first_name", "last_name", "email", "is_staff", "is_active", "date_joined", "phone", "address1", "address2", "city", "state_code", "zip_code", "country")
VALUES
('password123', '2023-11-28 08:30:00', 0, 'customer1', 'John', 'Doe', 'john.doe@email.com', 0, 1, '2023-11-28 08:00:00', '1234567890', '123 Main St', 'Apt 101', 'Cityville', 'CA', '90210', 'USA'),
('securepass', '2023-11-27 12:45:00', 0, 'customer2', 'Jane', 'Smith', 'jane.smith@email.com', 0, 1, '2023-11-27 12:30:00', '9876543210', '456 Oak St', NULL, 'Townsville', 'NY', '54321', 'USA'),
('pass123word', NULL, 0, 'customer3', 'Michael', 'Johnson', 'michael.johnson@email.com', 0, 1, '2023-11-26 10:15:00', '5551112233', '789 Pine St', 'Suite 202', 'Villagetown', 'TX', '76543', 'USA'),
('userpass', '2023-11-25 15:20:00', 0, 'customer4', 'Emily', 'Williams', 'emily.williams@email.com', 0, 1, '2023-11-25 15:00:00', '2223334444', '101 Elm St', NULL, 'Hamletville', 'FL', '32100', 'USA'),
('password456', NULL, 0, 'customer5', 'Robert', 'Brown', 'robert.brown@email.com', 0, 1, '2023-11-24 18:45:00', '7778889999', '222 Birch St', NULL, 'Villageburg', 'IL', '54321', 'USA');


## Table 2 : `app_hotelroom`
### Attributes : `id`, `number`, `room_type`, `description`, `price_per_night`, `max_occupancy`, `is_available`
### Primary Key : `id`
### Sample Data :

INSERT INTO "app_hotelroom" ("number", "room_type", "description", "price_per_night", "max_occupancy", "is_available")
VALUES
('101', 'SGL', 'Single Room with a Queen Bed', 99.99, 1, 1),
('202', 'DBL', 'Double Room with Two Double Beds', 149.99, 2, 1),
('303', 'KNG', 'King Suite with a Private Balcony', 199.99, 2, 1),
('404', 'VIP', 'VIP Suite with Jacuzzi and Lounge Area', 299.99, 4, 1),
('505', 'FAM', 'Family Suite with Two Bedrooms', 249.99, 4, 1);

## Table 3 : `app_roombooking`
### Attributes : `id`, `check_in_date`, `check_out_date`, `number_of_guests`, `total_amount`, `is_paid`, `customer_id`, `room_id`
### Primary key : `id`
### Foreign keys : `customer_id`, `room_id`
### Indexes :

Index on `customer_id`: `app_roombooking_customer_id_969bec7d`
Index on `room_id`: `app_roombooking_room_id_caedf380`

### Sample Data :

INSERT INTO "app_roombooking" ("check_in_date", "check_out_date", "number_of_guests", "total_amount", "is_paid", "customer_id", "room_id")
VALUES
('2023-12-01', '2023-12-05', 2, 499.99, 1, 1, 1),
('2023-12-10', '2023-12-15', 1, 299.99, 0, 2, 2),
('2023-12-20', '2023-12-25', 4, 899.99, 1, 3, 3),
('2024-01-05', '2024-01-10', 2, 349.99, 0, 4, 4),
('2024-01-15', '2024-01-20', 3, 599.99, 1, 5, 5);


## Table 4 : `app_bookingservice`
### Attributes: `id`, `room_booking_id`,  `room_service_id`
### Primary key : `id`
### Foreign keys : `room_booking_id`,  `room_service_id`
### Indexes:

Index on `room_booking_id`: `app_bookingservice_room_booking_id_1c31c30f`
Index on `room_service_id`: `app_bookingservice_room_service_id_6e420b66`

### Sample Data :

INSERT INTO "app_bookingservice" ("room_booking_id", "room_service_id")
VALUES
(1, 1),
(2, 2),
(3, 3),
(4, 4),
(5, 5);

## Table 5: `app_hotelpayment`
### Attributes :`id`, `amount`, `payment_date`, `payment_method`, `is_successful`, `customer_id`, `room_booking_id`
### Primary key : `id`
### Foreign keys : `customer_id`, `room_booking_id`
### Indexes :
 Index on `customer_id`: `app_hotelpayment_customer_id_adec9912`

### Sample Data :

INSERT INTO "app_hotelpayment" ("amount", "payment_date", "payment_method", "is_successful", "customer_id", "room_booking_id")
VALUES
(150.00, '2023-12-01 14:30:00', 'CC', 1, 1, 1),
(200.50, '2023-12-10 10:45:00', 'PP', 1, 2, 2),
(100.75, '2023-12-20 18:00:00', 'CC', 0, 3, 3),
(75.25, '2024-01-05 08:15:00', 'PP', 1, 4, 4),
(120.00, '2024-01-15 16:30:00', 'CC', 1, 5, 5);
