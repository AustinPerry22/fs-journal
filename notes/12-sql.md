# SQL
MySQL.org

massive excel spreadsheet
with cols and row
define table before storing data in it

casing doesn't matter


TEXT - uncapped length
VARCHAR(255) -how many bytes
BOOLEAN - true or false
DATETIME - dated
INT
BIGINT
DOUBLE
FLOAT



CREATE TABLE hotdogs(
    id INT AUTO_INCREMENT PRIMARY KEY, -adds 1 to the id every time hotdog is added, primary key organize by id.
    bun VARCHAR (1000),
    date DATETIME DEFAULT CURRENT_TIMESTAMP,
)

needs to be executed to run

INSERT INTO hotdogs
(name)
VALUES
(myhotdog)

SELECT name, data FROM hotdogs;   - gets all names and dates from the table. * selects all columns
SELECT name, FROM hotdogs WHERE 'hasKetchup' = true AND price < 2; 
// - returns the names where the hasketchup column is true AND the price is < 2. AND AND AND.
WHERE description LIKE '%jalapeno%';   - gets stuff where a jalapeno is in the description %-wildcard character.

ORDER BY name DESC -orders the table by decending name
LIMIT 2 OFFSET 1- limits the result to 2 rows, skips the first dog

SELECT  -order matters in sql
    name,
    price
FROM hotdogs
WHERE price < 30
ORDER BY price;

DELETE FROM hotdogs; -deletes entire table
DELETE FROM hotdogs WHERE id = 5;

UPDATE hotdogs
SET price = 5
WHERE id = 1;

UPDATE hotdogs
SET price = price /2
WHERE price > 5;

NOT NULL - in create table makes thing not able to be null
don't use NOT NULL if there is a DEFAULT

price INT min(1) max(1000) NOT NULL COMMENT "THESE ARE CAR PRICES",
make ENUM('egg' 'goblin', 'toya') NOT NULL,

at end of create table 
default charset utf8 COMMENT 'comment for the whole table';
utf8mb4 - supports emoji's

in the connection string in env make sure to put in the server the database the port, user id and the password.



