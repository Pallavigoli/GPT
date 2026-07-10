# GPT

A Spring Boot–based REST API that lets you send a question/prompt and get back an answer — no database required. Built with Java 17 and Spring Boot 4, it uses Spring's `WebClient` to call a language-model API and expose the response through a simple `WebMVC` endpoint that you can hit directly from Postman or a browser.

## Features

- Simple REST endpoint to submit a question and receive an answer
- Uses Spring `WebClient` for non-blocking HTTP calls to the GPT/LLM API
- Lightweight — no database or persistence layer needed
- Built and managed with Maven

## Tech Stack

- **Language:** Java 17
- **Framework:** Spring Boot 4.0.3
- **HTTP Client:** Spring WebClient (`spring-boot-starter-webflux`)
- **Web Layer:** Spring WebMVC (`spring-boot-starter-web`)
- **Build Tool:** Maven

## Prerequisites

- Java 17 or later
- Maven 3.6+
- An API key for the language-model provider you're calling (set as an environment variable / in `application.properties`, e.g. `OPENAI_API_KEY`)

## Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/Pallavigoli/GPT.git
   cd GPT
   ```

2. **Configure your API key**
   Add your LLM provider's API key to `src/main/resources/application.properties`:
   ```properties
   openai.api.key=YOUR_API_KEY_HERE
   ```

3. **Build the project**
   ```bash
   mvn clean install
   ```

4. **Run the application**
   ```bash
   mvn spring-boot:run
   ```
   The app starts on `http://localhost:8080` by default.

## Usage

Send a question directly from Postman or your browser — no setup or database needed.

**Example (Postman / curl):**
```bash
curl -X POST http://localhost:8080/api/ask \
  -H "Content-Type: application/json" \
  -d '{"question": "What is Spring Boot?"}'
```

**Response:**
```json
{
  "answer": "Spring Boot is a framework that simplifies building production-ready Spring applications..."
}
```

> Note: Update the endpoint path above (`/api/ask`) to match your actual controller mapping.

## Project Structure

```
GPT/
├── src/
│   ├── main/
│   │   ├── java/         # Application source code (controllers, services)
│   │   └── resources/    # application.properties, config
│   └── test/              # Unit tests
├── pom.xml                # Maven build configuration
└── README.md
```

## Author

**Pallavi Goli**
GitHub: [@Pallavigoli](https://github.com/Pallavigoli)
