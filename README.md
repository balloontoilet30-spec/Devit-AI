# Devit-AI
an Indian AI
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Devit AI</title>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
}

body {
    min-height: 100vh;
    background: linear-gradient(135deg, #0b1020, #151b35, #071827);
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
}

.app {
    width: 95%;
    max-width: 900px;
    height: 90vh;
    background: rgba(15, 20, 40, 0.92);
    border: 1px solid rgba(255,255,255,0.12);
    border-radius: 25px;
    overflow: hidden;
    box-shadow: 0 20px 60px rgba(0,0,0,0.5);
    display: flex;
    flex-direction: column;
}

.header {
    padding: 20px 25px;
    border-bottom: 1px solid rgba(255,255,255,0.1);
    display: flex;
    align-items: center;
    gap: 15px;
}

.logo {
    width: 50px;
    height: 50px;
    border-radius: 15px;
    background: linear-gradient(135deg, #00d4ff, #7c3cff);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 25px;
    font-weight: bold;
}

.header h1 {
    font-size: 25px;
}

.header p {
    color: #9ca3af;
    font-size: 13px;
    margin-top: 3px;
}

.chat {
    flex: 1;
    overflow-y: auto;
    padding: 25px;
}

.message {
    max-width: 75%;
    padding: 14px 17px;
    margin-bottom: 15px;
    border-radius: 18px;
    line-height: 1.5;
}

.bot {
    background: #202844;
    border-bottom-left-radius: 5px;
}

.user {
    background: linear-gradient(135deg, #2563eb, #6d28d9);
    margin-left: auto;
    border-bottom-right-radius: 5px;
}

.input-area {
    padding: 18px;
    border-top: 1px solid rgba(255,255,255,0.1);
    display: flex;
    gap: 10px;
}

input {
    flex: 1;
    padding: 15px;
    border: none;
    outline: none;
    border-radius: 15px;
    background: #202844;
    color: white;
    font-size: 15px;
}

button {
    border: none;
    cursor: pointer;
    padding: 0 22px;
    border-radius: 15px;
    background: linear-gradient(135deg, #00d4ff, #7c3cff);
    color: white;
    font-weight: bold;
}

button:hover {
    transform: scale(1.03);
}
</style>
</head>

<body>

<div class="app">

    <div class="header">
        <div class="logo">D</div>
        <div>
            <h1>Devit AI</h1>
            <p>Your AI assistant • Built by Devjeet & Ishit</p>
        </div>
    </div>

    <div class="chat" id="chat">

        <div class="message bot">
            👋 Hey! I'm <b>Devit AI</b>.<br>
            I'm the AI project created by Devjeet & Ishit.
            <br><br>
            Ask me something!
        </div>

    </div>

    <div class="input-area">
        <input
            id="userInput"
            type="text"
            placeholder="Ask Devit anything..."
            onkeydown="if(event.key==='Enter') sendMessage()"
        >

        <button onclick="sendMessage()">Send</button>
    </div>

</div>

<script>

function sendMessage() {

    const input = document.getElementById("userInput");
    const text = input.value.trim();

    if (text === "") return;

    addMessage(text, "user");

    input.value = "";

    setTimeout(() => {

        let reply = getReply(text.toLowerCase());

        addMessage(reply, "bot");

    }, 500);
}


function addMessage(text, type) {

    const chat = document.getElementById("chat");

    const message = document.createElement("div");

    message.className = "message " + type;

    message.innerHTML = text;

    chat.appendChild(message);

    chat.scrollTop = chat.scrollHeight;
}


function getReply(text) {

    if (text.includes("hello") || text.includes("hi")) {
        return "Hey! 👋 I'm Devit AI. How can I help?";
    }

    if (text.includes("who are you")) {
        return "I'm Devit AI 🤖 — a project created by Devjeet & Ishit.";
    }

    if (text.includes("your name")) {
        return "My name is Devit AI. ⚡";
    }

    if (text.includes("math")) {
        return "I can help with maths! ➗ Send me a question.";
    }

    if (text.includes("study")) {
        return "📚 Study mode activated! Tell me the subject or chapter.";
    }

    if (text.includes("thank")) {
        return "You're welcome! 😎";
    }

    return "I'm still learning! 🧠 This is Devit AI V1. Soon I'll have a real AI brain.";
}

</script>

</body>
</html>
