
# SQL Queries for Car Dekho Dataset

## Read the Data
SELECT * FROM cars.car_dekho;

## Total Number of Cars
SELECT COUNT(*) AS total_cars
FROM cars.car_dekho;

## Number of Automatic Transmission Cars

SELECT COUNT(*) AS num_automatic_cars 
FROM cars.car_dekho
WHERE transmission = 'Automatic';

## Total Number of Cars Sold by Fuel Type\
SELECT fuel, COUNT(*) AS num_cars_sold
FROM cars.car_dekho
GROUP BY fuel;

## Total Selling Price by Year
USE cars;
SELECT year, fuel, SUM(selling_price) AS total_selling_price
FROM cars.car_dekho
GROUP BY year, fuel;

## Number of Cars Sold by Owner Type
SELECT owner, COUNT(*) AS num_cars_sold
FROM cars.car_dekho
GROUP BY owner;

## Most Common Seller Type
SELECT seller_type, COUNT(*) AS total_cars_sold
FROM cars.car_dekho
GROUP BY seller_type
ORDER BY total_cars_sold DESC
LIMIT 1;

## Most Common Car Model
SELECT Name, COUNT(Name) AS frequency
FROM cars.car_dekho
GROUP BY Name
ORDER BY frequency DESC
LIMIT 5;

## Cars with the Highest Engine Power
SELECT Name, max_power AS engine_power
FROM cars.car_dekho
ORDER BY engine DESC
LIMIT 5;

## Total Number of Cars Sold by Fuel and Year
SELECT fuel, year, COUNT(*) AS total_cars_sold
FROM cars.car_dekho
WHERE year IN (2020, 2021, 2022, 2023)
GROUP BY fuel, year
ORDER BY year;

## Average Number of Seats per Car
SELECT AVG(seats) AS avg_seats_per_car
FROM cars.car_dekho;
