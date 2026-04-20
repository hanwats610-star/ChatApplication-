# 💬 Java Socket Chat Application

A simple real-time multi-client chat application built using **Java Sockets** and **Multithreading**. Multiple clients can connect to a server and exchange messages with each other in real time.

---

## 📁 Project Structure

```
ChatApp/
├── Server.java      # Server-side code (handles all clients)
└── Client.java      # Client-side code (connects to server)
```

---

## ⚙️ How It Works

- **Server** starts and listens on port `12346`
- **Clients** connect to the server using `localhost` and the same port
- Each client gets a **username** on joining
- Any message sent by a client is **broadcast to all other clients**
- Each client connection runs on its **own thread** so multiple users can chat simultaneously

```
[Client 1] ──┐
[Client 2] ──┼──► [SERVER] ──► broadcasts to everyone
[Client 3] ──┘
```

---

## 🛠️ Prerequisites

- Java JDK 8 or above
- IntelliJ IDEA (recommended) **or** any terminal

---

## ▶️ How to Run

### Option 1 — Using IntelliJ IDEA

**Step 1: Create Project**
1. Open IntelliJ IDEA
2. Click **New Project**
3. Select **Java**, set JDK, click **Create**

**Step 2: Add Files**
1. Right-click `src` → **New → Java Class** → Name it `Server`
2. Right-click `src` → **New → Java Class** → Name it `Client`
3. Paste the respective code into each file

**Step 3: Run Server**
1. Open `Server.java`
2. Click the green ▶️ button next to `main`

**Step 4: Allow Multiple Client Instances**
1. Go to **Run → Edit Configurations**
2. Click **+** → **Application**
3. Set Name: `Client`, Main class: `Client`
4. Click **Modify options** → Enable ✅ **Allow multiple instances**
5. Click **OK**

**Step 5: Run Multiple Clients**
- Run `Client` once → Enter username (e.g., `Rahul`)
- Run `Client` again → Enter username (e.g., `Priya`)
- Start chatting! 🎉

---

### Option 2 — Using Terminal / Command Prompt

**Compile both files:**
```bash
javac Server.java
javac Client.java
```

**Run Server (Terminal 1):**
```bash
java Server
```

**Run Client (Terminal 2):**
```bash
java Client
```

**Run another Client (Terminal 3):**
```bash
java Client
```

---

## 💬 Sample Output

```
---- Server Terminal ----
Server is running and waiting for connections...
User Rahul connected.
User Priya connected.
[Rahul]: Hello Priya!
[Priya]: Hi Rahul!

---- Client 1 (Rahul) ----
Connected to the chat server!
Enter your username: Rahul
Welcome to the chat, Rahul!
[Priya]: Hi Rahul!

---- Client 2 (Priya) ----
Connected to the chat server!
Enter your username: Priya
Welcome to the chat, Priya!
[Rahul]: Hello Priya!
```

---

## 🧵 Key Concepts Used

| Concept | Usage |
|---|---|
| `ServerSocket` | Server listens for incoming connections |
| `Socket` | Client connects to server |
| `BufferedReader` | Reads incoming messages |
| `PrintWriter` | Sends outgoing messages |
| `Thread` | Handles each client independently |
| `CopyOnWriteArrayList` | Thread-safe list of all connected clients |

---

## ⚠️ Common Errors & Fixes

| Error | Cause | Fix |
|---|---|---|
| `Connection refused` | Server not running | Start `Server.java` first |
| `Address already in use` | Port 12346 is busy | Restart server or change port number |
| `Cannot find symbol` | Missing import | Re-paste the full code |
| Only 1 client runs | Multiple instances disabled | Enable **Allow multiple instances** in Run Config |

---

## 🔧 Configuration

You can change these constants in the code:

| File | Constant | Default | Description |
|---|---|---|---|
| `Server.java` | `PORT` | `12346` | Port server listens on |
| `Client.java` | `SERVER_ADDRESS` | `localhost` | Server IP address |
| `Client.java` | `SERVER_PORT` | `12346` | Must match server PORT |

---

## 🚀 Possible Improvements

- Private messaging between two specific users
- GUI using Java Swing or JavaFX
- Chat history / message logging
- Online/offline status of users
- Multiple chat rooms support

---

## 📄 License

This project is free to use for learning and educational purposes.
