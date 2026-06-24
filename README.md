# Ai-Quiz
Willkommen beim ultimativen KI-Quiz! 
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KI-Quiz</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 700px;
            margin: 40px auto;
            padding: 20px;
            background: #f4f4f4;
        }

        .quiz-container {
            background: white;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }

        h1 {
            text-align: center;
        }

        .question {
            margin-bottom: 20px;
        }

        button {
            background: #0078ff;
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }

        button:hover {
            background: #005fd1;
        }

        #result {
            margin-top: 20px;
            font-size: 20px;
            font-weight: bold;
            text-align: center;
        }
    </style>
</head>
<body>

<div class="quiz-container">
    <h1>🤖 KI-Quiz</h1>

    <div class="question">
        <p>1. Wofür steht KI?</p>
        <label><input type="radio" name="q1" value="1"> Künstliche Intelligenz</label><br>
        <label><input type="radio" name="q1" value="0"> Kreative Information</label><br>
        <label><input type="radio" name="q1" value="0"> Komplexe Integration</label>
    </div>

    <div class="question">
        <p>2. Welche KI beantwortet gerade deine Fragen?</p>
        <label><input type="radio" name="q2" value="1"> ChatGPT</label><br>
        <label><input type="radio" name="q2" value="0"> Photoshop</label><br>
        <label><input type="radio" name="q2" value="0"> Excel</label>
    </div>

    <div class="question">
        <p>3. Kann KI Bilder erstellen?</p>
        <label><input type="radio" name="q3" value="1"> Ja</label><br>
        <label><input type="radio" name="q3" value="0"> Nein</label>
    </div>

    <div class="question">
        <p>4. Lernt KI aus Daten?</p>
        <label><input type="radio" name="q4" value="1"> Ja</label><br>
        <label><input type="radio" name="q4" value="0"> Nein</label>
    </div>

    <div class="question">
        <p>5. Ist KI immer fehlerfrei?</p>
        <label><input type="radio" name="q5" value="0"> Ja</label><br>
        <label><input type="radio" name="q5" value="1"> Nein</label>
    </div>

    <button onclick="auswerten()">Quiz auswerten</button>

    <div id="result"></div>
</div>

<script>
function auswerten() {
    let punkte = 0;

    for (let i = 1; i <= 5; i++) {
        let antwort = document.querySelector(`input[name="q${i}"]:checked`);
        if (antwort) {
            punkte += parseInt(antwort.value);
        }
    }

    let text = `Du hast ${punkte} von 5 Punkten erreicht!`;

    if (punkte === 5) {
        text += " 🎉 Perfekt!";
    } else if (punkte >= 3) {
        text += " 👍 Gut gemacht!";
    } else {
        text += " 📚 Da geht noch mehr!";
    }

    document.getElementById("result").innerHTML = text;
}
</script>

</body>
</html>
