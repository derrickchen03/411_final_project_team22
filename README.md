# 411-final-project-team22

## Project Description
This application allows users to store favorite weather locations in a dictionary and then request information regarding that location including the current weather (ie temperature, wind speed, precipitation), or the next day forecast or the historical weather of that location. The application also returns the attributes of all favorites saved if desired.

### Route Documentation
#### User Management 
```
Route: /create-user

Request Type: POST
Purpose: Adds a new user.
Request Body:
    username (str): user's new username
    password (str): user's chosen password
Response Format: JSON
    Success Response:
        Code: 200
        Content: {'status': 'success', 'username': username}
Example Request:
    {
        "username": "newuser",
        "password": "password"
    }
Example Response:
    {
        "'status': 'success', 'username': newuser",
        "status": "200"
    }
```
```
Route: /remove-user

Request Type: DELETE
Purpose: Deletes an existing user.
Request Body:
    username (str): user username which already exists
Response Format: JSON
    Success Response:
        Code: 200
        Content: {'status': 'success', 'username': username}
Example Request:
    {
        "username": "newuser"
    }
Example Response:
    {
        "'status': 'success', 'username': newuser",
        "status": "200"
    }
```
```
Route: /change-password

Request Type: POST
Purpose: Changes the password of an existing user.
Request Body:
    username (str): user username which already exists
    password (str): user's chosen new password
Response Format: JSON
    Success Response:
        Code: 200
        Content: {'status': 'success', 'username': username}
Example Request:
    {
        "username": "newuser",
        "password": "newpass"
    }
Example Response:
    {
        "'status': 'success', 'username': newuser",
        "status": "200"
    }
```
```
Route: /compare-password

Request Type: PUT
Purpose: Compares the username and password that is entered to that which already exists.
Request Body:
    username (str): user username which already exists
    password (str): user's password
Response Format: JSON
    Success Response:
        Code: 200
        Content: {'status': 'success', 'username': username}
Example Request:
    {
        "username": "newuser",
        "password": "newpass"
    }
Example Response:
    {
        "'status': 'success', 'username': newuser",
        "status": "200"
    }
```
```
Route: /login

Request Type: POST
Purpose: Logins in a user
Request Body:
    username (str): user's username which already exists
    password (str): user's password
Response Format: JSON
    Success Response:
        Code: 200
        Content: {"message": f"User {username} logged in successfully."}
Example Request:
    {
        "username": "newuser",
        "password": "password"
    }
Example Response:
    {
        "message": "User newuser logged in successfully",
        "status": "200"
    }
```
#### Favorites Management
```
Route: /add-favorite

Request Type: POST
Purpose: Adds a favorite to the user's list of favorites
Request Body:
    location (str): The location to be added to the favorites.
Response Format: JSON
    Success Response:
        Code: 200
        Content: {'status': 'success', 'location': location}
Example Request:
    {
        "location": "Boston"
    }
Example Response:
    {
        "'status': 'success', 'location': 'Boston'",
        "status": "200"
    }
```
```
Route: /get-favorite-weather/<str:location>

Request Type: GET
Purpose: Gets the weather for a favorite location.
Request Body:
    location (str): location whose weather will be retrieved.
Response Format: JSON
    Success Response:
        Code: 200
        Content: {'status': 'success', 'weather': weather}
Example Request:
    {    
        "location": "Boston"
    }
Example Response:
    {
        "'status': 'success', 'weather': [('temp', 34.0), ('wind', 4.0), ('precipitation', 0.0), ('humidity', 100)]",
        "status": "200"
    }
```
```
Route: /get-all-favorites-current-weather

Request Type: GET
Purpose: Gets the current weather for all locations in favorites.
Request Body:
    N/A
Response Format: JSON
    Success Response:
        Code: 200
        Content: {'status': 'success', 'favorite weather': weather}
Example Request:
Example Response:
    {
        "'status': 'success', 'favorite weather': [[('temp', 34.0), ('wind', 4.0), ('precipitation', 0.0), ('humidity', 100)], [('temp', 28.0), ('wind', 1.0), ('precipitation', 1.0), ('humidity', 10)]]",
        "status": "200"
    }
```
```
Route: /get-favorite-historical/<str:location>

Request Type: GET
Purpose: Gets the historical weather for a favorite location
Request Body:
    location (str): location whose historical weather will be retrieved.
Response Format: JSON
    Success Response:
        Code: 200
        Content: {'status': 'success', 'historical weather': weather}
Example Request:
    {    
        "location": "Boston"
    }
Example Response:
    {
        "'status': 'success', 'historical weather': [('temp', 38.0), ('wind', 13.2), ('precipitation', 0.06), ('humidity', 96)]",
        "status": "200"
    }
```
```
Route: /get-favorite-forecast/<str:location>

Request Type: GET
Purpose: Gets the next day forecast for a favorite location
Request Body:
    location (str): location whose forecast will be retrieved.
Response Format: JSON
    Success Response:
        Code: 200
        Content: {'status': 'success', 'forecast': weather}
Example Request:
    {    
        "location": "Boston"
    }
Example Response:
    {
        "'status': 'success', 'forecast': ["date": '2024-12-10', "max_temp": 39.0, "min_temp": 34]",
        "status": "200"
    }
```
```
Route: /clear-favorites
Request Type: DELETE
Purpose: Clear the dictionary of the user's favorite weather locations.
Request Body:
    N/A
Response Format: JSON
    Success Response Example:
        Code: 200
        Content: {"status": "success"}
Example Request:
Example Response:
    {
        "'status': 'success'",
        "status": "200"
    }
```
```
Route: /get-all-favorites

Request Type: GET
Purpose: Gets all locations in favorites.
Request Body:
    N/A
Response Format: JSON
    Success Response:
        Code: 200
        Content: {'status': 'success', 'favorite list': fav_list}
Example Request:
Example Response:
    {
        "'status': 'success', 'favorite list': ["Boston", "New York", "Springfield"] ",
        "status": "200"
    }
```
