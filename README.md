<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Der große Preis - Tierquiz</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        .quiz-container {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            width: 60%;
            margin: auto;
        }
        .category {
            font-weight: bold;
            margin-bottom: 10px;
        }
        .question {
            background-color: lightblue;
            padding: 20px;
            cursor: pointer;
            border-radius: 10px;
        }
    </style>
</head>
<body>
    <h1>Der große Preis - Tierquiz</h1>
    <h2>Punkte: <span id="score">0</span></h2>
    <div class="quiz-container">
        <div class="category">Luft</div>
        <div class="category">Land</div>
        <div class="category">Meer</div>
        
        <div class="question" onclick="askQuestion('luft', 100)">100</div>
        <div class="question" onclick="askQuestion('land', 100)">100</div>
        <div class="question" onclick="askQuestion('meer', 100)">100</div>
        
        <div class="question" onclick="askQuestion('luft', 200)">200</div>
        <div class="question" onclick="askQuestion('land', 200)">200</div>
        <div class="question" onclick="askQuestion('meer', 200)">200</div>
    </div>
    
    <script>
        let score = 0;
        const questions = {
            luft: {
                100: {q: "Welcher Vogel kann rückwärts fliegen?", a: "Kolibri"},
                200: {q: "Welcher Vogel hat die größte Flügelspannweite?", a: "Albatros"}
            },
            land: {
                100: {q: "Welches Tier ist das größte Landsäugetier?", a: "Elefant"},
                200: {q: "Welches Tier hat die längste Zunge?", a: "Ameisenbär"}
            },
            meer: {
                100: {q: "Welches ist das größte Tier im Meer?", a: "Blauwal"},
                200: {q: "Welcher Fisch kann Elektrizität erzeugen?", a: "Zitteraal"}
            }
        };
        
        function askQuestion(category, points) {
            let answer = prompt(questions[category][points].q);
            if (answer && answer.toLowerCase() === questions[category][points].a.toLowerCase()) {
                score += points;
                alert("Richtig! Du erhältst " + points + " Punkte.");
            } else {
                alert("Falsch! Die richtige Antwort war: " + questions[category][points].a);
            }
            document.getElementById("score").innerText = score;
        }
    </script>
</body>
</html>
