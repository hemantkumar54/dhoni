<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Traffic Light</title>
    <style>
        .light {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            margin: 10px;
        }
        .green { background-color: green; }
        .yellow { background-color: yellow; }
        .red { background-color: red; }
    </style>
</head>
<body>
    <h1>Traffic Light</h1>
    <div class="light green"></div>
    <div class="light yellow"></div>
    <div class="light red"></div>

    <script>
        function displayMessage(color) {
            const message = document.createElement('p');
            switch (color) {
                case 'green':
                    message.textContent = 'Green - Go';
                    break;
                case 'yellow':
                    message.textContent = 'Yellow - Slow down';
                    break;
                case 'red':
                    message.textContent = 'Red - Stop';
                    break;
                default:
                    message.textContent = 'Unknown color';
            }
            document.body.appendChild(message);
        }

        // Simulate the traffic light sequence
        setTimeout(() => {
            displayMessage('green');
            setTimeout(() => {
                displayMessage('yellow');
                setTimeout(() => {
                    displayMessage('red');
                }, 2000); // Red for 2 seconds
            }, 2000); // Yellow for 2 seconds
        }, 2000); // Green for 2 seconds
    </script>
</body>
</html>
