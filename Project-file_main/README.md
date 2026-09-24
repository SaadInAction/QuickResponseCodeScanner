# Quick Response Code Scanner API

A simple and practical REST API project for scanning, processing and managing QR code and barcode data.

This project was built to understand how a backend API can receive barcode information, validate it, process it and maintain scan history. The API is designed with a clean structure so it can be connected with web applications, mobile apps or other systems in the future.

## Features

* Barcode scanning and validation
* QR Code scanning support
* Supports common barcode formats such as:

  * Code128
  * EAN13
  * UPC
  * QR Code
* REST API based architecture
* Scan history management
* Input validation
* API key based authentication
* Error handling
* Configurable barcode processing
* Database support
* Docker support
* Easy integration with frontend applications

## Tech Stack

* Python
* REST API
* PostgreSQL
* Docker
* Git & GitHub
* JSON
* Environment Variables

## Project Structure

BarcodeScannerAPI/
│
├── app.py
├── requirements.txt
├── .env
├── Dockerfile
├── README.md
│
├── api/
├── models/
├── services/
├── utils/
└── tests/

## Getting Started

### 1. Clone the Repository

git clone https://github.com/Ali-hey-0/BarcodeScannerAPI.git

cd BarcodeScannerAPI

### 2. Create a Virtual Environment

python -m venv venv

For Windows:

venv\Scripts\activate

For Linux/macOS:

source venv/bin/activate

### 3. Install Dependencies

pip install -r requirements.txt

## Configuration

Create a `.env` file in the project folder.

Example:

API_HOST=0.0.0.0

API_PORT=5000

DEBUG=False

DATABASE_URL=postgresql://user:password@localhost:5432/barcode_db

API_KEY_SECRET=your_secret_key

MAX_BARCODE_LENGTH=1000

SUPPORTED_FORMATS=CODE128,EAN13,UPC,QRCODE

PROCESSING_TIMEOUT=30

Keep sensitive information such as database passwords and API secrets inside the `.env` file and never upload them to GitHub.

## Running the Project

Start the API using:

python app.py

The API will be available at:

http://localhost:5000

## API Endpoints

### Scan Barcode

POST /api/v1/scan

Example Request:

{
"barcode": "123456789012",
"format": "EAN13",
"metadata": {
"location": "warehouse_a"
}
}

### Get Scan History

GET /api/v1/scans

Example Response:

{
"success": true,
"total": 1,
"scans": [
{
"barcode": "123456789012",
"format": "EAN13",
"processed_at": "2026-09-24",
"metadata": {
"location": "warehouse_a"
}
}
]
}

### Generate API Key

POST /api/v1/auth/generate-key

## Authentication

Protected API requests can use an API key through the Authorization header.

Example:

curl -X GET http://localhost:5000/api/v1/scans -H "Authorization: Bearer YOUR_API_KEY"

## Error Handling

The API uses standard HTTP status codes to handle different types of requests and errors.

200 - Request successful

400 - Invalid request or barcode

401 - Authentication failed

404 - Resource not found

500 - Internal server error

Example Error Response:

{
"success": false,
"error": {
"message": "The provided barcode is invalid",
"code": "INVALID_BARCODE"
}
}

## Docker

The project can also be run using Docker.

Build the Docker image:

docker build -t barcode-scanner-api .

Run the container:

docker run -p 5000:5000 barcode-scanner-api

Then open:

http://localhost:5000

## Why I Built This Project

I built this project to get practical experience in backend development and REST API design.

The main goal was to understand how a real backend application receives data, validates requests, processes information, stores records and provides structured API responses.

Working on this project also helped me improve my understanding of Python backend development, API authentication, database integration, error handling and API testing.

## Future Improvements

Some features I would like to add in future versions:

* Camera based barcode scanning
* QR code image scanning
* Real-time barcode detection
* User login and role-based access
* Better dashboard for scan history
* Advanced analytics and reports
* Redis based caching
* Cloud deployment
* Automated testing
* Swagger/OpenAPI documentation
* Integration with inventory management systems
* Mobile application integration

## Testing

The API can be tested using:

* Postman
* cURL
* Swagger/OpenAPI
* Python automated tests

## Contributing

If you have any suggestions, improvements or new ideas, feel free to create an issue or submit a pull request.

1. Fork the repository

2. Create a new branch

git checkout -b feature-name

3. Make your changes

4. Commit your changes

git add .

git commit -m "Add new feature"

5. Push the branch

git push origin feature-name

6. Create a Pull Request

## License

This project is available under the MIT License.

## Author

Mohammed Saad

IT Engineer & Corporate Trainer

GitHub: SaadInAction

---

Thanks for checking out my project!

Also guys If you find this project useful, feel free to  star the repository and follow me for more projects and updates.
