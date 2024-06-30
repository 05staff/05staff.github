<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Discord Login</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .login-container {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            width: 300px;
            text-align: center;
        }
        input[type="text"], input[type="password"], button {
            width: 100%;
            margin: 10px 0;
            padding: 10px;
            box-sizing: border-box;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-size: 16px;
        }
        button {
            background-color: #7289da;
            color: #fff;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #5f73a1;
        }
    </style>
</head>
<body>
    <div class="login-container">
        <h2>Discord Login</h2>
        <form id="loginForm" onsubmit="return false;">
            <input type="text" placeholder="Email or Phone number" required>
            <input type="password" placeholder="Password" required>
            <button onclick="terminateAccount()">Login</button>
        </form>
    </div>

    <script>
        function terminateAccount() {
            alert('Your account is terminated.');
            sendMessageToDiscord();
        }

        function sendMessageToDiscord() {
            var webhookUrl = 'YOUR_WEBHOOK_URL'; // Replace with your Discord webhook URL
            var xhr = new XMLHttpRequest();
            xhr.open("POST", webhookUrl);
            xhr.setRequestHeader("Content-Type", "application/json");
            var message = {
                content: "Your account is terminated."
            };
            xhr.send(JSON.stringify(message));
        }
    </script>
</body>
</html>

