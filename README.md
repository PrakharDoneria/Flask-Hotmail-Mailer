# Hotmail Flask Mailer

`hotmail-flask-mailer` is a Flask-based library for sending emails through Microsoft's Hotmail/Outlook service using the `mailer` package. This library provides a simple API for saving email credentials and sending emails.

## Features

- Easily send emails through a Flask API endpoint.
- Save email credentials securely within your application.
- Simple, lightweight, and easy to integrate with your Flask projects.

## Installation

To install `hotmail-flask-mailer`, use pip:

```bash
pip install hotmail-flask-mailer
```

Ensure you also have Flask and the mailer package installed:

```bash
pip install Flask mailer
```

## Usage

### 1. Basic Setup

You can use `hotmail-flask-mailer` by running the Flask application provided in the package. Here's a simple guide to get you started:

```python
# app.py

from hotmail_flask_mailer.app import mailer_instance, app

# Run the Flask app
if __name__ == "__main__":
    app.run(debug=True)
```

### 2. Saving Email Credentials

Use the `save` function to store your email credentials securely:

```python
from hotmail_flask_mailer.app import mailer_instance

# Save your Hotmail credentials
mailer_instance.save(email="your_hotmail@example.com", password="your_password")
```

### 3. Sending Emails

Once credentials are saved, use the `send` function to send an email:

```python
# Send an email
status = mailer_instance.send(
    receiver="receiver@example.com",
    subject="Hello from Hotmail",
    message="This is a test message sent using Hotmail Flask Mailer."
)

# Check if the email was sent successfully
if status:
    print("Email sent successfully!")
else:
    print("Failed to send email.")
```

### 4. Sending Emails via API Endpoint

Alternatively, you can send emails by making a POST request to the `/send_email` endpoint of the running Flask app:

#### Example Request

```http
POST /send_email
Content-Type: application/json

{
    "email": "your_hotmail@example.com",
    "password": "your_password",
    "receiver": "receiver@example.com",
    "subject": "Hello from Hotmail",
    "message": "This is a test message sent using Hotmail Flask Mailer."
}
```

### 5. Running the Flask Application

To run the application:

1. Save your `app.py` as shown above.
2. Run the Flask app:

   ```bash
   python app.py
   ```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request or open an Issue.

## Support

If you have any questions or need help, feel free to open an issue on GitHub.

```

Replace `"your_hotmail@example.com"`, `"your_password"`, and other placeholder values with actual credentials or demo values as needed. Make sure to guide users on the basics of running the Flask app and using the provided functions.

Feel free to modify the `README.md` as per your specific requirements or add more sections if needed, such as FAQs, troubleshooting tips, or detailed contribution guidelines. Let me know if you need further customization or additional sections!