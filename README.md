# Open.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valentine's Day Invitation</title>
    <style>
        body {
            margin: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #fff;
        }

        .container {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .buttons {
            display: flex;
            align-items: center;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 20px;
        }

        button {
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            color: white;
            font-weight: bold;
            transition: all 0.2s ease-in-out;
        }

        #yesBtn {
            background-color: green;
            font-size: 16px;
        }

        #noBtn {
            background-color: red;
            font-size: 16px;
        }

        .success-text {
            font-size: 48px;
            color: pink;
            font-weight: bold;
            margin-top: 20px;
        }

        img {
            max-width: 300px;
        }
    </style>
</head>
<body>

    <div id="app" class="container">
        <img id="displayImg" src="https://media.tenor.com/VIChDQ6ejRQAAAAj/jumping-bear-hearts-no-png.gif" alt="Cute bear">
        <h1 id="question">Will you be my Valentine? 💘</h1>
        <div id="buttonContainer" class="buttons">
            <button id="yesBtn" onclick="handleYes()">Yes</button>
            <button id="noBtn" onclick="handleNo()">No</button>
        </div>
    </div>

    <script>
        let noClicks = 0;
        const NO_PHRASES = [
            "No 💔",
            "Pretty please? 🥺",
            "But we'd be so cute together! 💕",
            "One more chance, pookie?",
            "Don't break my heart :(",
            "What about a maybe?",
            "Please don't do this to me, I'm fragile",
        ];

        function handleNo() {
            noClicks++;
            const yesBtn = document.getElementById('yesBtn');
            const noBtn = document.getElementById('noBtn');
            
            // Calculate new font size for Yes button
            const newSize = (noClicks * 20) + 16;
            yesBtn.style.fontSize = `${newSize}px`;

            // Update No button text
            const phraseIndex = Math.min(noClicks - 1, NO_PHRASES.length - 1);
            noBtn.innerText = NO_PHRASES[phraseIndex];
        }

        function handleYes() {
            const app = document.getElementById('app');
            const secondImg = "https://media.tenor.com/f1xnRxTRxLAAAAAj/bears-with-kisses-bg.gif";
            
            app.innerHTML = `
                <img src="${secondImg}" alt="Bears kissing">
                <div class="success-text">Yay!!! 💖🎉</div>
            `;
        }
    </script>
</body>
</html>
