

This project provides an API for uploading and processing CSV files using Django and Django REST Framework (DRF). It validates and extracts data from a CSV file and stores valid records in a database while handling errors gracefully.

Files Included

test_csv.csv: Sample CSV file for testing.

test_users.csv: Additional test data.

csv_project.rar: Compressed project folder containing the full codebase.

json_response.txt: Contains sample JSON output from the API.

postman_screenshot.png: Screenshot of API testing in Postman.

Setup and Installation

1. Extract the Project Files

Unzip the csv_project.rar file to access the source code.

2. Install Dependencies

Ensure you have Python installed, then install the required packages:


3. Run Database Migrations

python manage.py makemigrations
python manage.py migrate

4. Start the Development Server

python manage.py runserver

The server will start at http://127.0.0.1:8000/.

API Usage

Uploading a CSV File

Endpoint: POST http://127.0.0.1:8000/upload/csv/

Field Name: file

Testing: Use Postman or any API client to send a POST request with a CSV file.

Example Request in Postman

Open Postman and select POST method.

Enter http://127.0.0.1:8000/upload/csv/ in the URL.

Under the Body tab, select form-data.

Add a key named file, choose File, and upload a CSV file.

Click Send.

Expected JSON Response

{
  "records_saved": 3,
  "records_failed": 2,
  "errors": [
    {"row": 3, "error": "Invalid email format"},
    {"row": 5, "error": "Age must be between 0 and 120"}
  ]
}


The API ensures that duplicate emails are skipped.

CSV data is validated before being stored in the database.

Check the json_response.txt file for sample output.

Refer to postman_screenshot.png for an example of API testing.

Contributions

Feel free to fork the repository, make improvements, and submit a pull request.
