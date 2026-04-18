# Antigravity Chat History Recovery Guide

This guide helps you recover **missing or invisible chat history** in Antigravity.

> ⚠️ Important: Your chats are usually **NOT deleted**. The app just loses the **index (map)** and cannot display them.

---

## 📁 Important File Locations (Mac)

* **Actual Chat Data (SAFE HERE):**

  ```
  ~/.gemini/antigravity/conversations/
  ```

  These `.pb` files contain your real chats.

* **Index File (CAUSE OF ISSUE):**

  ```
  ~/Library/Application Support/Antigravity/User/globalStorage/state.vscdb
  ```

  If this breaks → chats disappear from UI.

---

## ✅ Step 0: Verify Your Data (MOST IMPORTANT)

Run this command in Terminal:

```bash
ls ~/.gemini/antigravity/conversations/
```

✔ If you see `.pb` files → **Your data is SAFE**

---

## 🛠️ Method 1: Workspace Re-Sync (Recommended First)

### Why it works:

Reconnects chats to your project folder.

### Steps:

1. Open Antigravity
2. Go to **Agent Manager (sidebar)**
3. Click **+ Open Workspace**
4. Select your project folder (e.g., AuctionX)
5. Wait **30–60 seconds**

✔ Chats should reappear

---

## 🛠️ Method 2: Index Reset (Most Powerful Fix)

### Why it works:

Deletes corrupted index → forces rebuild

### Steps:

1. Quit Antigravity completely:

   ```
   Cmd + Q
   ```

2. Run this command in Terminal:

```bash
rm ~/Library/Application\ Support/Antigravity/User/globalStorage/state.vscdb*
```

3. Restart Antigravity
4. Log in again

✔ App rebuilds chat index automatically

---

## 🛠️ Method 3: Reset Onboarding

### Why it works:

Forces app to reinitialize and rescan chats

### Steps:

1. Open Antigravity
2. Press:

   ```
   Cmd + Shift + P
   ```
3. Type:

   ```
   Antigravity: Reset onboarding
   ```
4. Press Enter
5. Login again

---

## 🛠️ Method 4: Drag & Drop Restore

### Why it works:

Manually re-imports chat file

### Steps:

1. Open Finder:

   ```
   Cmd + Shift + G
   ```
2. Paste:

   ```
   ~/.gemini/antigravity/conversations/
   ```
3. Open Antigravity → New Chat
4. Drag a `.pb` file into chat window
5. Click **Import / Restore**

---

## 🛠️ Method 5: Manual Extraction (Emergency)

### Why it works:

Directly reads your chat content

### Steps:

1. Open:

   ```
   ~/.gemini/antigravity/conversations/
   ```
2. Right-click any `.pb` file
3. Open with **VS Code / TextEdit**
4. Scroll down
5. Copy your code & prompts

✔ Works even if app is completely broken

---

## 🧠 Backup Command (VERY IMPORTANT)

Run this regularly:

```bash
cp -r ~/.gemini/antigravity/conversations/ ~/Desktop/Antigravity_Backup
```

✔ Saves all chats safely

---

## 💡 Pro Tips

* Always generate:

  ```
  "Session Handoff Summary"
  ```

  before logout

* Keep backups weekly

* Never rely only on UI

---

## 🧾 Final Truth

If `.pb` files exist →
👉 **Your data is NEVER lost**
👉 Only the UI is broken

---

## 👨‍💻 Author

Maintained by Vansh 🚀
For future-proof debugging and recovery
