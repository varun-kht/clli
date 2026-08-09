URL shortner 
# 🔗 URL Shortener

A simple and efficient URL Shortener built with **FastAPI** and **PostgreSQL**. This application allows users to convert long URLs into short, unique links and redirect back to the original URL using the generated short code.

---

## ✨ Features

- 🔗 Shorten long URLs
- 🚀 Redirect using short URLs
- 🗄 Store URLs in PostgreSQL
- ⚡ FastAPI REST API
- 📖 Interactive Swagger Documentation
- 🐳 Docker Support

---

## 🛠 Tech Stack

- **Backend:** FastAPI
- **Language:** Python 3
- **Database:** PostgreSQL
- **ORM:** SQLAlchemy
- **Validation:** Pydantic
- **Server:** Uvicorn
- **Containerization:** Docker

---

## 📂 Project Structure

```text
url-shortener/
│
├── app/
│   ├── api/
│   ├── models/
│   ├── schemas/
│   ├── services/
│   ├── database/
│   ├── config/
│   └── main.py
│
├── requirements.txt
├── docker-compose.yml
├── Dockerfile
└── README.md
```

---

## 🚀 API Endpoints

### Create Short URL

```http
POST /shorten
```

**Request**

```json
{
  "url": "https://www.example.com"
}
```

**Response**

```json
{
  "short_url": "http://localhost:8000/Ab12Cd"
}
```

---

### Redirect to Original URL

```http
GET /{short_code}
```

Redirects the user to the original URL.

---

## 🗄 Database Schema

| Column | Type |
|---------|------|
| id | UUID |
| original_url | TEXT |
| short_code | VARCHAR |
| created_at | TIMESTAMP |

---

## ⚙️ Installation

### Clone the Repository

```bash
git clone https://github.com/your-username/url-shortener.git
cd url-shortener
```

### Create Virtual Environment

```bash
python -m venv .venv
```

### Activate Environment

**Linux / macOS**

```bash
source .venv/bin/activate
```

**Windows**

```bash
.venv\Scripts\activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Configure Environment Variables

Create a `.env` file.

```env
DATABASE_URL=postgresql://username:password@localhost:5432/urlshortener
BASE_URL=http://localhost:8000
```

### Run the Server

```bash
uvicorn app.main:app --reload
```

---

## 📖 API Documentation

Swagger UI

```
http://localhost:8000/docs
```

ReDoc

```
http://localhost:8000/redoc
```

---

## 💡 How It Works

1. User submits a long URL.
2. The server generates a unique short code.
3. The original URL and short code are stored in PostgreSQL.
4. Visiting the short URL redirects the user to the original destination.

---

## 🚧 Future Improvements

- Custom aliases
- Click analytics
- URL expiration
- User authentication
- QR code generation
- Redis caching
- Rate limiting
- Docker Compose deployment
- CI/CD pipeline

---

## 📄 License

MIT License
