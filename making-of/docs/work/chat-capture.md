# 📂 ChatGPT and Claude Chat Capture Bookmarklets

## Background

I do a lot of ideating and brainstorming using ChatGPT and Claude, but **while ChatGPT and Claude are both great for knocking ideas around, they're less great when it comes to capturing and returning to ideas later**. Sure, there's a searchbar, but if you're anything like me, you've got multiple chat threads open meandering across different topics over time = a nightmare to search by keyword. Then, even if you find what you're looking for, it's still just sitting there in your browser. You can copy and paste text chunks, but who has time for that? 

I Googled around a little and found some browser extensions and the like that capture LLM text, but didn't love the idea of installing a new tool made by dog-knows-who or sending my chat data to (another) (more unknown) place.

After a bit more research, I decided to create a **JavaScript bookmarklet** to help me with this - bookmarklets are lightweight, native across browsers, and easy to use right there in the bookmarks bar, plus I'd have the confidence of knowing I created it myself and it's therefore doing only exactly what I want it to do.

To learn how to create one yourself, read on!

## Do it yourself
This tutorial shows you how to:

- Create a JavaScript bookmarklet that captures full ChatGPT conversations, including both user questions and LLM responses
- Formats the export in clean, human-readable Markdown for maximum portability, compatibility, and future-proofing
- Automatically generates a unique filename with timestamp (to avoid overwrites)

Use this bookmarklet for AI note-taking, project tracking, and much else, all from your browser where you're already working.

### Tools you'll need
- A web browser (I built mine in **Firefox**).
- Access to an LLM web app (I used **ChatGPT**).
- A Markdown-friendly note-taking app (I like **Obsidian**).

### Walkthrough
To create a bookmarklet to save LLM chats:

****Note**: The following instructions assume you are using Firefox to capture ChatGPT content*
#### 1. Open your bookmarks manager
- Select the **hamburger (three-lines) icon** in the top-right corner, then **Bookmarks** > **Manage Bookmarks...**, *or* press **Cmd + Option + B** (Mac) / **Ctrl + Shift + O** (Windows). 
	- The **Manage Bookmarks** pane will open.
- From the sidebar, right-click **Bookmarks Toolbar**, then select **Add bookmark...**. 
	- The **Add Bookmark** pane will open.
#### 2. Add the bookmarklet code. 
- Fill out the fields to create the bookmarklet:
	- **Name:** Name the bookmarklet something like "**ChatGPT to MD**". This will be the name displayed in the bookmark bar.
	- **URL**: Paste this single-line JavaScript:
	
	```javascript
	javascript:(function(){let chats=document.querySelectorAll('[class*="group"]');if(chats.length===0){alert("No messages found! Try scrolling up.");return;}let markdownText=Array.from(chats).map(chat=>{let user=chat.querySelector('[class*="whitespace-pre-wrap"]');let bot=chat.querySelector('[class*="markdown"]');let userText=user?`**You:**\n${user.innerText.trim()}`:"";let botText=bot?`**ChatGPT:**\n${bot.innerText.trim()}`:"";return[userText,botText].filter(Boolean).join("\n\n");}).join("\n\n---\n\n");let now=new Date();let formattedTimestamp=now.toISOString().replace(/[:.]/g,"-").slice(0,19);let filename=`ChatGPT-${formattedTimestamp}.md`;let blob=new Blob([markdownText],{type:'text/markdown'});let a=document.createElement('a');a.href=URL.createObjectURL(blob);a.download=filename;document.body.appendChild(a);a.click();document.body.removeChild(a);})();
```

	- **Note:** Make sure the entire code is on **one line** with no breaks!

- Select **Save**, then close the **Bookmarks** pane. 
	- The new bookmarklet will appear in your Bookmarks toolbar. 
#### How to use it
- Open a conversation that you'd like to save in the ChatGPT web app.
- Click the **ChatGPT to MD** bookmarklet in your Bookmarks toolbar.
- A **.md** file containing your chat and marked with the current date and time will be saved in your default **Downloads** folder.
- Move the file into your Obsidian vault (or wherever you store notes), and you are done!
## Demo
I was so happy with how it came out, I even made a sparkly little demo in Canva to illustrate capturing a chat about the Roman Empire and converting it to Markdown with one click. 

**Behold**!:

<video controls src="../ChatGPTtoMD-demo.mp4" title="Title"></video>
<source src="../ChatGPTtoMD-demo.mp4" type="video/mp4">
## What next?
As I mentioned at the top of this post, the overall goal of this exercise is to be able to capture *and return to ideas later*. This bookmarklet is just the first step of that process. I next want to create a centralized knowledge base which includes both chat logs as well as other manual notes and documentation (maybe saved bookmarks, for example?) that would be the back end for a RAG pipeline feeding a local LLM. The ultimate goal of that project being to create a completely localized personal chatbot and knowledge base.

More to come there, hopefully soon!

---

