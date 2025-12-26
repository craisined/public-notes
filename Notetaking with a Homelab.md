#Coding #Homelab

# My First Notetaking Solution
I started heavily focusing on notetaking during the Second Brain productivity trend. At this time, I was spending a good bit of time looking into different types maths and many different fun problems, so I wanted to store + document them and share them with friends (which would eventually become these notes!). Additionally, I wanted a system to store any documents/notes I had on paper for school to consolidate all my resources into a single app.

## Notion
Of course, the first app I was drawn to was Notion. I was introduced by a friend, and spent a lot of time creating Notion pages to store data and manage time. Some noteworthy ways I used notion were:
- Database + Notion Pages to publish this set of notes
- Database + Zapier for documents

## Drawbacks
While Notion worked great, it had a few drawbacks. The most critical ones to me were:
- Lack of control over my notes
    - Lack of a portable format
- Hard to integrate with scanning documents (still in progress for my current setup)
- Did everything, but nothing well
- Spent more time on config than actually using the system

# Self-Hosting Notes
As I got into self-hosting, I started to wonder if I could improve my notetaking system by switching out Notion for something I controlled. This led me to start to look as markdown as a way to self host notes, trying to meet the following requirements:
- Control over notes and documents
- Clean interface for writing technical and regular notes
    - LaTeX support
- Extensible and tinkerable
    - Document scanning support
- Multi Device Support
    - Web + mobile

## Failed Attempt 1
My first attempt at self hosting notes frankly created a bloated system of jank and pain:
- Notes hosted primarily on a hard drive connected to a Mini PC
- Obsidian + syncthing for notes (inconsistent sync)
- Obsidian in a container for anywhere else (painfully slow for a md editor)
- N8N for getting documents from Google Drive (slow, broke a lot, wasn't very useful)
The notetaking system just wasn't very consistent or convenient, making it a hassle to use

## Failed Attempt 1.5 - Nextcloud Notes
I tried switching out to Nextcloud Notes for a while, but the lack of LaTeX and lack of polish on it made it difficult to use for much of anything.

## Failed Attempt 2 - Silverbullet
Silverbullet was a similar story - it looked REALLY promising, but was just hard to work with on mobile and did not feel polished (part of me still wants to love it, but I don't think I'm geeky enough for Silverbullet yet). Additionally, LaTeX was supported through an extension but was just weird.

# My Current Setup
I still really enjoyed the idea of markdown, especially for technical writing. Obsidian's mobile interface stuck to me as one of the better markdown editors, so I decided to try to find a better setup involving obsidian for Desktop.
The solution came in the form of syncing to git through Obsidian's community plugin. This allowed consistent sync in a manner I understood + easy access on all devices. Additionally, for web access, I could use a self hosted instance of VS Code to edit markdown files anywhere I want.
Lastly, I found out I could publish my notes using Quartz, and created my own container for it!
Here is the full setup:
- Obsidian app + Git plugin on mobile
- Obsidian app on my laptop
- Code Server for web access (self hosted VS Code)
- Sync through self hosted gitea instance (GitHub works fine too, I just already use a self hosted git)
- Publishing through Quartz

## WIP
I still have not found a good way to scan docs and add them into a MD system. Currently working on building a better way to scan and handle my documents, while messing around with some OpenCV.