[blog.html](https://github.com/user-attachments/files/25520216/blog.html)
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <title>Personal Computer - Kuba</title>
    <style>
        :root {
            --win-gray: #c0c0c0;
            --win-white: #ffffff;
            --win-dark: #808080;
            --win-blue: #000080;
        }

        body {
            background-color: #008080;
            font-family: "MS Sans Serif", Tahoma, sans-serif;
            display: flex;
            justify-content: center;
            padding-top: 50px;
        }

        .window {
            width: 550px;
            background: var(--win-gray);
            border: 2px solid;
            border-color: var(--win-white) #000 #000 var(--win-white);
            box-shadow: 1px 1px 0 1px var(--win-dark);
            padding: 3px;
        }

        .title-bar {
            background: var(--win-blue);
            color: white;
            padding: 3px 5px;
            display: flex;
            justify-content: space-between;
            font-weight: bold;
            font-size: 13px;
        }

        .tabs {
            display: flex;
            margin-top: 10px;
            padding-left: 5px;
        }

        .tab {
            padding: 5px 15px;
            background: var(--win-gray);
            border: 1px solid #000;
            border-bottom: none;
            border-radius: 5px 5px 0 0;
            margin-right: 2px;
            font-size: 12px;
            cursor: pointer;
            position: relative;
            top: 1px;
            border-color: var(--win-white) #000 transparent var(--win-white);
        }

        .tab.active {
            padding-bottom: 7px;
            top: 0px;
            z-index: 2;
            background: var(--win-gray);
            font-weight: bold;
        }

        .main-frame {
            background: var(--win-gray);
            border: 1px solid;
            border-color: var(--win-white) #000 #000 var(--win-white);
            margin: 0 5px 5px 5px;
            padding: 15px;
            min-height: 280px;
        }

        .inner-content {
            background: var(--win-white);
            border: 2px inset var(--win-gray);
            padding: 15px;
            height: 230px;
            overflow-y: auto;
        }

        /* Ukrywanie zakładek */
        .tab-page { display: none; }
        .tab-page.active { display: block; }

        .field { margin-bottom: 10px; }
        .label { font-weight: bold; width: 120px; display: inline-block; color: #000; }
        
        hr { border: 0; border-top: 1px solid var(--win-dark); border-bottom: 1px solid var(--win-white); margin: 15px 0; }

        button.win-btn {
            background: var(--win-gray);
            border: 2px solid;
            border-color: var(--win-white) #000 #000 var(--win-white);
            padding: 4px 20px;
            cursor: pointer;
            margin-left: 5px;
            font-family: inherit;
        }

        button.win-btn:active {
            border-color: #000 var(--win-white) var(--win-white) #000;
        }
    </style>
</head>
<body>

<div class="window">
    <div class="title-bar">
        <span>Właściwości: System Kubis_12</span>
        <span>[?] [X]</span>
    </div>

    <div class="tabs">
        <div class="tab active" onclick="openTab(event, 'o-mnie')">O mnie</div>
        <div class="tab" onclick="openTab(event, 'hobby')">Zainteresowania</div>
        <div class="tab" onclick="openTab(event, 'kontakt')">Kontakt</div>
    </div>

    <div class="main-frame">
        <div class="inner-content">
            
            <div id="o-mnie" class="tab-page active">
                <div class="field">
                    <span class="label">Nick:</span>
                    <span>Kuba / Kubis_12</span>
                </div>
                <div class="field">
                    <span class="label">Wiek:</span>
                    <span>20 lat</span>
                </div>
                <div class="field">
                    <span class="label">System:</span>
                    <span>Win 11 / Fedora Workstation 43</span>
                </div>
                <hr>
                <p>Siema. Nazywam się Kuba, pochodzę z Wielkopolski. Lubię memy polityczne i stary styl UI (Vista, 7, 98). Ta strona powstała w nocy z nudów, więc reszta jest w budowie!</p>
            </div>

            <div id="hobby" class="tab-page">
                <div class="field">
                    <span class="label">Główne:</span>
                    <span>Memy polityczne, IT, Retro computing</span>
                </div>
                <hr>
                <p>Moje hobby to:</p>
                <ul>
                    <li>Granie w GTA V</li>
                    <li>Dziewczyna mojego kolegi</li>
                    <li>Psucie sobie nerwów błędami i instalowaniem programów na Linuxie (przez terminal)</li>
                </ul>
                <p><i>Lubię muzykę. Moje ulubione zespoły i osoby ze sceny muzycznej to: Malik Montana, Kizo, Queen.</i></p>
            </div>

            <div id="kontakt" class="tab-page">
                <div class="field">
                    <span class="label">Instagram:</span>
                    <span>kk1402_2026</span>
                </div>
                <div class="field">
                    <span class="label">Discord:</span>
                    <span>Kubis_12</span>
                </div>
                <hr>
                <p>Znajdziesz mnie też na:</p>
                <p>Instagram / Discord</p>
                <p style="text-align: center; margin-top: 20px;">
                    <img src="https://web.archive.org/web/20090830033221im_/http://geocities.com/Heartland/Plains/1444/emailme.gif" alt="mail-me">
                </p>
            </div>

        </div>
        
        <div style="text-align: right; margin-top: 15px;">
            <button class="win-btn" onclick="alert('Ustawienia zapisane (w Twojej wyobraźni!)')">OK</button>
            <button class="win-btn" onclick="alert('Nie można zamknąć systemu Kuba!')">Anuluj</button>
        </div>
    </div>
</div>

<script>
    function openTab(evt, tabName) {
        // 1. Ukryj wszystkie strony
        const tabPages = document.getElementsByClassName('tab-page');
        for (let i = 0; i < tabPages.length; i++) {
            tabPages[i].style.display = "none";
        }

        // 2. Usuń klasę active ze wszystkich przycisków
        const tabs = document.getElementsByClassName('tab');
        for (let i = 0; i < tabs.length; i++) {
            tabs[i].className = tabs[i].className.replace(" active", "");
        }

        // 3. Pokaż wybraną stronę i dodaj klasę active do klikniętej zakładki
        document.getElementById(tabName).style.display = "block";
        evt.currentTarget.className += " active";
    }
</script>

</body>
</html>
