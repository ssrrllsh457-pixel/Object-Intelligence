# Object Intelligence — prototype v0.1

This is a responsive, installable web-app prototype for the Object Intelligence idea.

## What works now
- Arabic, German and English interface
- Select an image or open the phone camera
- Image preview and remove
- Optional context field
- Responsive mobile/desktop layout
- Basic offline caching when hosted over HTTPS

## Important limitation
The AI recognition engine is **not connected yet**. The Analyze button currently opens an honest setup notice; it does not pretend to identify the uploaded image. To add real recognition, connect a vision-capable AI service through a backend server. Never put a private API key in `app.js` or any browser code.

## Run it
You can open `index.html` for a quick preview. For camera/PWA features, host the folder on an HTTPS static host or run a local development server.

For example, if Python is installed:
```bash
python -m http.server 8000
```
Then open `http://localhost:8000` on the computer. On a phone, use an HTTPS deployment for camera access and installation.

## Next development step
Create a backend `/api/analyze` endpoint that:
1. Receives the uploaded image and optional context.
2. Sends it to a vision model using a server-side API key.
3. Requests structured output: object name, confidence, function, how it works, common materials, uncertainty, and safety notes.
4. Returns the result to the app.
5. Deletes temporary image data unless the user explicitly chooses to save it.

Do not rely on the app for safety-critical identification, electrical work, vehicle repairs, medical decisions, or hazardous machinery.
