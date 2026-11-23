# Qbank-Anki-Bridge
Chrome extension that links UWorld and AMBOSS questions to your AnKing Step 1 cards in Anki. See suspended/active cards, unsuspend, mark Again, and save underlined notes to the Extra field. Functions as a more efficient substitute to having to maintain a spreadsheet of incorrects. 

**TLDR: scroll down to see images and you'll understand the gist**

## About

QBank → Anki Bridge adds a small panel to UWorld and AMBOSS. For each question you're on, it shows the matching cards from your AnKing Step 1 deck. You can see whether each card is suspended or active, unsuspend it, mark it Again, or add a note to it, all without having to alt-tab into Anki.

**How to get the most out of it:** Think of it as a replacement for a QBank log of incorrect answers. When you miss a question, add a note in the panel and click **Append to Extra**. The note is saved in the card's Extra field with a "UWORLD:" or "AMBOSS:" label, and it's underlined. If you also use the Anki Format Shuffler add-on, underlined text changes color and stands out on the back of the card. The goal is to read your Extra sections more often.

**What to put in the note:** The best notes are the facts that would have gotten you the right answer. You can paste them straight from the UWorld or AMBOSS explanation into the note box. Bold, italic, and underline carry over, while colors and fonts are stripped. Pasting an image sometimes works (im working on it okay). Anki has to be open when you do this.

**Using the other buttons:**
- **Again:** If you already studied a card but still missed the question because of it, click **Again** so it comes back sooner. Again only works on cards that are due.
- **Unsuspend:** If a card is suspended and you haven't learned it, or you want to review it, click **Unsuspend**.

**Two modes:** Click the mode button in the panel header to switch.
- **Pre-dedicated** shows right away whether the linked cards are active or suspended, with a green or red bar. Green means every card is active, and red means at least one is suspended. It's useful during classes, when you're picking extra questions on a topic.

<img width="314" height="200" alt="image" src="https://github.com/user-attachments/assets/3428b66d-075a-47ea-8066-27f2a9938d62" /><img width="314" height="352" alt="image" src="https://github.com/user-attachments/assets/bac3338f-095d-4094-8989-0a02732b13f2" />

- **Dedicated** shows nothing about the cards until you answer the question. Knowing you've already done a card can give away the answer, since you could rule out choices you don't recognize.

<img width="314" height="352" alt="image" src="https://github.com/user-attachments/assets/4ee1148b-a9b0-402e-af56-d454f2c3b99e" /><img width="314" height="352" alt="image" src="https://github.com/user-attachments/assets/cbd0a091-7ca9-4ff9-bc87-75669274af14" />

The extension remembers your mode. You can also copy a note's ID to search for it in Anki, shrink the panel to a tiny tab at the bottom of the screen, and drag it to resize.

**What you need:** Google Chrome, Anki on your computer (open while you study), the AnKing Step 1 deck, and the free AnkiConnect add-on (Step 1 below).

## How to install

**Step 1: Install AnkiConnect.** AnkiConnect is a free Anki add-on that lets the extension talk to Anki. Open Anki, click **Tools** at the top, then **Add-ons**, then **Get Add-ons**. Paste in the code `2055492159` and click **OK**. Close Anki and open it again.

**Step 2: Download the extension from GitHub.**
- Go to this page's **Releases** section (on the right side of the page) and open the latest release.
- Under **Assets**, click `qbank-anki-bridge.zip` to download it.
- Don't click "Source code," because that one won't work.
- Unzip the file: right-click and choose **Extract All** on Windows, or double-click it on a Mac.
- Move the folder somewhere permanent, like Documents, and don't delete or move it later. Chrome reads the extension from that spot.

**Step 3: Add it to Chrome.** In Chrome, type `chrome://extensions` in the address bar and press Enter. Turn on **Developer mode** (top right), click **Load unpacked**, and choose the `qbank-anki-bridge` folder. On Windows, Chrome may show a pop-up about developer mode extensions. You can dismiss it.

**Step 4: Give the extension permission to talk to Anki.** On the `chrome://extensions` page, find **QBank → Anki Bridge** and copy the long ID of letters shown on its card. Your ID is different from everyone else's. In Anki, click **Tools**, then **Add-ons**, select **AnkiConnect**, and click **Config**. Find the `webCorsOriginList` section and add a line with `chrome-extension://` followed by your ID. Put a comma after the line above it, like this:

```
"webCorsOriginList": [
    "http://localhost",
    "chrome-extension://paste-your-id-here"
]
```

Click **OK**, then close and reopen Anki again.

**Step 5: Check that it works.** Click the puzzle-piece icon at the top right of Chrome and pin the extension. Click it, then click **Test AnkiConnect**. You should see "Connected." If you don't, make sure Anki is open, the ID is copied exactly, and you restarted Anki after saving.

**Step 6: Use it.** Keep Anki open while you study.
- **UWorld:** Open a test question, and the panel appears at the bottom-left on its own.
- **AMBOSS:** Click **Get Anki Cards** once on each question. The panel reads the code from that window and remembers it, so you only do this once per question.

**Updating later:** Download the new zip from the Releases page and unzip it. Copy its files into your existing `qbank-anki-bridge` folder and replace the old ones. Then go to `chrome://extensions` and click the circular reload arrow on the extension's card. Keeping the same folder means your ID stays the same, so you don't have to redo Step 4.
