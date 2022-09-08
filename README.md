# Cinema app

#### Prerequisites
- Install the latest versions of `Python` & `Django`. Downgrading might become necessary later on, as packages you might want to install ask for lower versions.
- Install and use `PostgreSQL` / `MySQL` as db engine for the project.

#### Good practices to apply while writing code
- Run `flake8` or `pylint` on the written code in order to get accomodated to `Python`'s coding standards (`PEP8`).
- Unit testing.

---
## First sprint

#### Create following pages:
- Presentation page
- Movies running in this period (filter)
- Add movie details page; embed trailer in the page
- Contact page
- Account related pages:
    - Login
    - Logout
    - Reset password
    - Register. Detailed steps:
        - I complete a form with just my email
        - I confirm my email address by clicking the received link
        - I complete other account details and the account is created


#### DB tables:

- City
    - name
    - country (FK)
- Cinema: 
    - city (FK)
    - address
    - name
    - description
- Hall:
    - city (FK)
    - name
    - description
- Film:
    - name
    - poster 
    - description
    - `IMDb` id
    - `IMDb` url (field / property generated using `IMDb` id)
    - trailer url
    - duration
- Seat:
    - name / representation in its hall
    - occupied (simulate pressure sensor)
- Reservation:
    - user (FK)
    - playing time (FK)
    - seat (FK)
- Playing time:
    - start time
    - hall (FK)
    - movie (FK)


#### Functionalities:

- As an admin, I should be able to add playing times for the movies.
- As an user, I should be able to select a cinema, hall, movie and playing time and create a reservation

- Limit requests on login to prevent bruteforce attacks

---
## Second sprint

- Add confirmation field on reservation.
- Send an email when a new Movie is added (newsletter)

#### Cronjobs. Async Tasks
- Invalidate reservations that are not confirmed within 30 mins from movie start.

#### Unit tests
- Tests for generating Seats
- Tests for login, logout, register (and for everything else if possible)

#### File uploads
- `.csv` upload to import Movies (with update if they already exist based on the imdb_id)

#### File download
- Allow users to export data about their reservations (`.csv`)

---
## Third sprint 

- Import movies from `.zip` file containing a `.csv` and images (for movie covers). The `.csv` will contain the relative path of the images
- Add a field that stores whether or not a seat is occupied (something like `occupied`)

### Django Rest Framework (DRF):

[Go through DRF tutorials (quickstart, 1-6)](https://www.django-rest-framework.org/tutorial/quickstart/)

##### Create `API`s for the following cases:
- This week's movies
- This week's movies and their playing times
- Where and when a specific movie is running, in all locations (search by `IMDb` id or name)
- Create / Update: 
    - movies
    - running times
    - halls
    - reservation
- Mark reservation as confirmed
- Allow the change of spectator presence on seats; flip `occupied` field on endpoint call. Limit API access (unique token, API key, IP filtering)

> Secure above endpoints with token authentication (`Bearer {base64 token}`)

##### Integrate Swagger for easier work with `API`s

### Handle huge downloads:
- Write an SQL script to generate a lot of user reservations (200k) and test `.csv` export response time 
- Lower `TTFB` (Time To First Byte) signifiantly for better UX


---
## Fourth sprint 

- Familiarize yourself with Docker. Go through all the parts of https://docs.docker.com/get-started/
- Dockerize project (run application in containers - django project & database)
- Migrate PostgreSQL data from local server to the docker contained server
- Task async (`crontab`) that retrieves the description of movies from the IMDB page and populates the DB with it
- Write a script that uses the presence API to simulate random seat occupation (like a sensor that is triggered when someone sits on their seat)
- Based on the above script, add a new API that will allow us to identify possible frauds (seats occupied without reservations)

---
# Fifth sprint

- Deploy app in Heroku (+presentation).
- Implement payment solution for buying tickets.
- Generate thumbnails for posters of specific dimensions (without external libraries)

---
# To be refined
- File manipulation (add metadata to uploaded images)


#### Ideas
- websockets?
- location consent?
- cookies consent? 
