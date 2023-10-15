# First-antivirus

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Antivirus</title>
    <style>
        body {
            background-color: #000;
            color: #fff;
            font-family: Arial, sans-serif;
        }

        header {
            background-color: #333;
            padding: 10px;
            text-align: center;
        }

        h1 {
            margin: 0;
            font-size: 24px;
        }

        .container {
            padding: 20px;
        }

        #progressBar {
            width: 100%;
            height: 20px;
            background-color: #444;
        }

        #progress {
            width: 0%;
            height: 100%;
            background-color: #0f0;
        }
    </style>
</head>
<body>
    <header>
        <h1>Antivirus</h1>
    </header>
    <div class="container">
        <h2>Scannez votre ordinateur</h2>
        <div id="progressBar">
            <div id="progress"></div>
        </div>
        <ul id="scanResults"></ul>
        <button id="scanButton">Scan</button>
        <button id="updateButton">Mise à jour</button>
    </div>

    <script>
        document.getElementById("scanButton").addEventListener("click", function() {
            // Simule une analyse pendant 5 secondes avec une mise à jour de la barre de progression
            const progressBar = document.getElementById("progress");
            let progress = 0;
            const interval = setInterval(function() {
                progress += 10;
                progressBar.style.width = progress + "%";
                if (progress >= 100) {
                    clearInterval(interval);
                    document.getElementById("scanResults").innerHTML = "<li>Aucun virus trouvé.</li>";
                }
            }, 500);
        });

        document.getElementById("updateButton").addEventListener("click", function() {
            // Simule une mise à jour de la base de données de signatures de virus
            alert("Mise à jour en cours...");
        });
    </script>
</body>
</html>
