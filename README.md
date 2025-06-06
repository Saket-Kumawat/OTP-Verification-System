# 📲 OTP Verification System (Go + Twilio + Gin)

This project is a simple and secure OTP (One-Time Password) verification backend system built with **Go**, the **Gin web framework**, and **Twilio Verify API**. It allows users to:

- Send an OTP to a phone number via SMS
- Verify the OTP entered by the user

---

## ✨ Features

- 🔒 OTP generation & validation using Twilio Verify
- 📱 SMS-based authentication
- ⚙️ REST API built with Go and Gin
- 📦 Environment variable support via `.env`
- ✅ Input validation using `go-playground/validator`
- 🔁 Compatible with Postman for manual testing

---

## 🚀 How It Works

1. User submits their phone number to `/otp`
2. Server calls Twilio Verify API to send OTP
3. User enters the OTP and submits it to `/verifyOTP`
4. Server checks OTP using Twilio and responds with success/failure

---

## 🔐 Prerequisites

- [Go](https://golang.org/dl/) 1.20+
- A [Twilio](https://twilio.com) account with Verify service
- A verified phone number (if on trial)

---

## ⚙️ Setup Instructions

### 1. Clone the Repo

```bash
git clone https://github.com/Saket-Kumawat/otp-verification-system.git
cd otp-verification-system
2. Create .env File

🔐 Never commit your .env file to Git!

3. Run the Server
go mod tidy
go run main.go
Server starts at: http://localhost:8000

📬 API Endpoints
➤ POST /otp
Request Body:

{
  "phoneNumber": "+91XXXXXXXXXX"
}
Response:

{
  "status": 202,
  "message": "success",
  "data": "OTP sent successfully"
}

➤ POST /verifyOTP
Request Body:
{

  "user": {
    "phoneNumber": "+91XXXXXXXXXX"
  },
  "code": "123456"
}
Response:

{
  "status": 202,
  "message": "success",
  "data": "OTP verified successfully"
}


🧪 Testing with Postman
Open Postman

Create a POST request to http://localhost:8000/otp for sending otp and (http://localhost:8000/verifyOTP) for verifing otp
