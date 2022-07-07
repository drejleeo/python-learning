# Cinema App Tickets

## [BE] Add email verification on user registration
The purpose of this task is to add email verification on user registration

Make sure Django authentication is enabled.
When signing up for an account, send an email to the user with a verification link, before activating the user. Activate the user when the link is accessed.

*DoD*:
- the user registration sends the verification email - the user cannot login right after registration
- the user can login after the email confirmation


## [UI] Add footer template
The purpose of this task is to create the footer template that will be reused in the other pages. The links will redirect to the social media pages and have the social media page icons as URLs.
The icons can be shown either vertically or horizontally.
*DoD*:
* the template can be rendered and used in the other pages


## [UI] Add header template
The purpose of this task is to create the template that will contain the links to the other app pages. .

Acasa | Filme | Contact

*DoD*:
* the template can be rendered and used the other pages


## [UI] Add Contact page
The purpose of this task is to add the Contacts page.
Contacts_page.design.file/Contact_page_design_link .
___
*Links to other pages*
___
Add several fields: - Name
- Email
- Phone number
- City

 - Cinema
- Subject
- Message
- Send button ___
*Links to social media accounts* ___
.
*DoD*:
* the page is rendered successfully and we can submit and view the submissions


## [UI] Add Home page
The purpose of this task is to add the Home page.
design_file/url reference
.
___
*Links to other pages*
___
Title
Description
___
*Links to social media accounts* ___
.
*DoD*:
* the page is rendered successfully


## [BE] [Model] Add the Movie model
The purpose of this task is to add the * model .
___
Add several fields:
- name
- poster
- description
- IMDB link (field or property generated with the help of the id field)
- IMDB id
- trailer URL (youtube, maybe, to be easily embedded into the details page) - length
-- other fields you think you might need
___
.
*DoD*:
* the model is ready to use and has a migration for it.


## [UI] Add "Currently playing" movies page

 The purpose of this task is to .
___
*Links to other pages*
___
Paginated list with movies that are playing in the next 7 days. The list should show 5 movies per page.
___
*Links to social media accounts*
___
.
*DoD*:
* the page is rendered successfully


## [BE] [Model] Add the cinema Hall model
The purpose of this task is to add the * model .
___
Add several fields:
- name
- seats
- description
-- other fields you think you might need
___
.
*DoD*:
* the model is ready to use and has a migration for it.


## [Security] Add ratelimit
The purpose of this task is to add a limitation for the requests to prevent brute force or system overload caused by these. .
___
Find a solution to prevent these issues.
___
.
*DoD*:
* this can be tested if we configure the server with a very low request limit


## [BE] [Model] Add the Cinema model
The purpose of this task is to add the Cinema model .
___
Add several fields:
- city
- address
- hall
- name
- description
-- other fields you think you might need ___
.

 *DoD*:
* the model is ready to use and has a migration for it.


## [Setup] Create the django project
The purpose of this task is to setup the project.
Try to use the latest version of Django and Python, if possible. Create a virtual environment for the project.
Initialize the Django project.
Use flake8 or pylint to check the syntax of the written python code. Add the requirements file.
*DoD*:
* server is up and running locally


## [BE] Add the ability to schedule the movies
The purpose of this task is to add the ability to schedule movies, as an admin. This can be achieved from the admin site. .
*DoD*:
- as an admin user, I can schedule a movie in a specific Cinema, Hall and timeframe
- as a guest user or an authenticated user (non-admin) I can view the scheduled movies in the Currently playing page


## [BE] Send an email to the user with the tickets after the booking was completed
.
*DoD*:
* The email is sent.


## [BE] Add the ability to book a ticket
The purpose of this task is to add the ability to book a ticket, as a registered user.
.
*DoD*:
- as an authenticated user, I can make a reservation for a movie in a specific Cinema, Hall and timeframe


## [UI] Save the submissions from the Contacts page in the DB
The purpose of this task is to allow us to save the Contacts submissions to be able to see them later, as an admin user.
Contacts_page.design.file/Contact_page_design_link .
___
*Links to other pages*
___
Add several fields:
- Name
- Email
- Phone number
- City
- Cinema
- Subject
- Message
- Send button
___
*Links to social media accounts*
___
.
*DoD*:
* the page is rendered successfully and we can submit and view the submissions


## [BE] [Model] Add the Seat model
The purpose of this task is to add the * model .
___
Add several fields:
- reservation
-- other fields you think you might need
___
.
*DoD*:
* the model is ready to use and has a migration for it.


## [BE][Enhancement] Show only the upcoming playing times when booking a ticket
Right now, all the playing times are present in the booking UI(including the passed ones). This enhancement will show only the upcoming ones.
*DoD*:
* The playing times shown in the UI are only the upcoming ones


## [Model] Adjust the Reservation model
The purpose of this task is to add an additional field on the Reservation model to know if a Reservation has been confirmed or if the tickets have been picked from the reception.


## [BE] Check email address before creating an account
The purpose of this task is to add the email validation before actually creating the account to make sure the emails are used.
Flow
- enter email
- verification email is sent
- redirect to a page where the user can continue the registration flow
*DoD*:
* Registration is allowed only if the email is validated first
Add unittests for login, logout and registration views
The purpose of this task is to add unittests for the specified views *DoD*:
* the tests pass


## [BE] Add unittests for Seat generation
The purpose of this task is to add unittests to make sure the Seats are properly generated when creating a Hall object. Refactor the code to make the generation part easier to test.
Move the dynamic Seat generation to Hall post_save signal.
*DoD*:
* the tests pass


## [UI] Add Movie details page
The purpose of this task is to add the details page of a Movie object. __design_file/url reference__
.
___
*Links to other pages*
___
Title
Length
Description
imdb link
Embed video player with the movie trailer ___
*Links to social media accounts*
___
.*DoD*:
* the page is rendered successfully


## [BE] Add possibility to download a csv file containing all the Reservation objects of an user
The purpose of this task is to be able to download Reservation object details as a csv file.
*DoD*:
* the file can be downloaded and it has the correct format


## [BE] Add reservation confirmation
The purpose of this functionality is to provide the user the ability to confirm the reservation by email link or UI
*DoD*:
* ability to confirm the reservation


## [BE] Add looping job to clean reservations
The purpose of this task is to add a job that is executed every minute and marks Reservation objects as expired that are not confirmed and for which the movie is about to begin (30 minutes), to allow clients to buy them from the reception.
*DoD*:
* the job cleans Reservations


## [BE] Create a migration that creates the scheduled tasks once applied
The purpose of this task is to add the * model .
___
Add several fields:
-- other fields you think you might need ___
.
*DoD*:
* The migration is ready to be applied
Add possibility to import Movies
The purpose of this task is to add the import Movies feature.
Flow:
- upload csv file
- handle possible issues
- create new Movie objects with the file data *DoD*:
* the movies are added in the DB


## [BE] Add the possibility to confirm the reservation by email
The purpose of this task is to add the possibility of confirming the reservation by an link send in the email
*DoD*:
* The feature email should contain a link that once clicked will confirm the reservation


## [BE] Send an email when a new movie is added
When a new movie is added, an email should be sent to the registered users that have subscribed to the newsletter or to non registered users that have subscribed by email
*DoD*:
* The code for the newsletter subscription


## [BE] [ENHANCEMENT] Email registration should only confirm the email once
The purpose of this task is to add the * model .
___
Add several fields:
-- other fields you think you might need ___
.
*DoD*:
* the model is ready to use and has a migration for it.



## [Analysis] DRF Documentation
The purpose of this task is to read the django rest framework tutorial, starting with: .
https://www.django-rest-framework.org/tutorial/quickstart/
https://www.django-rest-framework.org/tutorial/1-serialization/
and going through all the tutorial pages/steps.


## [BE] Add a new Movies import view
The purpose of this task is to add a new view that allows us to make Movies import.
The view should accept a zip file.
The zip should contain a directory with images.
The zip should contain a csv file with the movie's data and the relative path to the poster image, found in the above- mentioned directory.
. *DoD*:
* the import works and the images are set up properly
* import errors are handled ( missing image, existing imdb id


## [BE] [Model] Adjust the Seat model
The purpose of this task is to adjust the Seat model .
___
Add the occupied field as a boolean.
___
.
*DoD*:
* the model is ready to use and has a migration for the new field.


## [BE] Add the "currently playing" endpoint
The purpose of this task is to add a new endpoint to retrieve the movies that are playing this week.


## [BE] Add the currently playing with dates endpoint
The purpose of this task is to add a new endpoint to retrieve the movies that are playing this week and their playing hours. .
___
Results should look like this:
```json
[
    {
        'id': movie_id,
        ... # all other movie details
        'playing_time': [
            {
                'city': '',
                'hall': '',
                'start_time': '',
                ... # all other playing time details
            }
        ]
    }
]
```
___
.
*DoD*:
* the endpoint returns the data correctly


## [BE] Add token authentication in DRF
The purpose of this task is to add the token authentication method for users The tokens should have this form "Bearer {TOKEN}"
The tokens should be base64 encoded.
.
*DoD*:
* the tokens can be associated with users and they can be used to make requests.


## [BE] Add the search endpoint
The purpose of this task is to add a new endpoint that allows us to view all the playing times for a searched movie. The endpoint can receive two parameters:
- IMDb id
- name
The endpoint should search by the imdb id or by the name. .
*DoD*:
* the playing times can be retrieved correctly


## [BE] Add the hall endpoint
The purpose of this task is to add a new endpoint to create/update hall objects .
*DoD*:
* the hall objects can be created and retrieved successfully.


## [BE] Add the movies endpoint
The purpose of this task is to add a new endpoint to create/update Movie objects .
*DoD*:
* the Movie objects can be created and retrieved successfully.


## [BE] Refactor the code and add permissions in the endpoints.

 .
*DoD*:
* The code is refactored and each endpoint has perimssions and token based auth


## [BE] Add the running times endpoint
The purpose of this task is to add a new endpoint to create/update running time objects .
*DoD*:
* the running time objects can be created and retrieved successfully.


## [BE] Add the reservation endpoint
The purpose of this task is to add a new endpoint to create/update reservation objects.
Implement 2 enpoints: one for admin and one for clients to edit the reservation. Authorize endpoints using Bearer Token. .
*DoD*:
* the reservation objects can be created and retrieved successfully.


## [BE] API to set confirmed status
The purpose of this task is to create a new API endpoint with DRF to be able to mark a Reservation as confirmed. .
*DoD*:
* the endpoint can be used to change the confirmed status of a Reservation


## [BE] [Model] Add new endpoint to change occupied status of seats
The purpose of this task is to add a new endpoint to simulate the presence of people on the seats.
The API should be limited, to allow a single entrypoint/access: a unique token or API key not linked to an existing user, configured in the settings file.
.
*DoD*:
* the new endpoint should be accessible only with the configured token/key


## [BE] Integrate Swagger
The purpose of this task is to integrate Swagger
.
*DoD*:
* swagger can be used to view and use the endpoints


## [Analysis] Check the csv download feature
The purpose of this task is to create an SQL script to generate a lot of user reservations (200k or more) and test the CSV download response time
.

 *DoD*:
* add SQL script in the ticket * add conclusions in the ticket
In Progress Review Done
