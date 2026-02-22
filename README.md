<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Live Clock</title>
    <style>
        body {
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: #111;
            font-family: Arial, sans-serif;
        }

        #clock {
            font-size: 4rem;
            color: #00ffcc;
            background: #222;
            padding: 20px 40px;
            border-radius: 15px;
            box-shadow: 0 0 20px rgba(0, 255, 204, 0.5);
        }
    </style>
</head>
<body>

    <div id="clock">00:00:00</div>

    <script>
        function updateClock() {
            const now = new Date();
            let hours = now.getHours();
            let minutes = now.getMinutes();
            let seconds = now.getSeconds();

            // Add leading zeros
            hours = hours.toString().padStart(2, '0');
            minutes = minutes.toString().padStart(2, '0');
            seconds = seconds.toString().padStart(2, '0');

            document.getElementById('clock').textContent = 
                `${hours}:${minutes}:${seconds}`;
        }

        // Update immediately and then every second
        updateClock();
        setInterval(updateClock, 1000);
    </script>

</body>
</html>
