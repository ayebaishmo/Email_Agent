# Email_Agent
An email and AI agent that helps one to create masages


# Email Sending App

This app allows you to send emails programmatically via Gmail using the SMTP protocol. The email content, subject, and recipient are dynamically generated and sent using a Gmail account that requires an app-specific password for enhanced security.

## Features

- **Send Emails**: Automatically send emails with custom subject and body.
- **Environment Variables**: Securely store Gmail credentials using a `.env` file.
- **SMTP over SSL**: Sends emails via Gmail’s SMTP server with SSL encryption.
- **Error Handling**: Includes error handling to catch and display any login or sending issues.

## Requirements

- Python 3.x
- Gmail account with 2-Step Verification enabled and an app password generated
- Libraries:
  - `smtplib` (Python Standard Library)
  - `email` (Python Standard Library)
  - `python-dotenv`

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/email-sending-app.git
   cd email-sending-app
   ```

2. **Create a virtual environment** (Optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scriptsctivate`
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Create a `.env` file** in the root of your project and add the following environment variables:
   ```env
   SENDER_EMAIL=your-email@gmail.com
   GMAIL_APP_PASSWORD=your-app-password
   ```

   You can generate an app password by following [this guide](https://support.google.com/accounts/answer/185833?hl=en) if you have 2-Step Verification enabled on your Gmail account.

5. **Run the app**:
   Once everything is set up, you can run the app by executing the Jupyter notebook or Python script in your environment.

## Usage

1. **Import necessary libraries and load environment variables**:

   In the notebook, the code reads credentials stored in the `.env` file securely:

   ```python
   import smtplib
   from email.message import EmailMessage
   from dotenv import load_dotenv
   import os

   load_dotenv()  # Load environment variables from .env file

   SENDER_EMAIL = os.getenv('SENDER_EMAIL')
   GMAIL_APP_PASSWORD = os.getenv('GMAIL_APP_PASSWORD')
   ```

2. **Define email generation and sending functions**:

   - **`generate_email(subject, body)`**: Creates a simple email body using the subject and body text.
   - **`send_email(to_email, subject, body)`**: Logs into Gmail’s SMTP server and sends the email.

3. **Send an email**:

   Example of sending an email:

   ```python
   email_body = generate_email("Meeting Request", "Requesting a meeting on Tuesday at 10 AM.")
   send_email("recipient-email@example.com", "Meeting Request", email_body)
   ```

   - Replace `recipient-email@example.com` with the desired recipient's email address.
   - Customize the subject and body as needed.

## Example Output

After successfully sending the email, you should see:
```
Email sent successfully!
```

If there is an error, it will be displayed with details, such as authentication issues or server connection failures.

## Troubleshooting

- **SMTP Authentication Error**: If you encounter an authentication error, ensure that you are using an app password and not your regular Gmail password. If you haven't generated one yet, [follow these steps](https://support.google.com/accounts/answer/185833?hl=en).
- **Missing Environment Variables**: Make sure the `.env` file is properly configured and located in the same directory as your notebook.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For support, please reach out to [your-email@example.com].



