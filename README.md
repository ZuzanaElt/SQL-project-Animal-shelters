# SQL-project-Animal-shelters
Project for introduction to SQL and MySQL databases course.

![image](https://github.com/user-attachments/assets/0cb04476-4604-4bd8-ab15-fbdf355875b0)

## This project was a final project for CFG course Introduction to SQL and MySQL databases. 
There were 4 cooperators on this project.

## The projects includes 5 tables with various data concerning pets, their health and their adopters.
Reverse engineering gives us a EER diagram (Database drop down menu --> Reverse Engineer option).
![Capture](https://github.com/user-attachments/assets/ccd40fbd-d4f6-403d-a083-5e578d5c6bab)

## Function and procedure and join functions
In the script there are examples of using different functions 
such as the following:

-- Which animals are at the Paris shelter? 
```
DELIMITER //
CREATE FUNCTION AnimalsInParis()
RETURNS VARCHAR(255) READS SQL DATA
BEGIN
    DECLARE animalList VARCHAR(255);
    SELECT GROUP_CONCAT(animal_name) INTO animalList
    FROM animals
    WHERE shelter_ID = (SELECT shelter_ID FROM shelters WHERE shelter_city = 'Paris');
    -- 'Paris'; -- Replace 'Paris' with the actual identifier for the Paris shelter
    RETURN animalList;
END 
//
DELIMITER ;
```



