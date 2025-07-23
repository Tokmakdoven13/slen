<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Çiçek Efektli Arka Plan - Selen</title>
    
    <style>
        :root {
            /* Varsayılan Tema (Kırmızı/Sarı) */
            --theme-bg-color: #000000;
            --flower-center-yellow-light: #FFFF00;
            --flower-center-yellow-dark: #FFD700;
            --petal-primary-color: #FF0000;
            --petal-secondary-color: #CC0000;
            --stem-green-light: #81C784;
            --stem-green-dark: #388E3C;
            --message-bg: rgba(0, 0, 0, 0.85);
            --message-text: white;

            --mini-flower-yellow: #FFFF00;
            --mini-flower-pink: #FF0000;
            --mini-flower-green: #388E3C;

            --sparkle-color1: #FFD700;
            --sparkle-color2: #FFFFFF;
            --sparkle-color3: #FF4500;
            --sparkle-color4: #00BFFF;
        }

        /* Temalar */
        body[data-theme="blue"] {
            --theme-bg-color: #0d47a1;
            --flower-center-yellow-light: #ADD8E6;
            --flower-center-yellow-dark: #87CEEB;
            --petal-primary-color: #42A5F5;
            --petal-secondary-color: #2196F3;
            --stem-green-light: #66BB6A;
            --stem-green-dark: #4CAF50;
            --mini-flower-yellow: #B0E0E6;
            --mini-flower-pink: #87CEFA;
            --mini-flower-green: #A5D6A7;
            --sparkle-color1: #B0E0E6;
            --sparkle-color2: #FFFFFF;
            --sparkle-color3: #ADD8E6;
            --sparkle-color4: #42A5F5;
        }

        body[data-theme="purple"] {
            --theme-bg-color: #4a148c;
            --flower-center-yellow-light: #E1BEE7;
            --flower-center-yellow-dark: #CE93D8;
            --petal-primary-color: #BA68C8;
            --petal-secondary-color: #9C27B0;
            --stem-green-light: #7CB342;
            --stem-green-dark: #689F38;
            --mini-flower-yellow: #F3E5F5;
            --mini-flower-pink: #E0BBE4;
            --mini-flower-green: #C5E1A5;
            --sparkle-color1: #E1BEE7;
            --sparkle-color2: #FFFFFF;
            --sparkle-color3: #BA68C8;
            --sparkle-color4': '#9C27B0'
        }

        body[data-theme="green"] {
            --theme-bg-color: #1b5e20;
            --flower-center-yellow-light: #C8E6C9;
            --flower-center-yellow-dark: #A5D6A7;
            --petal-primary-color: #81C784;
            --petal-secondary-color: #4CAF50;
            --stem-green-light: #FFEB3B;
            --stem-green-dark: #FBC02D;
            --mini-flower-yellow: #F0F4C3;
            --mini-flower-pink: #C5E1A5;
            --mini-flower-green: #FFEB3B;
            --sparkle-color1: #C8E6C9;
            --sparkle-color2: '#FFFFFF;
            --sparkle-color3: '#81C784;
            --sparkle-color4': '#4CAF50'
        }

        body[data-theme="pink"] {
            --theme-bg-color: #880E4F;
            --flower-center-yellow-light: #F8BBD0;
            --flower-center-yellow-dark: #F48FB1;
            --petal-primary-color: #EC407A;
            --petal-secondary-color: #D81B60;
            --stem-green-light: #A5D6A7;
            --stem-green-dark: #66BB6A;
            --mini-flower-yellow: #FCE4EC;
            --mini-flower-pink: #F06292;
            --mini-flower-green: #81C784;
            --sparkle-color1: #F8BBD0;
            --sparkle-color2: #FFFFFF;
            --sparkle-color3: #EC407A;
            --sparkle-color4': '#FCE4EC'
        }

        /* Genel Stil Ayarları */
        body {
            margin: 0;
            background-color: var(--theme-bg-color);
            overflow: hidden;
            font-family: 'Arial', sans-serif;
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            cursor: default;
            transition: background-color 1s ease-out;
        }

        /* Ana İçerik Konteyneri */
        .flower-page {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            width: 100%;
            position: relative;
        }

        /* Çiçek Konteyneri */
        #flower-container {
            position: relative;
            width: 350px;
            height: 450px;
            z-index: 5;
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transform: scale(0.5);
            animation: fadeInScale 2s forwards ease-out;
            animation-delay: 1s;
            margin-top: -50px;
            transition: opacity 1s ease-out, transform 1s ease-out;
        }

        @keyframes fadeInScale {
            0% { opacity: 0; transform: scale(0.5); }
            100% { opacity: 1; transform: scale(1); }
        }

        /* Çiçek Merkezi */
        .flower__center {
            width: 25%;
            height: 25%;
            background: radial-gradient(circle, var(--flower-center-yellow-light), var(--flower-center-yellow-dark));
            border-radius: 50%;
            position: absolute;
            top: 30%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 3;
            box-shadow: 0 0 30px var(--flower-center-yellow-dark);
        }

        /* Çiçek Sapı */
        .flower__stem {
            width: 6%;
            height: 60%;
            background: linear-gradient(to top, var(--stem-green-dark), var(--stem-green-light));
            position: absolute;
            top: 40%;
            left: 50%;
            transform: translateX(-50%);
            z-index: 1;
            border-radius: 8px;
            box-shadow: 0 0 15px var(--stem-green-light);
        }

        /* Çiçek Yaprakları */
        .flower__petal {
            width: 25%;
            height: 30%;
            background: radial-gradient(circle, var(--petal-primary-color), var(--petal-secondary-color));
            border-radius: 50% 50% 50% 0;
            position: absolute;
            top: 30%;
            left: 50%;
            transform-origin: center center;
            cursor: pointer;
            transition: all 0.5s ease, transform 0.6s ease-out;
            z-index: 100;
            box-shadow: 0 0 10px var(--petal-primary-color);
            outline: none;
        }

        .flower__petal:focus {
            box-shadow: 0 0 0 3px rgba(255, 255, 255, 0.7), 0 0 15px var(--petal-primary-color);
        }

        .flower__petal--clicked {
            transform: translateY(200px) rotate(360deg);
            opacity: 0;
            pointer-events: none;
        }

        /* Mesaj Kutuları */
        .message {
            position: fixed;
            bottom: 40px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--message-bg);
            padding: 12px 30px;
            border-radius: 12px;
            color: var(--message-text);
            opacity: 0;
            transition: opacity 0.5s;
            z-index: 9999;
            pointer-events: none;
            text-shadow: 0 0 15px #000;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            min-width: 200px;
            box-sizing: border-box;
            max-width: 90vw; /* Ekran genişliğinin %90'ını geçmez */
            line-height: 1.2; /* Satır aralığını biraz daraltabiliriz */
            white-space: normal; /* Metnin alt satıra inmesine izin ver */
            text-wrap: balance; /* Metni görsel olarak dengeli sarar (modern tarayıcılar için) */
        }

        .message--welcome {
            top: 50%;
            bottom: auto;
            transform: translate(-50%, -50%);
            animation: welcomeFadeInFadeOut 3s forwards ease-in-out;
            z-index: 10000;
            background: none;
            text-shadow: 0 0 20px rgba(255, 255, 255, 0.7);
            padding: 0;
            /* clamp(minimum_boyut, tercih_edilen_boyut, maksimum_boyut) */
            /* Burada: min 20px, %5.5 vw tercih, max 60px */
            font-size: clamp(20px, 5.5vw, 60px);  
        }

        @keyframes welcomeFadeInFadeOut {
            0% { opacity: 0; transform: translate(-50%, -30%) scale(0.8); }
            30% { opacity: 1; transform: translate(-50%, -50%) scale(1); }
            70% { opacity: 1; transform: translate(-50%, -50%) scale(1); }
            100% { opacity: 0; transform: translate(-50%, -70%) scale(0.8); }
        }

        .message--final {
            top: 50%;
            bottom: auto;
            transform: translate(-50%, -50%);
            text-shadow: 0 0 20px rgba(255, 255, 255, 0.7);
            transition: opacity 1.5s ease-in;
            z-index: 10002;
            background-color: black;
            padding: 20px 40px;
            border-radius: 15px;
            box-shadow: 0 0 50px rgba(255, 255, 255, 0.5);
            max-width: 90vw;
            line-height: 1.2;
            flex-direction: column;
            white-space: normal;
            /* clamp(minimum_boyut, tercih_edilen_boyut, maksimum_boyut) */
            /* Burada: min 24px, %5.5 vw tercih, max 70px */
            font-size: clamp(24px, 5.5vw, 70px);  
        }

        /* Animasyonlu Küçük Çiçekler */
        .animated-flower {
            position: absolute;
            width: 30px;
            height: 50px;
            pointer-events: none;
            z-index: 1;
            transition: opacity 1s ease-out;
        }

        .animated-flower__center {
            width: 8px;
            height: 8px;
            background: var(--mini-flower-yellow);
            border-radius: 50%;
            position: absolute;
            z-index: 2;
            top: 15px;
            left: 50%;
            transform: translateX(-50%);
        }

        .animated-flower__petal {
            width: 12px;
            height: 12px;
            background: radial-gradient(circle, var(--mini-flower-pink), var(--mini-flower-yellow));
            border-radius: 50%;
            position: absolute;
        }

        /* Küçük çiçek yaprak pozisyonları */
        .animated-flower__petal--1 { top: 3px; left: 50%; transform: translateX(-50%); }
        .animated-flower__petal--2 { top: 27px; left: 50%; transform: translateX(-50%); }
        .animated-flower__petal--3 { left: 3px; top: 15px; transform: translateY(-50%); }
        .animated-flower__petal--4 { right: 3px; top: 15px; transform: translateY(-50%); }

        .animated-flower__stem {
            width: 4px;
            height: 20px;
            background: var(--mini-flower-green);
            position: absolute;
            top: 30px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
        }

        @keyframes fadeOutAndWobble {
            0% { opacity: 1; transform: scale(1) rotate(0deg); }
            50% { opacity: 0.5; transform: scale(0.7) rotate(15deg); }
            100% { opacity: 0; transform: scale(0.3) rotate(-15deg); }
        }

        .animated-flower--mini {
            animation: fadeOutAndWobble 3s forwards ease-out;
            transition: opacity 1s ease-out;
        }

        /* Parıltı Efektleri */
        .sparkle {
            position: absolute;
            width: 5px;
            height: 5px;
            background: radial-gradient(circle, var(--sparkle-color1), var(--sparkle-color2));
            border-radius: 50%;
            opacity: 0;
            pointer-events: none;
            animation: sparkleFadeScale 1s forwards;
            filter: blur(1px);
            box-shadow: 0 0 5px var(--sparkle-color1), 0 0 10px var(--sparkle-color2);
            transition: opacity 1s ease-out;
        }

        @keyframes sparkleFadeScale {
            0% { opacity: 0; transform: scale(0); }
            20% { opacity: 1; transform: scale(1); }
            100% { opacity: 0; transform: scale(1.5); }
        }

        .sparkle--celebration {
            position: fixed;
            width: 8px;
            height: 8px;
            background: radial-gradient(circle, var(--sparkle-color3), var(--sparkle-color4));
            border-radius: 50%;
            opacity: 0;
            pointer-events: none;
            animation: celebrationSparkleFall 3s forwards;
            filter: blur(1px);
            box-shadow: 0 0 8px var(--sparkle-color3), 0 0 15px var(--sparkle-color4);
            z-index: 10000;
            transition: opacity 1s ease-out;
        }

        @keyframes celebrationSparkleFall {
            0% { opacity: 0; transform: translate(var(--startX), var(--startY)) scale(0.5); }
            20% { opacity: 1; transform: translate(var(--midX), var(--midY)) scale(1); }
            100% { opacity: 0; transform: translate(var(--endX), var(--endY)) scale(0.7); }
        }

        /* Tema Seçici Butonları */
        .theme-selector {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 10001;
            display: flex;
            gap: 10px;
        }

        .theme-selector__button {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            cursor: pointer;
            border: 2px solid rgba(255, 255, 255, 0.5);
            transition: transform 0.2s ease-in-out, border-color 0.2s ease-in-out;
            box-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
            padding: 0;
        }

        .theme-selector__button:hover {
            transform: scale(1.1);
            border-color: white;
        }

        .theme-selector__button--default { background-color: black; }
        .theme-selector__button--blue { background-color: #0d47a1; }
        .theme-selector__button--purple { background-color: #4a148c; }
        .theme-selector__button--green { background-color: #1b5e20; }
        .theme-selector__button--pink { background-color: #E91E63; }

        /* Tekrar Başlat Butonu */
        .button--replay {
            position: fixed;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            padding: 10px 20px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1.2em;
            z-index: 10003;
            opacity: 0;
            transition: opacity 0.5s ease-in-out;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            display: none;
        }

        .button--replay:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>

    <main class="flower-page">
        <div id="flower-container" aria-label="Tıklanabilir çiçek yaprakları">
            <div id="flower-center" class="flower__center"></div>
            <div id="stem" class="flower__stem"></div>
            </div>

        <section id="messages" aria-live="polite">
            <div id="message" class="message"></div>
            <div id="welcome-message" class="message message--welcome"></div>
            <div id="final-message" class="message message--final"></div>
        </section>

        <button id="replay-button" class="button button--replay" aria-label="Tekrar başlatma butonu">Tekrar Başla</button>

        <aside id="theme-selector" class="theme-selector" aria-label="Tema seçici">
            <button class="theme-selector__button theme-selector__button--default" data-theme="default" title="Varsayılan Tema" aria-label="Varsayılan Tema"></button>
            <button class="theme-selector__button theme-selector__button--blue" data-theme="blue" title="Mavi Tema" aria-label="Mavi Tema"></button>
            <button class="theme-selector__button theme-selector__button--purple" data-theme="purple" title="Mor Tema" aria-label="Mor Tema"></button>
            <button class="theme-selector__button theme-selector__button--green" data-theme="green" title="Yeşil Tema" aria-label="Yeşil Tema"></button>
            <button class="theme-selector__button theme-selector__button--pink" data-theme="pink" title="Pembe Tema" aria-label="Pembe Tema"></button>
        </aside>
    </main>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // DOM Elementleri
            const Elements = {
                flowerContainer: document.getElementById('flower-container'),
                messageDisplay: document.getElementById('message'),
                welcomeMessage: document.getElementById('welcome-message'),
                finalMessage: document.getElementById('final-message'),
                themeSelector: document.getElementById('theme-selector'),
                body: document.body,
                replayButton: document.getElementById('replay-button')
            };

            // Sabitler
            const PETAL_MESSAGES = [
                "SELEENN",
                "NİCEE!",
                "MUTLUU",
                "SENELEREE",
                "İYİKİİ",
                "DOĞDUNN"
            ];
            const NUM_PETALS = PETAL_MESSAGES.length;
            let clickedPetalCount = 0;
            let petals = []; // Oluşturulan yaprak elementlerini tutar

            // Sesler
            // Acode'da göreceli yollarla çalışması beklenir.
            const Sounds = {
                petalClick: new Audio('sounds/pop.mp3'),
                celebration: new Audio('sounds/celebration.mp3')
            };

            // Temalar (değişmedi)
            const Themes = {
                'default': {
                    '--theme-bg-color': '#000',
                    '--flower-center-yellow-light': '#FFFF00',
                    '--flower-center-yellow-dark': '#FFD700',
                    '--petal-primary-color': '#FF0000',
                    '--petal-secondary-color': '#CC0000',
                    '--stem-green-light': '#81C784',
                    '--stem-green-dark': '#388E3C',
                    '--mini-flower-yellow': '#FFFF00',
                    '--mini-flower-pink': '#FF0000',
                    '--mini-flower-green': '#388E3C',
                    '--sparkle-color1': '#FFD700',
                    '--sparkle-color2': '#FFFFFF',
                    '--sparkle-color3': '#FF4500',
                    '--sparkle-color4': '#00BFFF'
                },
                'blue': {
                    '--theme-bg-color': '#0d47a1',
                    '--flower-center-yellow-light': '#ADD8E6',
                    '--flower-center-yellow-dark': '#87CEEB',
                    '--petal-primary-color': '#42A5F5',
                    '--petal-secondary-color': '#2196F3',
                    '--stem-green-light': '#66BB6A',
                    '--stem-green-dark': '#4CAF50',
                    '--mini-flower-yellow': '#B0E0E6',
                    '--mini-flower-pink': '#87CEFA',
                    '--mini-flower-green': '#A5D6A7',
                    '--sparkle-color1': '#B0E0E6',
                    '--sparkle-color2': '#FFFFFF',
                    '--sparkle-color3': '#ADD8E6',
                    '--sparkle-color4': '#42A5F5'
                },
                'purple': {
                    '--theme-bg-color': '#4a148c',
                    '--flower-center-yellow-light': '#E1BEE7',
                    '--flower-center-yellow-dark': '#CE93D8',
                    '--petal-primary-color': '#BA68C8',
                    '--petal-secondary-color': '#9C27B0',
                    '--stem-green-light': '#7CB342',
                    '--stem-green-dark': '#689F38',
                    '--mini-flower-yellow': '#F3E5F5',
                    '--mini-flower-pink': '#E0BBE4',
                    '--mini-flower-green': '#C5E1A5',
                    '--sparkle-color1': '#E1BEE7',
                    '--sparkle-color2': '#FFFFFF',
                    '--sparkle-color3': '#BA68C8',
                    '--sparkle-color4': '#9C27B0'
                },
                'green': {
                    '--theme-bg-color': '#1b5e20',
                    '--flower-center-yellow-light': '#C8E6C9',
                    '--flower-center-yellow-dark': '#A5D6A7',
                    '--petal-primary-color': '#81C784',
                    '--petal-secondary-color': '#4CAF50',
                    '--stem-green-light': '#FFEB3B',
                    '--stem-green-dark': '#FBC02D',
                    '--mini-flower-yellow': '#F0F4C3',
                    '--mini-flower-pink': '#C5E1A5',
                    '--mini-flower-green': '#FFEB3B',
                    '--sparkle-color1': '#C8E6C9',
                    '--sparkle-color2': '#FFFFFF',
                    '--sparkle-color3': '#81C784',
                    '--sparkle-color4': '#4CAF50'
                },
                'pink': {
                    '--theme-bg-color': '#880E4F',
                    '--flower-center-yellow-light': '#F8BBD0',
                    '--flower-center-yellow-dark': '#F48FB1',
                    '--petal-primary-color': '#EC407A',
                    '--petal-secondary-color': '#D81B60',
                    '--stem-green-light': '#A5D6A7',
                    '--stem-green-dark': '#66BB6A',
                    '--mini-flower-yellow': '#FCE4EC',
                    '--mini-flower-pink': '#F06292',
                    '--mini-flower-green': '#81C784',
                    '--sparkle-color1': '#F8BBD0',
                    '--sparkle-color2': '#FFFFFF',
                    '--sparkle-color3': '#EC407A',
                    '--sparkle-color4': '#FCE4EC'
                }
            };

            // Yardımcı Fonksiyonlar

            function playSound(audioElement) {
                try {
                    audioElement.currentTime = 0;
                    audioElement.play();
                } catch (e) {
                    console.warn("Ses çalma hatası:", e);
                }
            }

            function applyTheme(themeName) {
                const selectedTheme = Themes[themeName];
                if (selectedTheme) {
                    for (const [prop, value] of Object.entries(selectedTheme)) {
                        document.documentElement.style.setProperty(prop, value);
                    }
                    Elements.body.setAttribute('data-theme', themeName);
                }
            }

            function createAnimatedFlower(x, y, type = 'mini') {
                const flower = document.createElement("div");
                flower.className = `animated-flower animated-flower--${type}`;
                flower.style.left = (x - 15) + "px";
                flower.style.top = (y - 25) + "px";

                for (let i = 1; i <= 4; i++) {
                    const petal = document.createElement("div");
                    petal.className = `animated-flower__petal animated-flower__petal--${i}`;
                    flower.appendChild(petal);
                }

                const center = document.createElement("div");
                center.className = "animated-flower__center";
                flower.appendChild(center);

                const stem = document.createElement("div");
                stem.className = "animated-flower__stem";
                flower.appendChild(stem);

                document.body.appendChild(flower);

                if (type === 'mini') {
                    setTimeout(() => flower.remove(), 3000);
                }
            }

            function createSparkle(x, y, isCelebration = false) {
                const sparkle = document.createElement("div");
                sparkle.className = isCelebration ? "sparkle sparkle--celebration" : "sparkle";

                const sparkleColorIndex = Math.floor(Math.random() * 4) + 1;
                const primaryColorVar = `var(--sparkle-color${sparkleColorIndex})`;
                const secondaryColorVar = `var(--sparkle-color${(sparkleColorIndex % 4) + 1})`;

                sparkle.style.background = `radial-gradient(circle, ${primaryColorVar}, ${secondaryColorVar})`;
                sparkle.style.boxShadow = `0 0 5px ${primaryColorVar}, 0 0 10px ${secondaryColorVar}`;

                if (isCelebration) {
                    const startX = Math.random() * window.innerWidth;
                    const startY = Math.random() * window.innerHeight * 0.2;
                    const endX = startX + (Math.random() - 0.5) * 400;
                    const endY = window.innerHeight + 50;

                    sparkle.style.setProperty('--startX', `${startX}px`);
                    sparkle.style.setProperty('--startY', `${startY}px`);
                    sparkle.style.setProperty('--midX', `${startX + (Math.random() - 0.5) * 200}px`);
                    sparkle.style.setProperty('--midY', `${startY + (window.innerHeight - startY) * 0.5}px`);
                    sparkle.style.setProperty('--endX', `${endX}px`);
                    sparkle.style.setProperty('--endY', `${endY}px`);
                    sparkle.style.animationDelay = `${Math.random() * 0.5}s`;
                    setTimeout(() => sparkle.remove(), 3000);
                } else {
                    sparkle.style.left = x + "px";
                    sparkle.style.top = y + "px";
                    setTimeout(() => sparkle.remove(), 1000);
                }
                document.body.appendChild(sparkle);
            }

            // Artık font boyutunu manuel ayarlayan bir fonksiyonumuz yok,
            // CSS'teki clamp() ve text-wrap ile otomatik hallolacak.
            function setElementText(element, text) {
                element.textContent = text;
            }


            function triggerCelebration() {
                setElementText(Elements.messageDisplay, "İYİKİ DOĞDUN SELEEN! 🎉");
                Elements.messageDisplay.style.opacity = 1;

                const numSparkles = 100;
                for (let i = 0; i < numSparkles; i++) {
                    createSparkle(0, 0, true);
                }

                playSound(Sounds.celebration);

                setTimeout(() => {
                    Elements.messageDisplay.style.opacity = 0;

                    Elements.flowerContainer.style.animation = 'none';
                    Elements.flowerContainer.style.opacity = 0;
                    Elements.flowerContainer.style.transform = 'scale(0.5)';

                    document.querySelectorAll('.animated-flower, .sparkle, .sparkle--celebration').forEach(el => {
                        el.style.opacity = 0;
                        setTimeout(() => el.remove(), 1000);
                    });

                    Elements.themeSelector.style.opacity = 0;
                    Elements.body.style.backgroundColor = 'black';

                    setTimeout(() => {
                        setElementText(Elements.finalMessage, "BİR GÜN DEĞİL, HER GÜN ÖZELSİN!");
                        Elements.finalMessage.style.opacity = 1;
                        Elements.replayButton.style.display = 'block';
                        setTimeout(() => Elements.replayButton.style.opacity = 1, 100);
                    }, 500);
                }, 2000);
            }

            function resetAnimation() {
                clickedPetalCount = 0;
                Elements.messageDisplay.style.opacity = 0;
                Elements.finalMessage.style.opacity = 0;
                Elements.replayButton.style.opacity = 0;
                Elements.replayButton.style.display = 'none';

                document.querySelectorAll('.animated-flower, .sparkle, .sparkle--celebration').forEach(el => el.remove());
                petals.forEach(petal => petal.remove());
                petals = [];

                Elements.flowerContainer.style.transition = 'none';
                Elements.flowerContainer.style.opacity = 0;
                Elements.flowerContainer.style.transform = 'scale(0.5)';

                requestAnimationFrame(() => {
                    requestAnimationFrame(() => {
                        Elements.flowerContainer.style.transition = 'opacity 1s ease-out, transform 1s ease-out';
                        Elements.flowerContainer.style.opacity = 1;
                        Elements.flowerContainer.style.transform = 'scale(1)';
                    });
                });

                createPetals();

                Elements.themeSelector.style.opacity = 1;
                applyTheme('default');

                const welcomeText = "Merhaba Selen! Bu sana özel bir an. Her bir yaprakta kalbimizden geçen bir mesaj var.";
                setElementText(Elements.welcomeMessage, welcomeText);
                Elements.welcomeMessage.style.opacity = 0; // Ensures it starts hidden before animation
                setTimeout(() => {
                    Elements.welcomeMessage.style.animation = 'welcomeFadeInFadeOut 3s forwards ease-in-out';
                }, 50); // Small delay to ensure animation restarts if reset
            }

            function createPetals() {
                petals.forEach(petal => petal.remove());
                petals = [];

                for (let i = 0; i < NUM_PETALS; i++) {
                    const petal = document.createElement("div");
                    petal.className = "flower__petal";
                    petal.setAttribute('role', 'button');
                    petal.setAttribute('aria-label', `Mesaj için '${PETAL_MESSAGES[i]}' yazılı taç yaprağa tıkla`);
                    petal.tabIndex = 0;

                    const angle = i * (360 / NUM_PETALS);
                    const radius = 80;
                    const rad = angle * Math.PI / 180;
                    const x = Math.cos(rad) * radius;
                    const y = Math.sin(rad) * radius;

                    petal.style.transform = `translate(-50%, -50%) translate(${x}px, ${y}px) rotate(${angle}deg)`;
                    petal.dataset.message = PETAL_MESSAGES[i];

                    petal.addEventListener("click", handlePetalInteraction);
                    petal.addEventListener("keydown", (event) => {
                        if (event.key === 'Enter' || event.key === ' ') {
                            event.preventDefault();
                            handlePetalInteraction.call(petal, event);
                        }
                    });

                    Elements.flowerContainer.appendChild(petal);
                    petals.push(petal);
                }
            }

            // Olay Yöneticileri

            function handlePetalInteraction(event) {
                event.stopPropagation();

                if (this.classList.contains('flower__petal--clicked')) return;

                setElementText(Elements.messageDisplay, this.dataset.message);
                Elements.messageDisplay.style.opacity = 1;

                this.classList.add('flower__petal--clicked');
                playSound(Sounds.petalClick);

                for (let j = 0; j < 12; j++) {
                    const randomX = Math.random() * window.innerWidth;
                    const randomY = Math.random() * window.innerHeight;
                    createAnimatedFlower(randomX, randomY, 'mini');
                }

                setTimeout(() => {
                    if (clickedPetalCount < NUM_PETALS) {
                        Elements.messageDisplay.style.opacity = 0;
                    }
                }, 1000);

                clickedPetalCount++;
                if (clickedPetalCount === NUM_PETALS) {
                    setTimeout(() => {
                        triggerCelebration();
                    }, 500);
                }
            }

            Elements.body.addEventListener("click", function (e) {
                const isInteractiveElement = e.target.closest(".flower__petal") ||
                                             e.target.closest(".theme-selector__button") ||
                                             e.target.closest("#flower-center") ||
                                             e.target.closest("#replay-button"); // replay-button kontrolü eklendi

                if (!isInteractiveElement) {
                    createSparkle(e.clientX, e.clientY);
                }
            });

            Elements.themeSelector.addEventListener("click", (event) => {
                const button = event.target.closest(".theme-selector__button");
                if (button) {
                    const theme = button.dataset.theme;
                    applyTheme(theme);
                }
            });

            Elements.replayButton.addEventListener("click", resetAnimation);

            // Başlangıç animasyonları ve kurulum
            applyTheme('default');
            createPetals();

            const welcomeText = "Merhaba Selen! Bu sana özel bir an. Her bir yaprakta kalbimizden geçen bir mesaj var.";
            setElementText(Elements.welcomeMessage, welcomeText);
            Elements.welcomeMessage.style.opacity = 0; // Animasyondan önce gizli başladığından emin olun
            setTimeout(() => {
                Elements.welcomeMessage.style.animation = 'welcomeFadeInFadeOut 3s forwards ease-in-out';
            }, 50); // Sıfırlama durumunda animasyonun yeniden başlaması için kısa bir gecikme
        });
    </script>
</body>
</html>
