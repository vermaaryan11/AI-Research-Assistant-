# AI Research Assistant 🤖

An AI-powered research assistant built using **Java, Spring Boot, and Google Gemini API** to simplify research and information processing. The application processes user-provided text and generates concise summaries or suggests related topics and further reading using generative AI.

## ✨ Features

- **AI-Powered Summarization:** Converts lengthy text into clear, concise summaries.
- **Related Topic Suggestions:** Recommends relevant topics and further reading based on the supplied content.
- **RESTful API:** Provides a REST endpoint for submitting content and specifying the desired operation.
- **Gemini API Integration:** Uses Google's Gemini generative AI model to process text and generate responses.
- **Structured Request Handling:** Accepts content and operation parameters through JSON requests.
- **Modular Architecture:** Separates the controller, service layer, request model, and API response model for maintainability.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **Java** | Core programming language |
| **Spring Boot** | Backend application framework |
| **Spring Web** | REST API development |
| **Spring WebFlux WebClient** | HTTP communication with the Gemini API |
| **Google Gemini API** | AI-powered text summarization and topic suggestions |
| **Jackson** | JSON response deserialization |
| **Lombok** | Reduces boilerplate code using annotations such as `@Data` and `@AllArgsConstructor` |
| **Maven** | Build and dependency management, if configured in the project |

## ⚙️ How It Works

1. The client submits research content and the required operation through a REST API.
2. The controller receives the request and forwards it to the service layer.
3. The service constructs a prompt based on the selected operation.
4. The prompt is sent to the configured Google Gemini API using Spring WebClient.
5. The Gemini response is parsed into Java objects using Jackson.
6. The generated text is returned to the client.

## 🔌 API Documentation

### Process Research Content

**Endpoint:** `POST /api/research/process`

**Content-Type:** `application/json`

### 1. Summarize Content

**Request Body:**

```json
{
  "content": "Artificial intelligence is transforming industries by enabling machines to perform tasks that typically require human intelligence.",
  "operation": "summarize"
}
```

**Expected Result:** A concise summary of the supplied content.

### 2. Suggest Related Topics

**Request Body:**

```json
{
  "content": "Artificial intelligence and machine learning",
  "operation": "suggest"
}
```

**Expected Result:** Relevant related topics and suggestions for further reading.

### Supported Operations

| Operation | Description |
|---|---|
| `summarize` | Generates a concise summary of the supplied text |
| `suggest` | Suggests related topics and further reading |

## 📁 Project Structure

```text
src/
└── main/
    └── java/
        └── com/
            └── research/
                └── assistant/
                    ├── ResearchAssistantApplication.java
                    ├── ResearchController.java
                    ├── ResearchService.java
                    ├── ResearchRequest.java
                    ├── GeminiResponse.java
                    └── WebClientConfig.java
```

### Key Components

- **ResearchAssistantApplication:** Entry point of the Spring Boot application.
- **ResearchController:** Exposes the research processing REST endpoint.
- **ResearchService:** Builds prompts, communicates with the Gemini API, and extracts generated responses.
- **ResearchRequest:** Represents the incoming content and operation.
- **GeminiResponse:** Maps the Gemini API response structure to Java objects.
- **WebClientConfig:** Configures the WebClient builder used for external API communication.

## 🚀 Getting Started

### Prerequisites

- Java Development Kit (JDK) compatible with your project configuration
- Maven, if the project uses Maven
- A Google Gemini API key
- An IDE such as IntelliJ IDEA or Visual Studio Code

### 1. Clone the Repository

```bash
git clone https://github.com/vermaaryan11/AI-Research-Assistant-.git
```

### 2. Navigate to the Project Directory

```bash
cd AI-Research-Assistant-
```

### 3. Configure API Credentials

Configure the following properties in your local `application.properties` file or through environment-based configuration:

```properties
gemini.api.url=${GEMINI_API_URL}
gemini.api.key=${GEMINI_API_KEY}
```

Set `GEMINI_API_URL` to the appropriate Gemini API endpoint for the model you are using, and `GEMINI_API_KEY` to your valid API key.

**Security Note:** Never commit API keys, passwords, or other secrets to GitHub. Store credentials in environment variables or a local configuration file excluded through `.gitignore`.

### 4. Run the Application

For a Maven project with the Maven wrapper, use:

**Windows PowerShell:**

```powershell
.\mvnw.cmd spring-boot:run
```

**Linux/macOS:**

```bash
./mvnw spring-boot:run
```

If the project does not contain a Maven wrapper, use the build tool configured in your repository.

### 5. Test the API

Once the application is running, send a POST request to:

```text
http://localhost:8080/api/research/process
```

You can test the endpoint using Postman or another HTTP client by supplying one of the JSON request bodies documented above.

## 🔮 Future Enhancements

- Support for additional research operations.
- Integration with academic paper and research publication sources.
- Improved exception handling and API error responses.
- Request validation and automated testing.
- A web-based user interface for interacting with the assistant.
- Enhanced research workflows and more detailed AI-generated insights.

## 👨‍💻 Author

**Aryan Verma**

GitHub: [@vermaaryan11](https://github.com/vermaaryan11)

---

⭐ If you find this project interesting, consider giving the repository a star!
