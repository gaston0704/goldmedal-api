# Olympic Gold Medal Statistics API

REST API built with Spring Boot that provides statistics about Olympic gold medals by country.

The application allows users to retrieve country information, medal statistics, and lists of Olympic gold medals sorted by different criteria.

## Technologies

* Java
* Spring Boot
* Spring Data JPA
* H2 In-Memory Database
* Maven

## Features

* Retrieve Olympic medal statistics for a specific country
* List countries sorted by:

  * name
  * GDP
  * population
  * medal count
* Retrieve a list of Olympic gold medals won by a country
* Sort medal lists by:

  * year
  * season
  * city
  * athlete name
  * event

## API Endpoints

### Get countries summary

GET /countries?sort_by={field}&ascending={y|n}

Example:

curl http://localhost:3001/countries?sort_by=name&ascending=y

### Get details about a country

GET /countries/{country}

Example:

curl http://localhost:3001/countries/Germany

### Get medal list for a country

GET /countries/{country}/medals?sort_by={field}&ascending={y|n}

Example:

curl http://localhost:3001/countries/Germany/medals?sort_by=year&ascending=y

## Example Response

Example request:

curl http://localhost:3001/countries/Germany

Example response:

{
"name": "Germany",
"gdp": 41313.31399,
"population": 81413145,
"numberMedals": 572,
...
}

## Running the Application

Clone the repository:

git clone https://github.com/yourusername/goldmedal-api.git

Run the project using Maven:

mvn spring-boot:run

The application will start on:

http://localhost:3001

## Database

The project uses an in-memory H2 database.

The dataset is loaded automatically from:

src/main/resources/data.sql

## Author

Alecs
