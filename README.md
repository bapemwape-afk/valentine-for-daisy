# valentine-for-daisy
A tiny website for someone important ❤️
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>💖 For Daisy 💖</title>

<style>
body {
  margin: 0;
  background: #ece5dd;
  font-family: Helvetica, Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

/* Phone frame */
.phone {
  width: 360px;
  height: 640px;
  background: #e5ddd5;
  border-radius: 30px;
  box-shadow: 0 15px 30px rgba(0,0,0,0.3);
  display: flex;
  flex-direction: column;
  overflow: hidden;
}

/* Header */
.header {
  background: #075e54;
  color: white;
  padding: 12px;
  display: flex;
  align-items: center;
  gap: 10px;
}

.avatar {
  width: 40px;
  height: 40px;
  background: #fff;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
  color: #075e54;
}

.name {
  font-weight: bold;
}

/* Chat area */
.chat {
  flex: 1;
  padding: 15px;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.bubble {
  max-width: 75%;
  padding: 12px;
  border-radius: 15px;
  font-size: 15px;
  line-height: 1.4;
}

.from-me {
  background: #dcf8c6;
  align-self: flex-end;
  border-bottom-right-radius: 5px;
}

/* Typing bubble */
.typing {
  background: #fff;
  align-self: flex-end;
  font-style: italic;
  color: #555;
}

/* Buttons */
.buttons {
  padding: 15px;
  display: flex;
  justify-content: space-around;
  background: #f0f0f0;
}

button {
  padding: 10px 18px;
  border-radius: 20px;
  border: none;
  font-size: 14px;
}

.yes {
  background: #25d366;
  color: white;
  cursor: pointer;
}

.no {
  background: #ccc;
  color: #777;
  cursor: not-allowed;
}

/* Hearts */
.heart {
  position: fixed;
  bottom: 0;
  font-size: 24px;
  animation: float 4s linear forwards;
}

@keyframes float {
  0% { transform: translateY(0); opacity: 1; }
  100% { transform: translateY(-600px); opacity: 0; }
}
</style>
</head>

<body>

<div class="phone">
  <div class="header">
    <div class="avatar">D</div>
    <div class="name">Daisy 💕</div>
  </div>

  <div class="chat" id="chat">
    <div class="bubble from-me">Hey Daisy 💖</div>
    <div class="bubble from-me">I’ve been wanting to ask you something special 🥰</div>
    <div class="bubble from-me">You make my days brighter just by being you 🌸</div>
    <div class="bubble from-me">So… would you be my Valentine? 💌🌹</div>
  </div>

  <div class="buttons">
    <button class="yes" onclick="yesClicked()">Yes of course 💖</button>
    <button class="no" disabled>No 🙈</button>
  </div>
</div>

<script>
function yesClicked() {
  const chat = document.getElementById("chat");

  // typing bubble
  const typing = document.createElement("div");
  typing.className = "bubble typing";
  typing.innerText = "typing...";
  chat.appendChild(typing);

  setTimeout(() => {
    typing.remove();

    const reply = document.createElement("div");
    reply.className = "bubble from-me";
    reply.innerHTML = "😭💖💖 YAY!!<br><br>You just made me so happy, Daisy 🌹🥰";
    chat.appendChild(reply);

    document.querySelector(".buttons").style.display = "none";
    startHearts();
  }, 1500);
}

function startHearts() {
  setInterval(() => {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerText = "💖";
    heart.style.left = Math.random() * 100 + "vw";
    document.body.appendChild(heart);

    setTimeout(() => heart.remove(), 4000);
  }, 300);
}
</script>

</body>
</html>
