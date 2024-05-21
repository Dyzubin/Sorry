<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Page title</title>
    <style>
        :root {
            --color-env: #0077B2;
            --color-env2: pink;
            --color-flap: white;
            --color-bg: #c9e4f7;
            --color-heart: #D00000;
            --env-border-radius: 6px;
            --env-width: 280px;
            --env-height: 180px;
        }

        body {
            background-color: var(--color-bg);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
        }

        .envelope-wrapper {
            position: relative;
            width: var(--env-width);
            height: var(--env-height);
        }

        #envelope {
            position: relative;
            width: var(--env-width);
            height: var(--env-height);
            border-bottom-left-radius: var(--env-border-radius);
            border-bottom-right-radius: var(--env-border-radius);
            background-color: var(--color-env2);
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            transition: transform 0.5s;
        }

        .flap {
            position: absolute;
            top: 0%;
            left: 0;
            width: 0;
            height: 4;
            border-left: calc(var(--env-width) / 2) solid transparent;
            border-right: calc(var(--env-width) / 2) solid transparent;
            border-top: calc(var(--env-height) / 2) solid var(--color-flap);
            transform-origin: top;
            transition: transform 0.5s;
                    }

        .letter {
            position: absolute;
            top: 2%;
            left: 5%;
            width: 90%;
            height: 80%;
            background-color: #fff;
            border-radius: var(--env-border-radius);
            box-shadow: 0 2px 26px rgba(0, 0, 0, 0.12);
            transform: translateY(-50%);
            opacity: 0;
            transition: opacity 0.5s;
            padding: 10px;
            box-sizing: border-box;
        }

        .words {
            width: 100%;
            height: 20px;
            background-color: #EEEFF0;
            margin-bottom: 10px;
            border-radius: 4px;
        }

        #envelope.open .flap {
            transform: rotateX(180deg);
        }

        #envelope.open .letter {
            opacity: 1;
        }

        .reset {
            margin-top: 20px;
        }

        button {
            margin: 5px;
            padding: 10px 20px;
            border: none;
            background-color: var(--color-env);
            color: white;
            border-radius: var(--env-border-radius);
            cursor: pointer;
            transition: background-color 0.3s;
        }

        button:hover {
            background-color: var(--color-env2);
        }
    </style>
</head>
<body>
    <div class="envelope-wrapper">
        <div id="envelope" class="close">
            <div class="flap"></div>
            <div class="letter">
                <div class="words line1">to:maria</div>
                <div class="words line2">   hi love sorry na sorry sa puro</div>
                <div class="words line3">kasinungalingan ko sana mapatawad</div>
                <div class="words line4">mo ako pinapangako na hindi na mauulit. </div>
            </div>
        </div>
    </div>
    <div class="reset">
        <button id="open">Open</button>
        <button id="reset">Reset</button>
    </div>
    <script>
        document.addEventListener('DOMContentLoaded', function () {
            var envelope = document.getElementById('envelope');
            var btnOpen = document.getElementById('open');
            var btnReset = document.getElementById('reset');

            function openEnvelope() {
                envelope.classList.add('open');
                envelope.classList.remove('close');
            }

            function closeEnvelope() {
                envelope.classList.add('close');
                envelope.classList.remove('open');
            }

            envelope.addEventListener('click', openEnvelope);
            btnOpen.addEventListener('click', openEnvelope);
            btnReset.addEventListener('click', closeEnvelope);
        });
    </script>
</body>
</html>
