AI Code Generator SaaS

Generate clean HTML & CSS from natural language prompts using AI.

Built with n8n + Google Gemini API + lightweight frontend.

⸻

💡 Overview

AI Code Generator is a system that converts plain-English UI descriptions into usable HTML & CSS code.

Example prompt:

“A large rounded blue button that says Click Me and changes to a lighter blue on hover.”

➡️ Output: Ready-to-use HTML & CSS.

This project explores how AI can reduce frontend development friction by converting intent directly into code.

⸻

🏗️ Architecture

🔹 Frontend
	•	Single index.html (TailwindCSS + vanilla JS)
	•	Input field for natural language prompts
	•	Sends requests to n8n webhook
	•	Displays generated HTML/CSS output

🔹 Backend (n8n Workflow)
	1.	Webhook node → Receives prompt (?prompt=...)
	2.	HTTP Request node → Sends prompt to Gemini API
	3.	Respond to Webhook node → Returns generated code

🔹 AI
	•	Google Gemini (Generative Language API)

⸻

💡 Use Cases
	•	Rapid UI prototyping
	•	Generate frontend components instantly
	•	Speed up SaaS development
	•	Automate frontend workflows
	•	Learn HTML/CSS through AI-generated examples

⸻

🌐 Live Demo (Frontend only)

👉 https://.github.io/Vibe-Coding-Prototype/

⚠️ Note:
Frontend is live, but backend (n8n) runs locally.
Use local setup or ngrok for full functionality.

📸 Demo

Prompt Input
n8n Workflow
Output Result

📂 Files in this repo
	•	index.html → Frontend UI
	•	workflow.json → n8n workflow (API key removed)
	•	README.md → Documentation
	•	Screenshots → Demo visuals

▶️ How to Run Locally

1. Serve Frontend
python -m http.server 8000
# Open http://localhost:8000/index.html
2. Run n8n (Docker)
docker-compose up -d
# or
docker run -it --rm -p 5678:5678 n8nio/n8n
3. Import Workflow
	•	Open n8n
	•	Import workflow.json

4. Connect Backend

Set webhook URL in frontend:
http://localhost:5678/webhook/<your-webhook-id>
5. Run
	•	Enter prompt
	•	Click “Generate Code”

⸻

⚡ Temporary Live Demo (ngrok)

To expose backend publicly:
ngrok http 5678
Example:
https://abc123.ngrok.app/webhook/<your-webhook-id>

Paste this into frontend → works globally.

⚠️ Free ngrok URLs change every session.

⸻

🔍 Notes & Limitations
	•	Output may include extra wrappers (<iframe>, <html>, <body>)
	•	No post-processing currently
	•	Backend not deployed permanently

⸻

🛣️ Roadmap
	•	Deploy backend (Render / Railway)
	•	Clean HTML/CSS output automatically
	•	Add live preview inside UI
	•	Support JavaScript generation
	•	Save & share generated snippets
	•	Build reusable component library

👤 Author

Keerthi Raj
Building AI SaaS & Automation Tools

📧 keerthirajprofessional@gmail.com
:::
