
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cookie Of Fortune</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #ffebee, #ffcdd2);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
            text-align: center;
        }

        h1 {
            color: #d32f2f;
            margin-bottom: 20px;
            font-size: 2rem;
        }

        /* Fortune Cookie / Button Styling */
        .cookie-container {
            cursor: pointer;
            transition: transform 0.2s ease;
        }

        .cookie-container:hover {
            transform: scale(1.05);
        }

        .cookie-container:active {
            transform: scale(0.95);
        }

        .cookie-icon {
            font-size: 80px;
            user-select: none;
        }

        /* Quote Display Box */
        .quote-box {
            margin-top: 30px;
            min-height: 80px;
            max-width: 80%;
            background: white;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.5s ease;
        }

        .quote-box.reveal {
            opacity: 1;
            transform: translateY(0);
        }

        #quote {
            color: #424242;
            font-size: 1.2rem;
            font-style: italic;
            font-weight: 500;
        }
    </style>
</head>
<body>

    <h1>🥠 crack of love 🥠</h1>

    <div class="cookie-container" onclick="generateQuote()">
        <div class="cookie-icon" id="cookie-emoji">🥠</div>
    </div>

    <div class="quote-box" id="quote-box">
        <p id="quote">Click the cookie to reveal your fortune...</p>
    </div>

    <script>
        // Array of love quotes
        const loveQuotes = [
            "\"Love is not about how many days, months, or years you have been together. Love is about how much you love each other every single day.\"",
            "\"In all the world, there is no heart for me like yours. In all the world, there is no love for you like mine.\" — Maya Angelou",
            "\"I swear I couldn't love you more than I do right now, and yet I know I will tomorrow.\" — Leo Christopher",
            "\"If I had a flower for every time I thought of you... I could walk through my garden forever.\" — Alfred Tennyson",
            "\"To love and be loved is to feel the sun from both sides.\" — David Viscott",
            "\"You are my today and all of my tomorrows.\" — Leo Christopher",
            "\"Loved you yesterday, love you still, always have, always will.\"",
            "\"I want you. All of you. Your flaws. Your mistakes. Your imperfections. I want you, and only you.\""
        ];

        function generateQuote() {
            const quoteBox = document.getElementById('quote-box');
            const quoteText = document.getElementById('quote');
            const cookieEmoji = document.getElementById('cookie-emoji');

            // Hide the box momentarily for an animation reset
            quoteBox.classList.remove('reveal');

            // Change emoji briefly to look 'opened'
            cookieEmoji.innerHTML = "💌";

            setTimeout(() => {
                // Pick a random quote
                const randomIndex = Math.floor(Math.random() * loveQuotes.length);
                quoteText.innerHTML = loveQuotes[randomIndex];
                
                // Show the quote box with animation
                quoteBox.classList.add('reveal');
            }, 300); 
        }
    </script>
</body>
</html>
