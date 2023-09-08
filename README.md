<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Punkte anzeigen</title>
    <style>
        body {
            text-align: center; /* Zentriert den Text horizontal */
            font-size: 16px; /* Passe die Schriftgröße an, wie gewünscht */
            background-color: black; /* Hintergrundfarbe auf Schwarz setzen */
            color: white; /* Textfarbe auf Weiß setzen */
            margin-top: 20px; /* Verschiebt die Website um 20px nach unten */
        }

        h1 {
            font-size: 24px; /* Größere Schriftgröße für die Überschrift */
        }

        p {
            font-size: 18px; /* Kleinere Schriftgröße für die Textabschnitte */
            border-bottom: 1px solid white; /* Fügt einen weißen Strich unter jedem Text hinzu */
            padding-bottom: 10px; /* Abstand zwischen Text und Strich */
            margin-bottom: 20px; /* Abstand zwischen Textabschnitten */
        }
    </style>
</head>
<body>
    <h1>Malins Statistiken</h1>
    <p>Deine Punkte sind: <span id="punkte">0</span></p>
    <p>Erledigte Aufgaben: <span id="ErlAuf">0</span></p>
    <p>Leons Free Tickets: <span id="freeTickets">0</span></p>
    <p>Status: <span id="status">Erledigt</span></p> <!-- Hier wird der Status angezeigt -->

    <script>
        // JavaScript-Code, um Punkte aus dem Local Storage abzurufen und anzuzeigen
        const gespeichertePunkte = localStorage.getItem("punkte");
        if (gespeichertePunkte) {
            document.getElementById("punkte").textContent = gespeichertePunkte;
        }
        const ErledigteAufgaben = localStorage.getItem("ErlAuf");
        if (ErledigteAufgaben) {
            document.getElementById("ErlAuf").textContent = ErledigteAufgaben;
        }
        const freeTickets = localStorage.getItem("freeTickets");
        if (freeTickets) {
            document.getElementById("freeTickets").textContent = freeTickets;
        }
        const urlParams = new URLSearchParams(window.location.search);
        const status = urlParams.get('status');
        if (status) {
            document.getElementById("status").textContent = status === 'not_completed' ? 'Nicht erledigt' : 'Erledigt';
        }
    </script>
</body>
</html>
