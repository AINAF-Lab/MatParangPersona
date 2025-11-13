<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My OpenAI Assistant Test</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 40px; }
    textarea { width: 100%; height: 80px; }
    button { margin-top: 10px; padding: 10px 20px; }
    #chat { margin-top: 20px; }
    .user { color: blue; margin: 5px 0; }
    .assistant { color: green; margin: 5px 0; }
  </style>
</head>
<body>
  <h1>Test Chat with My OpenAI Assistant</h1>
  <div id="chat"></div>
  <textarea id="message" placeholder="Type your message here..."></textarea>
  <button onclick="sendMessage()">Send</button>

  <script>
    const OPENAI_API_KEY = "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"; // ⚠️ Only for local test
    const ASSISTANT_ID = "asst_xIjDeMsmB3vFJ0mgny4L5Q0J";

    async function sendMessage() {
      const userMsg = document.getElementById("message").value;
      const chatDiv = document.getElementById("chat");
      chatDiv.innerHTML += `<div class='user'><b>You:</b> ${userMsg}</div>`;

      const res = await fetch("https://api.openai.com/v1/threads/runs", {
        method: "POST",
        headers: {
          "Authorization": `Bearer ${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}`,
          "Content-Type": "application/json"
        },
        body: JSON.stringify({
          assistant_id: ASSISTANT_ID,
          thread: {
            messages: [{ role: "user", content: userMsg }]
          }
        })
      });

      const data = await res.json();
      chatDiv.innerHTML += `<div class='assistant'><b>Assistant:</b> ${data.output_text || "..."}</div>`;
      document.getElementById("message").value = "";
    }
  </script>
</body>
</html>
