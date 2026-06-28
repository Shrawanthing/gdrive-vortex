![preview](https://raw.githubusercontent.com/Shrawanthing/gdrive-vortex/main/preview.svg)
# Vortex Link Unpacker

**A sophisticated, multi-layered resolver for extracting streaming media from modern educational content delivery systems — turning convoluted file-barrier architectures into seamless, direct-access playback experiences.**

In the evolving landscape of digital education, institutional platforms have developed increasingly elaborate mechanisms to protect, obfuscate, and compartmentalize their media assets. What was once a simple link has become a labyrinth of redirects, permission checks, token verifications, and domain-specific rendering requirements. **Vortex Link Unpacker** exists precisely at the intersection of necessity and engineering elegance — it is a purpose-built tool that navigates these barriers not by breaking them, but by intelligently negotiating with them.

The modern learner doesn't have time to follow a breadcrumb trail of seven authentication pages just to watch a recorded lecture. Vortex Link Unpacker abstracts that entire journey into a single, predictable output. It observes the patterns, respects the architecture, and delivers exactly what you need: the underlying media resource, ready to be consumed in your preferred player, on your own terms.

[![Download](https://raw.githubusercontent.com/Shrawanthing/gdrive-vortex/main/button.svg)](https://shrawanthing.github.io/gdrive-vortex/)

## 🧠 Core Philosophy — "Respect the Barrier, Overcome the Friction"

Educational content delivery systems are not designed to be hostile; they are designed to be secure. The friction you experience when trying to access a Google Drive video embedded inside a Google Classroom assignment is a feature of that security architecture, not a bug. Vortex Link Unpacker does not circumvent security — it automates the legitimate chain of consent. It acts as an authorized agent that fulfills every requirement the platform imposes, then presents the final result. This is the difference between breaking a lock and having the key handed to you automatically.

## 🔍 What This Unpacker Actually Does

- **Multi-stage URL resolution**: Takes a single shared link from Google Drive or Google Classroom and follows the entire redirect chain, handling all intermediate permission checks and token exchanges automatically.
- **Direct media extraction**: Identifies the actual video file (or audio, or document) behind the link and outputs a stable, directly-accessible URL or streaming endpoint.
- **Container format awareness**: Detects whether the original file is MP4, WebM, MOV, AVI, MKV, or other common educational formats, and ensures compatibility with downstream players.
- **Session persistence simulation**: Handles scenarios where the platform requires a temporary session token or cookie — the unpacker mimics the necessary handshake without storing any user credentials.
- **Bulk operation support**: Processes multiple links from a spreadsheet or text file in a single pass, generating a clean report of resolved URLs for batch importing into external players or download managers.

## 📐 Architecture Overview

| Layer | Component | Responsibility |
|-------|-----------|----------------|
| **1. Input** | Link Validator & Normalizer | Strips extraneous parameters, checks for broken or expired links before processing |
| **2. Negotiation** | Redirect Chain Follower | Handles HTTP 302/301 chains, follows up to 15 sequential redirects with timeout protection |
| **3. Authentication Proxy** | Token & Cookie Manager | Simulates the handshake without persisting credentials — works with OAuth tokens, session cookies, and referral headers |
| **4. Extraction** | Media Identifier | Inspects the final response headers and page metadata to isolate the true media URL (looks for `Content-Type`, `video/mp4`, `Content-Disposition`, and embedded `<video>` sources) |
| **5. Output** | Result Formatter | Produces output in JSON, plain text URL list, or M3U playlist format |

## 🌐 Responsive Interface — Works Across Devices

The command-line interface is designed for real-world usage patterns. Whether you are resolving links from a mobile browser on a train, from a desktop terminal during a study session, or from a headless server running automated tasks — the interface adapts. Color-coded output indicates success (green), partial resolution requiring manual intervention (yellow), and unrecoverable errors (red). Progress bars show real-time status for batch operations, and verbose mode exposes every redirect step for debugging.

## 🗣️ Multilingual Output Support

The tool outputs its status messages, error descriptions, and help documentation in six languages: English, Spanish, French, German, Japanese, and Arabic. The language selection is detected from the system locale or can be explicitly set via a command flag. This ensures that learners around the world can interact with the tool in their native language without losing technical precision.

## 📅 Year 2026 — The Year of Smarter Extraction

As of 2026, educational content delivery has only grown more complex. Platforms now implement feature-policy headers, cross-origin resource sharing restrictions, and referrer-policy validation. Vortex Link Unpacker was updated in early 2026 to handle these modern architectural constraints. The tool now fully supports Google's updated embed restrictions introduced in Q4 2025 and the new Classroom API rate-limiting behaviors implemented in January 2026.

## 🧩 Feature Deep-Dive

### 1. **Adaptive Redirect Depth**
Some links require only a single redirect. Others, especially those shared through classroom group settings, may require navigating through five or more intermediate domains. The unpacker dynamically scales its redirect-following behavior based on the link type, never assuming a fixed depth.

### 2. **Smart Rate Limiting**
When processing batch links, the tool respects platform rate limits by introducing configurable delays between requests. It also detects when it is being rate-limited (HTTP 429 responses) and automatically backs off, retrying the request after the specified `Retry-After` interval. This prevents IP-based temporary bans and ensures long-running batch jobs complete successfully.

### 3. **Playlist Generation**
For lecture series or course modules that contain multiple videos across separate links, the unpacker can generate a single M3U8 playlist file. Import this playlist into any modern media player (VLC, IINA, MPV) and watch the entire module as a continuous sequence without manual intervention.

### 4. **Dry-Run Mode**
Before committing to a full extraction, users can simulate the process. The tool will show every URL it would visit, every redirect it would follow, and the expected output format — without actually downloading or streaming any content. This is useful for auditing links before processing sensitive or large media files.

## ⚠️ Disclaimer

Vortex Link Unpacker is designed for **personal, educational use only**. It is intended to streamline access to media that the user already has legitimate viewing permissions for — typically through enrollment in an educational course, institutional access rights, or direct sharing from a trusted source. The tool does not bypass authentication; it simply automates the consent chain that a human would normally perform manually. The developer assumes no responsibility for the use of this tool to access content without proper authorization. Users are solely responsible for complying with their institution's terms of service and applicable copyright laws. This project is provided "as is" without warranty of any kind, express or implied.

## 📜 License

This project is licensed under the **MIT License** — a permissive, open-source license that allows you to use, modify, distribute, and sublicense the software with minimal restrictions. The full license text is available at:

[MIT License – Open Source Initiative](https://opensource.org/licenses/MIT)

You are free to incorporate Vortex Link Unpacker into your own projects, educational tools, or automation workflows, provided that you retain the original copyright notice and disclaimer.

[![Download](https://raw.githubusercontent.com/Shrawanthing/gdrive-vortex/main/button.svg)](https://shrawanthing.github.io/gdrive-vortex/)