# AI Chatbot with Document Q&A and Appointment Booking

A modern, intelligent chatbot application that combines document Q&A capabilities with appointment booking functionality. Built with FastAPI, React, and Google's Gemini AI, this application provides a seamless experience for users to interact with documents and schedule appointments.

## 🌟 Features

### Document Q&A Capabilities
- Support for multiple document formats:
  - PDF (.pdf)
  - Text (.txt)
  - Word (.docx)
  - Excel (.xlsx)
  - PowerPoint (.pptx)
  - HTML (.html)
  - Markdown (.md)
- Intelligent document processing using LangChain
- Semantic search and Q&A using Gemini AI
- Document chunking for better context understanding

### Appointment Booking System
- Natural language date parsing
  - "next Monday"
  - "next week"
  - "next month"
  - "this week"
  - And more...
- Time slot selection
- Form validation
- Appointment notes
- Email and phone number validation

### User Interface
- Modern, responsive Material-UI design
- Real-time chat interface
- Document upload with progress indicator
- Interactive appointment booking form
- Error handling with visual feedback
- Clear chat history option

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- Node.js 14+
- Google Cloud API key for Gemini
- Git

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd <repository-name>
```

2. Set up the backend:
```bash
cd backend
pip install -r requirements.txt
```

3. Create a `.env` file in the backend directory:
```
GOOGLE_API_KEY=your_google_api_key_here
```

4. Set up the frontend:
```bash
cd frontend
npm install
```

### Running the Application

1. Start the backend server:
```bash
cd backend
uvicorn main:app --reload
```

2. Start the frontend development server:
```bash
cd frontend
npm start
```

The application will be available at `http://localhost:3000`

## 💡 Usage Guide

### Document Q&A

1. Upload a Document:
   - Click the upload icon in the top-right corner
   - Select a supported document type
   - Wait for the upload confirmation

2. Ask Questions:
   - Type your question about the document
   - The chatbot will search through the document and provide relevant answers
   - You can ask multiple questions about the same document

Example:
```
User: What are the main points in the document?
Bot: Based on the document, the main points are...

User: Can you summarize the first section?
Bot: The first section discusses...
```

### Appointment Booking

1. Initiate Booking:
   - Use keywords like "book", "appointment", "schedule", or "call"
   - Example: "I'd like to book an appointment"

2. Fill the Form:
   - Enter your name (letters and spaces only)
   - Provide a valid email address
   - Enter your phone number (international format)
   - Select a date (using natural language or date picker)
   - Choose a preferred time
   - Add any additional notes

Example:
```
User: I want to book an appointment for next Monday
Bot: I'd be happy to help you book an appointment. Could you please provide your name, email, and phone number?

[Form appears with validation]
```

### Natural Language Date Examples

The chatbot understands various date formats:
- "next Monday"
- "next week"
- "next month"
- "this week"
- "tomorrow"
- "next year"
- Specific dates like "2024-03-15"

## 🔧 Technical Details

### Backend Architecture
- FastAPI for the REST API
- LangChain for document processing
- Google Gemini AI for natural language understanding
- Chroma for vector storage
- Pydantic for data validation

### Frontend Architecture
- React for the UI
- Material-UI for components
- Axios for API calls
- Date-fns for date handling

### API Endpoints

1. Chat Endpoint:
```http
POST /api/chat
Content-Type: application/json

{
    "message": "string",
    "user_info": {
        "name": "string",
        "email": "string",
        "phone": "string",
        "preferred_date": "string",
        "preferred_time": "string",
        "notes": "string"
    }
}
```

2. Document Upload:
```http
POST /api/upload-document
Content-Type: multipart/form-data

file: <file>
```

3. Date Validation:
```http
POST /api/validate-date
Content-Type: application/json

{
    "date_str": "string"
}
```

## 🔒 Validation Rules

### Name Validation
- 2-50 characters
- Only letters and spaces
- Auto-capitalization

### Email Validation
- Standard email format
- Domain validation
- MX record checking

### Phone Validation
- International format
- 9-15 digits
- Optional country code

### Date Validation
- Future dates only
- Natural language parsing
- Multiple format support

## 🛠️ Development

### Adding New Features
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

### Code Structure
```
├── backend/
│   ├── main.py
│   └── requirements.txt
├── frontend/
│   ├── src/
│   │   ├── App.js
│   │   └── index.js
│   └── package.json
└── README.md
```

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📧 Support

For support, please open an issue in the GitHub repository or contact the maintainers.

## 🙏 Acknowledgments

- Google Gemini AI
- LangChain
- FastAPI
- React
- Material-UI
- All contributors and users 