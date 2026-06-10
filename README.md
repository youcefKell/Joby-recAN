# AI Resume Analyzer

This project is a client-side web application that analyzes uploaded resumes using AI and provides structured feedback.

## How it works

- Users authenticate via Puter.js.
- Users upload a resume PDF and provide job details.
- The resume file is uploaded to Puter file storage.
- The app converts the PDF to an image for preview and AI context.
- The app sends the document and job information to Puter AI.
- AI returns resume feedback in a structured JSON format.
- The app stores the result in Puter KV storage and shows it on the review page.

## API / AI used

- **Puter.js** is the main external API used by this project.
- It provides:
  - client-side auth
  - file upload and storage
  - key-value storage
  - AI chat integration
- The AI request is sent through `puter.ai.chat(...)` and is prompted to return JSON feedback.

## Technologies

- **React** for the user interface.
- **React Router v7** for page navigation.
- **TypeScript** for static typing.
- **Tailwind CSS** for styling.
- **Vite** for development and bundling.
- **Zustand** for app state management.
- **Puter.js** for backend-free auth, storage, and AI services.

## Architecture

- `app/root.tsx` initializes the Puter integration and app layout.
- `app/routes/upload.tsx` handles resume upload, job details, and AI analysis.
- `app/routes/home.tsx` displays saved resumes.
- `app/routes/resume.tsx` shows AI feedback for a selected resume.
- `app/lib/puter.ts` wraps Puter APIs inside a Zustand store.
- `constants/index.ts` builds the AI prompt and response schema.

## Purpose

The app is designed to help users get AI-powered resume feedback quickly without needing a custom backend. It combines file storage, authentication, and AI analysis entirely in the browser.

## Run locally

```bash
npm install
npm run dev
```

Open `http://localhost:5173` in your browser.
