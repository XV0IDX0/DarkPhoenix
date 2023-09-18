# DarkPhoenix
<!DOCTYPE html>
<html>
<head>
    <title>Simple Chat App</title>
    <style>
        /* Basic styling for the chat interface */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }

        #chat-container {
            width: 300px;
            margin: 0 auto;
            border: 1px solid #ccc;
            padding: 10px;
            height: 400px;
            overflow-y: scroll;
        }

        #message-input {
            width: 100%;
            padding: 5px;
        }
    </style>
</head>
<body style="background-color:black;">
    <div id="chat-container">
        <div id="chat-messages"></div>
    </div>
    <input type="text" id="message-input" placeholder="Type a message...">
    <button id="send-button">Send</button>

    <script>
        const chatMessages = document.getElementById('chat-messages');
        const messageInput = document.getElementById('message-input');
        const sendButton = document.getElementById('send-button');

        sendButton.addEventListener('click', sendMessage);
        messageInput.addEventListener('keyup', (event) => {
            if (event.key === 'Enter') {
                sendMessage();
            }
        });

        function sendMessage() {
            const messageText = messageInput.value.trim();
            if (messageText !== '') {
                const messageElement = document.createElement('div');
                messageElement.innerText = messageText;
                chatMessages.appendChild(messageElement);
                messageInput.value = '';
                chatMessages.scrollTop = chatMessages.scrollHeight;
            }
        }
    </script>
</body>
</html>
