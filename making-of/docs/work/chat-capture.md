# 📂 ChatGPT and Claude Chat Capture Bookmarklets

Created custom JavaScript bookmarklets to export full ChatGPT and Claude conversations (including both user input and assistant responses) as cleanly formatted Markdown files for integration with an Obsidian knowledge base.

---
## ✅ Project Outcomes

- Full, clean exports of ChatGPT conversations in Markdown, including both user and assistant content.
- Seamless integration with Obsidian for personal AI learning documentation and knowledge capture.
- Reliable, reusable browser tool requiring no third-party access or extensions.
- Demonstrated skill in scripting for automation and applied DOM manipulation.
- Established a personal system for archiving, reviewing, and learning from AI interactions.

## 🛠️ Technologies and Tools Used

- **JavaScript**: Used to build the bookmarklet for extracting and formatting content from the DOM.
- **Markdown**: Target format for clean, portable exports that support future use in tools like Obsidian.
- **Blob API**: Enabled on-the-fly file creation and automatic downloading in the browser.
- **Browser Developer Tools**: Used for step-by-step debugging and validating script behavior before converting to a bookmarklet.

---

## 🔧 Project Implementation

- **Script Prototyping in Console**: Verified message extraction and file generation worked correctly in the console before creating a bookmarklet.
- **DOM Element Selection**: Identified and targeted elements representing user queries and assistant responses within ChatGPT’s dynamic interface.
- **Bookmarklet Creation**: Converted the working JavaScript into a compact, single-line bookmarklet compatible with modern browsers.
- **Filename Versioning**: Added date and timestamp formatting to prevent file overwrites and improve organization.

---

## 🧩 Challenges Defeated

- Identified and corrected faulty DOM selectors that caused missing user inputs in the output.
- Debugged silent errors caused by browser restrictions on multiline or malformed bookmarklets.
- Implemented a workaround for browser filename conflicts by adding timestamp-based uniqueness.
- Rebuilt the bookmarklet multiple times for resilience across browser restarts and system reboots.
