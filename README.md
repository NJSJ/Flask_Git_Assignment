A Flask web application that handles userform submissions, stores records securelyin MongoDB, and provides a JSON API endpoint. 

Features
* Renders templates
* Form Submission
* Connects to MongoDB.
* Serves structured data from `data.json`.

## Project Structure


flask-tutorial/
    app.py              # Main Flask application
    data.json           # JSON data file for the /api endpoint
    requirements.txt    # Python dependencies
    .env                # Local environment configuration
    README.md           # Project notes
    templates           # HTML templates
        form.html       # Submission form template
        success.html    # Submission confirmation page

## LocalSetup
Pre-requisites: Python,MongoDB Atlas account

Database Configuration (MongoDB Atlas)
-Create a free-tier database cluster.
-Navigate to Database Access.Create a user.
-Navigate to Network Access and add your IP address (or 0.0.0.0/0 for development access).
-Select Connect -> Drivers to copy your MongoDB connection string.

#.env
Create .env file in your root directory. File contains credentials.

## Running application
python app.py
Response visible in http://127.0.0.1:5000
(Logging,error prevention and input validation is done.)

##Routes
/ - returns form.html page
/submit - to accept data from the form and store in db
/success - display success info
/api - returns json data froom data.json
/health - returns db health

# Testing
Open http://127.0.0.1:5000/.Enter name and email and then click Submit.
You will be redirected to /success, and a new record will be inserted into your MongoDB.

