# 📂 ChatGPT and Claude Chat Capture Bookmarklets

## Background

I do a lot of ideating and brainstorming using ChatGPT and Claude (not to mention debugging), but **while ChatGPT and Claude are both great for knocking ideas around, they're less great when it comes to capturing and returning to ideas later**. Sure, there's a searchbar, but if you're anything like me, you've got multiple chat threads open meandering across different topics over time = a nightmare to search by keyword. Then, even if you find what you're looking for, it's still just sitting there in your browser. You can copy and paste text chunks, but who has time for that? 

I Googled around a little and found some browser extensions and the like that capture LLM text, but didn't love the idea of installing a new tool made by dog-knows-who or sending my chat data to (another) (more unknown) place.

So. I needed **a tool to capture ChatGPT and Claude conversations, including both user and LLM content, that**:

- Does not require third-party access or extensions, 
- Does not require me to click away into another tool (thus interrupting my flow), and
- Exports content cleanly, in a human-readable format that is portable and widely compatible. 
- I also decided that I wanted datestamps to be captured automatically in the filenames, both for uniqueness but also as an easy metadata hook.

After a bit more research, I decided to create a JavaScript bookmarklet to help me with this - bookmarklets are lightweight, native across browsers, and easy to save right there in the bookmarks bar, plus I'd have the confidence of knowing I created it myself and it's therefore doing only exactly what I want it to do.

## Implementation

I was already working in ChatGPT and Claude to help me plan/begin sketching out the bookmarklet. I've been playing around with getting my LLM of choice to summarize everything in a kind of templatized format once I'm done with a project, and so I did here. 

(*Note: The below process is what I did for ChatGPT specifically, but the Claude bookmarklet does pretty much exactly the same thing; it just works a little differently in terms of what the bookmarklet selects/captures from the DOM.*)

Take it away, Chat:
 
###  ✅ Project Outcomes

- Full, clean exports of ChatGPT conversations in Markdown, including both user and assistant content.
- Seamless integration with Obsidian for personal AI learning documentation and knowledge capture.
- Reliable, reusable browser tool requiring no third-party access or extensions.
- Demonstrated skill in scripting for automation and applied DOM manipulation.
- Established a personal system for archiving, reviewing, and learning from AI interactions.

### 🛠️ Technologies and Tools Used

- **JavaScript**: Used to build the bookmarklet for extracting and formatting content from the DOM.
- **Markdown**: Target format for clean, portable exports that support future use in tools like Obsidian.
- **Blob API**: Enabled on-the-fly file creation and automatic downloading in the browser.
- **Browser Developer Tools**: Used for step-by-step debugging and validating script behavior before converting to a bookmarklet.

---

### 🔧 Project Implementation

- **Script Prototyping in Console**: Verified message extraction and file generation worked correctly in the console before creating a bookmarklet.
- **DOM Element Selection**: Identified and targeted elements representing user queries and assistant responses within ChatGPT’s dynamic interface.
- **Bookmarklet Creation**: Converted the working JavaScript into a compact, single-line bookmarklet compatible with modern browsers.
- **Filename Versioning**: Added date and timestamp formatting to prevent file overwrites and improve organization.

---

### 🧩 Challenges Defeated

- Identified and corrected faulty DOM selectors that caused missing user inputs in the output.
- Debugged silent errors caused by browser restrictions on multiline or malformed bookmarklets.
- Implemented a workaround for browser filename conflicts by adding timestamp-based uniqueness.
- Rebuilt the bookmarklet multiple times for resilience across browser restarts and system reboots.

## Demo
I was so happy with how it came out, I even made a sparkly little demo in Canva to illustrate capturing a chat about the Roman Empire and converting it to Markdown with one click. 

**Behold**!:

<video controls src="../ChatGPTtoMD-demo.mp4" title="Title"></video>
<source src="../ChatGPTtoMD-demo.mp4" type="video/mp4">
## What next?
As I mentioned at the top of this post, the overall goal of this exercise is to be able to capture *and return to ideas later*. This bookmarklet is just the first step of that process. I next want to create a centralized knowledge base which includes both chat logs as well as other manual notes and documentation (maybe saved bookmarks, for example?) that would be the back end for a RAG pipeline feeding a local LLM. The ultimate goal of that project being to create a completely localized personal chatbot and knowledge base.

More to come there, hopefully soon!

---

