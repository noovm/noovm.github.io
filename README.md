# Noo VM – Interactive Cybersecurity Lab 
## [ [NooVM is a Live](https://noovm.github.io/) ] </br>


Noo VM is a browser‑based cybersecurity training lab that simulates hands‑on scenarios without requiring a virtual machine. Users select an OS, guidance mode, and topic, then walk through progressive stages with commands, hints, and feedback.

Noo VM is built using only free resources: a free Hugging Face API token, free GitHub Pages hosting, and free Cloudflare Workers for the backend.

## What It Does

- Generates interactive, step‑by‑step cybersecurity scenarios directly in the browser.
- Guides users through staged challenges with objectives, questions, and expected commands.
- Provides hints, explanations, and answer reveal options for learning support.
- Supports multiple topics (e.g., network recon, privilege escalation, web security, logs, permissions, and more).

## Who It Helps

- **Beginners** learning foundational cybersecurity workflows and command usage.
- **Students** needing structured, guided practice without a VM setup.
- **Instructors** looking for a lightweight, repeatable training interface.
- **Self‑learners** who want interactive practice with immediate feedback.

## How AI Is Used

- AI generates scenario content based on selected OS, topic, and guidance mode.
- Each scenario includes staged questions, expected commands, hints, and explanations.
- AI output is constrained to a strict JSON schema to keep the experience consistent.
- A short prompt instructs the model to produce linked, progressive stages and exact command answers.

## Add Your Hugging Face API Token

Noo VM uses Hugging Face to generate scenarios. Add your token in the app:

1. Create a free Hugging Face account.
2. Go to `https://huggingface.co/settings/tokens`
3. Click **New token**.
4. Click **Read**.
5. Click **Create Token**.
6. Copy the token (starts with `hf_`).
7. Open Noo VM, click **Settings**, paste the token, and click **Save Token**.

**Note:** The token is stored locally in your browser.


## Quick Start

1. Open the live site:
   ```
   https://noovm.github.io/
   ```
2. Click **Settings** to add your Hugging Face token.
3. Choose OS, Guidance Mode, and Topic.
4. Click **Start Machine**.

## Backend (Cloudflare Workers)

Noo VM uses Cloudflare Workers as a lightweight backend proxy for AI requests.

**How it works:**

1. The browser sends the scenario request (model + prompt) to the Worker endpoint.
2. The Worker forwards the request to Hugging Face Inference.
3. The Worker returns the model response to the browser.

This keeps the frontend simple, avoids a full server stack, and allows free hosting on GitHub Pages.

## Guidance Mode

- **Guided (extra hints)**: Shows extra hints and explanations after correct answers.
- **Challenge (minimal hints)**: Fewer hints for more realistic practice.

## Core Features

- Scenario generation without a VM.
- Progressive, linked stages.
- Exact‑answer command validation.
- Guided hints and explanations.
- Answer reveal after multiple incorrect attempts.
- Multiple cybersecurity topics.
- Built‑in progress stats (time, stage, commands).
- Responsive UI for desktop and mobile.
- Sidebar collapse for focused practice.

## Topics Included

- Network Penetration
- Privilege Escalation
- Web Security
- Post‑Exploitation
- Cryptography
- Log Analysis
- File Permissions
- Process & Service Recon
- User & Access Auditing
- Network Troubleshooting
- Web App Basics
- File Search & Discovery
- System Performance
- Windows Local Recon (Windows only)
- Active Directory Basics (Windows only)
- Wireless Recon (Advanced/Expert)

## Scenario Structure

Each scenario is generated as JSON and includes:

- Title and description
- OS, topic, and number of stages
- Background and target IP
- Staged questions and expected commands
- Hints and command explanations
- Optional metadata for learning outcomes

## How the UI Works

- The left panel controls OS, guidance mode, and topic.
- The main terminal shows stages, questions, and feedback.
- The top bar shows stage name, objective, and key context.
- Hints can be requested by typing `hint`.
- Answers can be revealed after multiple incorrect attempts by typing `answer`.

## Token Storage

- Tokens are stored in `localStorage` in your browser.
- They are not encrypted in this prototype.

## Performance Notes

- Large models can be slow (30–40s).


## Troubleshooting

- **Token error**: Open Settings and verify your HF token.
- **Invalid JSON**: Click Regenerate to retry.
- **Popup “Manage Passwords”**: Autofill is disabled, but some browsers may still suggest saved passwords.

## Upcoming Features

- Server‑side token handling
- Scenario caching
- Downloadable reports
- Export to PDF
- Custom templates per topic

## Contributing

Contributions are welcome. Suggested improvements:

- Add new topics and section lists
- Improve prompt quality
- Add more helpful hints
- Fix UI issues and accessibility

## Screenshots</div>

## Main UI
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/d52f4238-ed6e-4e2e-b05e-394b8a40f81e" />

## Adding API or Token in Setting
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/9765e2e7-109d-4f49-9673-e796168ab771" />

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/d3fdadf1-7384-4a0e-83ce-960336fbc570" />



## Credits

- Built with HTML, CSS, and JavaScript
- Powered by Hugging Face models
- And me

## FAQ

**Is a VM required?**  
No. Noo VM simulates training without a VM.

**Can I use my own model?**  
No, currently you can only use `openai-gpt-oss-120b`

**Why is it slow?**  
openai/gpt-oss-120b model take time to generate structured JSON.


