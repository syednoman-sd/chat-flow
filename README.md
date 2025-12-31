# ChatFlow

A modern AI-powered chat application built with Bun, React, TypeScript, and OpenAI. This full-stack chatbot lets you have intelligent conversations with AI in a beautiful, responsive interface.

## 🚀 Features

- **🤖 AI-Powered Chat**: Integrated with OpenAI GPT-4o-mini for smart conversations
- **💬 Real-time Messaging**: Instant chat experience with typing indicators
- **🎨 Beautiful UI**: Modern interface built with React 19, Tailwind CSS, and shadcn/ui
- **⚡ Lightning Fast**: Powered by Bun runtime for blazing-fast performance
- **📝 Markdown Support**: Rich text formatting in chat messages
- **� Conversation Memory**: Maintains context throughout the conversation
- **🎯 TypeScript**: Full type safety across the entire stack
- **� Monorepo Structure**: Clean separation between client and server code

## 📁 Project Structure

```
.
├── packages/
│   ├── client/                    # React + Vite frontend
│   │   ├── src/
│   │   │   ├── components/
│   │   │   │   └── chat/          # Chat components
│   │   │   │       ├── ChatBot.tsx
│   │   │   │       ├── ChatInput.tsx
│   │   │   │       ├── ChatMessages.tsx
│   │   │   │       └── TypingIndicator.tsx
│   │   │   └── App.tsx
│   │   └── vite.config.ts
│   └── server/                    # Express.js backend
│       ├── controllers/           # Request handlers
│       │   └── chat.controller.ts
│       ├── services/              # Business logic
│       │   └── chat.service.ts
│       ├── repositories/          # Data management
│       │   └── conversation.repository.ts
│       ├── routes.ts              # API routes
│       └── index.ts
├── package.json                   # Root workspace configuration
└── index.ts                       # Development orchestrator
```

## 🛠️ Tech Stack

### Frontend

- **React 19** - Latest React with modern features
- **Vite** - Next-generation frontend tooling
- **TypeScript** - Type-safe development
- **Tailwind CSS** - Utility-first CSS framework
- **shadcn/ui** - Beautiful, accessible component library
- **React Hook Form** - Form handling and validation
- **React Markdown** - Markdown rendering in chat messages
- **Axios** - HTTP client for API requests

### Backend

- **Bun** - Fast all-in-one JavaScript runtime
- **Express.js** - Minimal and flexible web framework
- **TypeScript** - Type-safe server development
- **OpenAI API** - GPT-4o-mini integration for AI responses
- **Zod** - Schema validation for API requests

### Development Tools

- **ESLint** - Code linting
- **Prettier** - Code formatting
- **Concurrently** - Run multiple commands simultaneously

## 📋 Prerequisites

- [Bun](https://bun.sh) >= 1.0.0
- OpenAI API Key (get it from [OpenAI Platform](https://platform.openai.com/api-keys))

## 🚀 Getting Started

1. **Clone the repository**

   ```bash
   git clone https://github.com/syednoman-sd/chat-flow.git
   cd chat-flow
   ```

2. **Install dependencies**

   ```bash
   bun install
   ```

3. **Set up environment variables**

   Create a `.env` file in the `packages/server` directory:

   ```env
   PORT=3000
   OPENAI_API_KEY=your_openai_api_key_here
   ```

4. **Start development servers**

   ```bash
   bun run dev
   ```

   This will start:
   - Frontend dev server at `http://localhost:5173`
   - Backend API server at `http://localhost:3000`

5. **Open your browser**

   Navigate to `http://localhost:5173` and start chatting with the AI!

## 📝 Available Scripts

### Root Level

- `bun run dev` - Start both client and server in development mode
- `bun run format` - Format code with Prettier

### Client (`packages/client`)

- `bun run dev` - Start Vite dev server
- `bun run build` - Build for production
- `bun run lint` - Lint code with ESLint
- `bun run preview` - Preview production build

### Server (`packages/server`)

- `bun run dev` - Start server with hot reload
- `bun run start` - Start server in production mode

## 🔧 Configuration

### Environment Variables

The server requires the following environment variables in `packages/server/.env`:

```env
PORT=3000                          # Server port (default: 3000)
OPENAI_API_KEY=sk-...             # Your OpenAI API key
```

### API Endpoints

- `POST /api/chat` - Send a message to the AI chatbot
- Request body: `{ prompt: string, conversationId: string }`
- Response: `{ message: string }`

### How It Works

1. **Frontend**: User types a message in the chat input
2. **API Call**: Message is sent to `/api/chat` endpoint with conversation ID
3. **Backend**: Server validates the request and calls OpenAI API
4. **AI Response**: OpenAI generates a response based on conversation history
5. **Display**: Response is shown in the chat interface with markdown support

## 🏗️ Building for Production

1. **Build the client**

   ```bash
   cd packages/client
   bun run build
   ```

2. **Start the server**

   ```bash
   cd packages/server
   bun run start
   ```

## ✨ Key Features Explained

### Chat Components

- **ChatBot**: Main component managing chat state and API calls
- **ChatInput**: Text input with Enter key support and character limit (1000 chars)
- **ChatMessages**: Displays messages with markdown rendering and auto-scroll
- **TypingIndicator**: Animated dots showing when AI is thinking

### Backend Architecture

- **Controller Layer**: Handles HTTP requests and validation
- **Service Layer**: Business logic and OpenAI API integration
- **Repository Layer**: Manages conversation state and history

### Conversation Memory

The app maintains conversation context using OpenAI's `previous_response_id` feature, allowing the AI to remember previous messages in the conversation.

## 🤝 Contributing

Contributions are welcome! Feel free to submit a Pull Request.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- Built with [Bun](https://bun.sh)
- AI powered by [OpenAI](https://openai.com)
- UI components from [shadcn/ui](https://ui.shadcn.com)
- Styled with [Tailwind CSS](https://tailwindcss.com)

---

**Happy Chatting! 💬✨**
