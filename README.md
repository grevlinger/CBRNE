<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CBRNE Konkurranse</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
    </style>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <header>
        <h1>CBRNE Konkurranse</h1>
        <p>En spennende månedslang konkurranse for våre ansatte!</p>
    </header>

    <main>
        <!-- Oppgave 1 -->
        <section id="oppgave1">
            <h2>Oppgave 1</h2>
            <p>Beskrivelse av den første oppgaven...</p>
            <form onsubmit="return validateAnswer('answer_1', 'nytt_riktig_svar_1', 'oppgave2');" action="#" method="post">
                <label for="answer_1">Svar:</label>
                <input type="text" id="answer_1" name="answer_1" required value="">
                <input type="submit" value="Send inn svar">
            </form>
        </section>

        <!-- Oppgave 2 -->
        <section id="oppgave2" style="display: none;">
            <h2>Oppgave 2</h2>
            <p>Beskrivelse av den andre oppgaven...</p>
            <form onsubmit="return validateAnswer('answer_2', 'nytt_riktig_svar_2', 'oppgave3');" action="#" method="post">
                <label for="answer_2">Svar:</label>
                <input type="text" id="answer_2" name="answer_2" required value="">
                <input type="submit" value="Send inn svar">
            </form>
        </section>

        <!-- Fortsett mønsteret for de andre oppgavene -->
        <!-- Oppgave 3 -->
        <section id="oppgave3" style="display: none;">
            <h2>Oppgave 3</h2>
            <p>Beskrivelse av den tredje oppgaven...</p>
            <form onsubmit="return validateAnswer('answer_3', 'nytt_riktig_svar_3', 'oppgave4');" action="#" method="post">
                <label for="answer_3">Svar:</label>
                <input type="text" id="answer_3" name="answer_3" required value="">
                <input type="submit" value="Send inn svar">
            </form>
        </section>

        <!-- Fortsett mønsteret for Oppgave 4 til Oppgave 10 -->
        <!-- Husk å oppdatere 'nytt_riktig_svar_X' for hver oppgave -->

        <!-- Oppgave 4 -->
        <section id="oppgave4" style="display: none;">
            <h2>Oppgave 4</h2>
            <p>Beskrivelse av den fjerde oppgaven...</p>
            <form onsubmit="return validateAnswer('answer_4', 'nytt_riktig_svar_4', 'oppgave5');" action="#" method="post">
                <label for="answer_4">Svar:</label>
                <input type="text" id="answer_4" name="answer_4" required value="">
                <input type="submit" value="Send inn svar">
            </form>
        </section>

        <!-- Oppgave 5 -->
        <section id="oppgave5" style="display: none;">
            <h2>Oppgave 5</h2>
            <p>Beskrivelse av den femte oppgaven...</p>
            <form onsubmit="return validateAnswer('answer_5', 'nytt_riktig_svar_5', 'oppgave6');" action="#" method="post">
                <label for="answer_5">Svar:</label>
                <input type="text" id="answer_5" name="answer_5" required value="">
                <input type="submit" value="Send inn svar">
            </form>
        </section>

        <!-- Fortsett denne strukturen for Oppgave 6 til Oppgave 10 -->

    </main>

    <footer>
        <p>&copy; 2023 CBRNE Konkurranse</p>
    </footer>

    <script>
        // Funksjon for å hente lagrede svar fra lokale lagringsalternativer
        function loadAnswers() {
            for (let i = 1; i <= 10; i++) {
                const answer = localStorage.getItem('answer_' + i);
                if (answer !== null) {
                    document.getElementById('answer_' + i).value = answer;
                }
            }
        }

        // Kall funksjonen for å laste lagrede svar når siden lastes
        loadAnswers();

        function validateAnswer(answerId, correctAnswer, nextSectionId) {
            var userAnswer = document.getElementById(answerId).value.trim().toLowerCase();

            // Sammenlign med det forhåndsbestemte riktige svaret
            if (userAnswer === correctAnswer) {
                alert('Riktig svar! Du kan nå gå videre til neste oppgave.');
                document.getElementById(nextSectionId).style.display = 'block';

                // Lagre svaret lokalt for neste gang
                localStorage.setItem(answerId, userAnswer);

                // Skjul gjeldende oppgave
                document.getElementById('oppgave' + answerId.charAt(answerId.length-1)).style.display = 'none';

                return false; // Hindre formen fra å bli faktisk sendt
            } else {
                alert('Feil svar. Prøv igjen.');
                return false; // Hindre innsending
            }
        }
    </script>

</body>
</html>
