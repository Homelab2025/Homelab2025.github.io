# Homelab2025.github.io

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Page Title</title>
    <style>
        body {
            background-color: #333; /* Dark grey background color */
            color: white; /* White text color */
            font-family: Arial, sans-serif; /* Choose your preferred font */
        }
        .timestamp {
            text-align: center;
            padding: 20px;
        }
        .ip-address {
            text-align: center;
            padding: 20px;
        }
    </style>
</head>
<body>
    <div class="timestamp">
        <h2>Timestamp: <span id="timestamp"></span></h2>
    </div>
    <div class="ip-address">
        <h2>IP Address: <span id="ip-address"></span></h2>
    </div>

    <script>
        // Function to get current timestamp
        function getCurrentTimestamp() {
            var now = new Date();
            var timestamp = now.toLocaleString();
            return timestamp;
        }
        // Function to get current IP address
        function getCurrentIPAddress() {
            var ipAddress = "";
            // Fetch IP address from a service like ipify.org
            fetch('https://api.ipify.org?format=json')
            .then(response => response.json())
            .then(data => {
                ipAddress = data.ip;
                document.getElementById('ip-address').innerText = ipAddress;
            })
            .catch(error => console.error('Error fetching IP address:', error));
        }
        // Update timestamp and IP address on page load
        window.onload = function() {
            document.getElementById('timestamp').innerText = getCurrentTimestamp();
            getCurrentIPAddress();
        };
    </script>
</body>
</html>
