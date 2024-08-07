<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flor para Heather</title>
    <style>
        body {
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #f0f8ff;
            overflow: hidden;
            position: relative;
        }
        .flower {
            position: absolute;
            bottom: 0;
            width: 0;
            height: 0;
            background-color: red;
            border-radius: 50%;
            transition: width 1s ease, height 1s ease;
            text-align: center;
            color: white;
            font-size: 16px;
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 0;
        }
        .message {
            display: none;
            position: absolute;
            bottom: 10%;
            font-size: 24px;
            color: red;
        }
    </style>
</head>
<body>
    <div id="flower" class="flower"></div>
    <div id="message" class="message">Te amo Heather</div>
    <script>
        let clickCount = 0;

        document.body.addEventListener('click', () => {
            const flower = document.getElementById('flower');
            const message = document.getElementById('message');

            clickCount++;

            // Increase flower size
            flower.style.width = `${clickCount * 20}px`;
            flower.style.height = `${clickCount * 20}px`;

            // Make flower appear after the first click
            if (clickCount === 1) {
                flower.style.opacity = 1;
            }

            // Show message after the flower has fully grown
            if (clickCount === 10) {
                flower.style.transition = 'none';
                flower.style.width = '200px';
                flower.style.height = '200px';
                setTimeout(() => {
                    flower.style.transition = 'width 1s ease, height 1s ease';
                    flower.style.opacity = 0;
                    message.style.display = 'block';
                }, 1000);
            }
        });
    </script>
</body>
</html>
