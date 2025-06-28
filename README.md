# FinanceFullStack
FinShark is a full-stack web application designed to help investors access relevant financial data efficiently. The api directory contains the backend implementation of FinShark, built using ASP.NET Core Web API. It provides RESTful endpoints to support user authentication, stock management, portfolio tracking, and comment functionalities.

# FinShark API

**FinShark** is a full-stack web application designed to help investors efficiently access relevant financial data. This repository contains the **backend API**, built with **ASP.NET Core Web API**, providing secure, RESTful endpoints for user authentication, stock management, portfolio tracking, and commenting — all integrated with a **Microsoft SQL Server** database.

The API fetches stock data from external sources like [financialmodelingprep.com](https://financialmodelingprep.com/) and supports searching for companies by ticker (e.g., `AAPL` for Apple) and retrieving **SEC 10-K forms**.

The backend works seamlessly with the **FinShark frontend**, built with **React.js**, **TypeScript**, and **Tailwind CSS**, delivering a smooth user experience.

---

## 🚀 Features

- 🔒 **User Authentication** — Register & log in users securely with JWT tokens
- 📈 **Stock Management** — Create, read, update & delete stock entries (admin only)
- 📊 **Portfolio Management** — Add/remove stocks from user portfolios
- 💬 **Comment System** — Add, update & delete comments on stock pages
- 🛡️ **Admin Management** — Assign roles & manage administrative tasks
- ⚙️ **Rate Limiting** — Control request rates for API stability
- 📏 **Profiling Middleware** — Monitor & optimize app performance
- 🌐 **External Data Integration** — Fetch real-time stock data & SEC filings

---

## 🗂️ Project Structure

api/
├── Controllers/ # Handles HTTP requests & responses
├── Data/ # EF Core DB context & configuration
├── DTOs/ # Data Transfer Objects
├── Helpers/ # Utility classes & functions
├── Models/ # Data models: Stocks, Users, Portfolios, Comments
├── Middleware/ # Rate limiting & profiling middleware
├── Program.cs # ASP.NET Core entry point
├── Startup.cs # App configuration (if .NET 5 or earlier)
├── appsettings.json # Config (DB strings, API keys)
└── FinShark.csproj # Project file & dependencies

yaml
Copy
Edit

---

## 🧰 Prerequisites

- [.NET SDK 6.0+](https://dotnet.microsoft.com/)
- [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) or SQL Server Express
- [Visual Studio](https://visualstudio.microsoft.com/) or VS Code
- API key from [financialmodelingprep.com](https://financialmodelingprep.com/)

---

## ⚙️ Setup Instructions

**1️⃣ Clone the Repository**

```bash
git clone https://github.com/teddysmithdev/FinShark.git
cd FinShark/api
2️⃣ Restore Dependencies

bash
Copy
Edit
dotnet restore







You said:
do not divide, give me all markdown code


ChatGPT said:
Got it! Here’s the entire README.md in one piece, no breaks — fully formatted and ready to paste:

markdown
Copy
Edit
# FinShark API

**FinShark** is a full-stack web application designed to help investors efficiently access relevant financial data. This repository contains the **backend API**, built with **ASP.NET Core Web API**, providing secure, RESTful endpoints for user authentication, stock management, portfolio tracking, and commenting — all integrated with a **Microsoft SQL Server** database.

The API fetches stock data from external sources like [financialmodelingprep.com](https://financialmodelingprep.com/) and supports searching for companies by ticker (e.g., `AAPL` for Apple) and retrieving **SEC 10-K forms**.

The backend works seamlessly with the **FinShark frontend**, built with **React.js**, **TypeScript**, and **Tailwind CSS**, delivering a smooth user experience.

## 🚀 Features

- 🔒 **User Authentication** — Register & log in users securely with JWT tokens
- 📈 **Stock Management** — Create, read, update & delete stock entries (admin only)
- 📊 **Portfolio Management** — Add/remove stocks from user portfolios
- 💬 **Comment System** — Add, update & delete comments on stock pages
- 🛡️ **Admin Management** — Assign roles & manage administrative tasks
- ⚙️ **Rate Limiting** — Control request rates for API stability
- 📏 **Profiling Middleware** — Monitor & optimize app performance
- 🌐 **External Data Integration** — Fetch real-time stock data & SEC filings

## 🗂️ Project Structure

api/
├── Controllers/ # Handles HTTP requests & responses
├── Data/ # EF Core DB context & configuration
├── DTOs/ # Data Transfer Objects
├── Helpers/ # Utility classes & functions
├── Models/ # Data models: Stocks, Users, Portfolios, Comments
├── Middleware/ # Rate limiting & profiling middleware
├── Program.cs # ASP.NET Core entry point
├── Startup.cs # App configuration (if .NET 5 or earlier)
├── appsettings.json # Config (DB strings, API keys)
└── FinShark.csproj # Project file & dependencies

markdown
Copy
Edit

## 🧰 Prerequisites

- [.NET SDK 6.0+](https://dotnet.microsoft.com/)
- [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) or SQL Server Express
- [Visual Studio](https://visualstudio.microsoft.com/) or VS Code
- API key from [financialmodelingprep.com](https://financialmodelingprep.com/)

## ⚙️ Setup Instructions

**1️⃣ Clone the Repository**

```bash
git clone https://github.com/teddysmithdev/FinShark.git
cd FinShark/api
2️⃣ Restore Dependencies

bash
Copy
Edit
dotnet restore
3️⃣ Configure the Database

Update appsettings.json:

json
Copy
Edit
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost;Database=FinSharkDB;Trusted_Connection=True;"
  },
  "FinancialModelingPrep": {
    "ApiKey": "your-api-key-here"
  }
}
4️⃣ Run Migrations

bash
Copy
Edit
dotnet ef migrations add InitialCreate
dotnet ef database update
5️⃣ Run the API

bash
Copy
Edit
dotnet run
The API will be available at:

arduino
Copy
Edit
https://localhost:5001
http://localhost:5000
(Check Properties/launchSettings.json for exact ports.)

🧪 Testing the API
Example request with curl:

bash
Copy
Edit
curl -X GET "https://localhost:5001/api/stocks/AAPL" -H "Authorization: Bearer <your-token>"
Use Postman or cURL to test other endpoints.

📌 Key API Endpoints
Method	Endpoint	Description
POST	/api/auth/register	Register a new user
POST	/api/auth/login	Log in & receive a JWT token
GET	/api/stocks/{ticker}	Get stock details by ticker
POST	/api/stocks	Create stock (admin only)
PUT	/api/stocks/{id}	Update stock (admin only)
DELETE	/api/stocks/{id}	Delete stock (admin only)
GET	/api/portfolio	Get user portfolio
POST	/api/portfolio	Add stock to portfolio
DELETE	/api/portfolio/{stockId}	Remove stock from portfolio
POST	/api/comments	Add comment to a stock
PUT	/api/comments/{id}	Update comment
DELETE	/api/comments/{id}	Delete comment

Note: Most endpoints require a JWT token in the Authorization header.

🗃️ Dependencies
Microsoft.EntityFrameworkCore.SqlServer

Microsoft.AspNetCore.Authentication.JwtBearer

Microsoft.EntityFrameworkCore.Design

Newtonsoft.Json
