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
    background-color: #f5f5f5;
}

.quiz {
    background: white;
    padding: 20px;
    border-radius: 10px;
}

button {
    margin-top: 20px;
    padding: 10px 20px;
    cursor: pointer;
}

#ergebnis {
    margin-top: 20px;
    font-size: 20px;
    font-weight: bold;
}
</style>
</head>

<body>

<div class="quiz">
    <h1>🤖 KI-Quiz</h1>

    <p>1. Wofür steht KI?</p>
    <label><input type="radio" name="q1" value="1"> Künstliche Intelligenz</label><br>
    <label><input type="radio" name="q1" value="0"> Kreative Information</label><br><br>

    <p>2. Kann KI Bilder erstellen?</p>
    <label><input type="radio" name="q2" value="1"> Ja</label><br>
    <label><input type="radio" name="q2" value="0"> Nein</label><br><br>

    <p>3. Lernt KI aus Daten?</p>
    <label><input type="radio" name="q3" value="1"> Ja</label><br>
    <label><input type="radio" name="q3" value="0"> Nein</label><br><br>

    <p>4. Ist ChatGPT eine KI?</p>
    <label><input type="radio" name="q4" value="1"> Ja</label><br>
    <label><input type="radio" name="q4" value="0"> Nein</label><br><br>

    <p>5. Ist KI immer fehlerfrei?</p>
    <label><input type="radio" name="q5" value="0"> Ja</label><br>
    <label><input type="radio" name="q5" value="1"> Nein</label><br><br>

    <button onclick="auswerten()">Auswerten</button>

    <div id="ergebnis"></div>
</div>

<script>
function auswerten() {
    var punkte = 0;

    for (var i = 1; i <= 5; i++) {
        var antwort = document.querySelector('input[name="q' + i + '"]:checked');

        if (antwort) {
            punkte += Number(antwort.value);
        }
    }

    document.getElementById("ergebnis").innerHTML =
        "Du hast " + punkte + " von 5 Punkten erreicht!";
}
</script>

</body>
</html>
