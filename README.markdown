# Huiz — Know Better.

A Perplexity-style AI search and answer engine that finds, reasons, and cites sources in real time.  
**Fast, conversational answers with links you can trust.**

![Huiz Screenshot](public/screenshot.png)

Huiz is a modern, AI-powered search engine designed to deliver insightful, well-reasoned responses with inline citations. With a minimal, vintage-inspired UI, Huiz combines real-time web search, conversational AI, and a delightful user experience to help you uncover knowledge swiftly.

## Features

- **🔍 Real-Time Web Search**: Fetches and cites sources instantly using providers like Tavily, with source cards including titles, snippets, and images.
- **🤖 Conversational Answers**: Streams detailed, markdown-formatted reports with inline citations and a collapsible analysis process for transparency.
- **📚 Source Cards**: View source details with links (open in new tab), images, and hoverable tooltips for quick insights.
- **🧠 Dynamic Suggestions**: Offers 24 contextual prompts (e.g., "Analyze," "Research," "Fact Check") with 4 randomly displayed for quick query formulation.
- **⚡ Minimal, Fast UI**: Built with React, TypeScript, Tailwind CSS, and Framer Motion for a smooth, vintage aesthetic with geometric backgrounds and amber tones.
- **🎯 Keyboard-First Experience**: Press `Enter` to submit queries, `Shift+Enter` for newlines in the textarea.
- **📝 Flexible Input**: Supports custom user prompts alongside suggestion-based queries.
- **🖼️ Elegant Loading Animation**: A spinning SVG circle with a "Thinking..." fade effect, matching the vintage aesthetic.
- **🔄 Reset Functionality**: Click the Huiz logo or title to return to the initial prompt screen, clearing all chat history.
- **📜 Auto-Scroll**: Smoothly scrolls to the response area when text generation begins for a seamless experience.
- **🧩 Pluggable LLM Backend**: Bring your own LLM provider (e.g., OpenAI, OpenRouter) via a unified interface.
- **🔒 Provider-Agnostic**: Configure your preferred search and LLM providers through environment variables.

## Tech Stack

- **Frontend**: React, Vite, TypeScript, Tailwind CSS, Framer Motion, React Markdown
- **Backend (Optional)**: Node.js/Express for proxying APIs and server-side features
- **AI**: Any LLM provider (e.g., OpenAI, OpenRouter, Anthropic) via a single interface
- **Search**: Web search APIs (e.g., Tavily, Serper, Exa, You.com)
- **Dependencies**: `react-markdown`, `remark-gfm` for rendering markdown responses with tables and links

## Repository

```bash
git clone https://github.com/Mahatir-Ahmed-Tusher/Huiz.git
cd Huiz
```

## Quick Start

1. **Install Dependencies**

   ```bash
   npm install
   ```

2. **Create `.env` File**

   Create a `.env` file in the project root with the following variables:

   ```env
   # LLM
   LLM_PROVIDER=openai            # e.g., openai | openrouter | anthropic | azure
   LLM_API_KEY=sk-xxx             # Your LLM API key

   # Search
   SEARCH_PROVIDER=tavily         # e.g., tavily | serper | exa | you
   SEARCH_API_KEY=tvly-xxx        # Your search API key

   # Optional (server)
   PORT=3000
   CLIENT_URL=http://localhost:5173
   ```

3. **Run in Development**

   Start the Vite development server:

   ```bash
   npm run dev
   # Vite default: http://localhost:5173
   ```

   If using the optional Node/Express server:

   ```bash
   npm run server
   # Server: http://localhost:3000
   ```

4. **Build for Production**

   ```bash
   npm run build
   ```

5. **Preview Production Build**

   ```bash
   npm run preview
   ```

## Environment Variables

| Key              | Required | Example                    | Purpose                              |
|------------------|----------|----------------------------|--------------------------------------|
| `LLM_PROVIDER`   | ✔        | `openai`                   | Specifies the LLM adapter to use     |
| `LLM_API_KEY`    | ✔        | `sk-...`                   | API key for the chosen LLM          |
| `SEARCH_PROVIDER`| ✔        | `tavily`                   | Specifies the web search provider    |
| `SEARCH_API_KEY` | ✔        | `tvly-...`                 | API key for the search provider     |
| `PORT`           | ✕        | `3000`                     | Server port (if using backend)      |
| `CLIENT_URL`     | ✕        | `http://localhost:5173`    | CORS/redirects for local dev        |

**Tip**: For serverless deployments, call LLM and search APIs directly from serverless functions to securely manage keys.

## NPM Scripts

- `npm run dev`: Starts the Vite development server
- `npm run build`: Builds the production bundle
- `npm run preview`: Previews the production build locally
- `npm run server`: Starts the optional Express server
- `npm run check`: Runs TypeScript type checking

## Project Structure

```
Huiz/
├─ src/
│  ├─ components/          # Reusable UI components
│  ├─ lib/                 # Adapters for LLM and search APIs, fetch utilities
│  ├─ pages/               # Page components (e.g., page.tsx)
│  ├─ styles/              # Tailwind CSS and custom styles
│  └─ main.tsx             # Entry point
├─ server/                 # Optional Node/Express server
├─ public/                 # Static assets (favicon, manifest, images)
├─ .env.example            # Example environment variables
└─ README.md               # Project documentation
```

## Security Notes

- **Never commit `.env` files or API keys** to version control.
- Use environment variables or a secret manager in production.
- Replace all keys/secrets with your own when forking the repository.

## Deployment

- **Frontend**: Deploy to Vercel, Netlify, or similar platforms.
- **Backend (Optional)**: Deploy the Node/Express server to Render, Fly.io, or Heroku.
- Add environment variables in your hosting platform's dashboard.
- Configure `CLIENT_URL` for proper CORS settings in development and production.

## Roadmap

- **Streaming Enhancements**: Add partial citations during response streaming.
- **Session Persistence**: Support pinned threads and saved chat history.
- **Multi-Engine Aggregation**: Combine results from multiple search providers.
- **RAG Support**: Enable Retrieval-Augmented Generation for user-uploaded documents.

## License

[MIT](LICENSE) — Free to use, modify, and share.

## Acknowledgments

- **UX Inspiration**: Perplexity and modern AI search interfaces.
- **UI Components**: Built with primitives from the open-source community (e.g., shadcn/ui).
- **Libraries**: Thanks to `framer-motion`, `react-markdown`, and `remark-gfm` for enabling smooth animations and rich text rendering.

## Star the Repo ⭐

If Huiz helps you explore and discover knowledge, please consider starring the project on [GitHub](https://github.com/Mahatir-Ahmed-Tusher/Huiz)!