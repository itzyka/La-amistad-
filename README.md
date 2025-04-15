# La-amistad-
un lindo mensaje para mis amigos.
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Amigos Animalitos</title>
    <style>
        body {
            font-family: 'Comic Sans MS', cursive, sans-serif;
            background-color: #FFF5E6;
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            color: #5E4B56;
            text-align: center;
            overflow-x: hidden;
        }

        h1 {
            color: #FF8FAB;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
            margin-bottom: 30px;
        }

        .animal-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            margin-bottom: 30px;
        }

        .animal {
            width: 120px;
            height: 120px;
            cursor: pointer;
            transition: all 0.3s ease;
            border-radius: 50%;
            border: 4px solid #FFD1DC;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            background-color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        .animal:hover {
            transform: scale(1.1) rotate(5deg);
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
        }

        .animal img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .message-container {
            background-color: #FFD1DC;
            border-radius: 20px;
            padding: 20px;
            max-width: 80%;
            margin: 20px auto;
            display: none;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            border: 3px dashed #FF8FAB;
        }

        .message {
            font-size: 18px;
            color: #5E4B56;
        }

        .footer {
            margin-top: 30px;
            color: #FF8FAB;
            font-size: 14px;
        }

        .controls {
            margin-top: 20px;
            display: flex;
            gap: 10px;
        }

        button {
            background-color: #FF8FAB;
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 20px;
            cursor: pointer;
            font-family: 'Comic Sans MS', cursive, sans-serif;
            transition: all 0.3s;
        }

        button:hover {
            background-color: #FFB3C6;
            transform: scale(1.05);
        }
    </style>
</head>
<body>
    <h1>❤️ Amigos Animalitos ❤️</h1>
    
    <div class="animal-container">
        <div class="animal" data-animal="mapache" data-sound="meow">
            <img src="https://cdn.vectorstock.com/i/500p/55/04/cartoon-raccoon-on-a-white-background-vector-44035504.jpg" alt="Mapache">
        </div>
        <div class="animal" data-animal="pinguino" data-sound="chirp">
            <img src="https://static.vecteezy.com/system/resources/previews/003/417/359/original/cute-cartoon-baby-penguin-vector.jpg" alt="Pingüino">
        </div>
        <div class="animal" data-animal="mariposa" data-sound="bell">
            <img src="https://i.pinimg.com/originals/28/f1/2a/28f12a349b9d067e71f6383addce8972.jpg" alt="Mariposa">
        </div>
        <div class="animal" data-animal="rana" data-sound="ribbit">
            <img src="https://static.vecteezy.com/system/resources/previews/009/159/551/non_2x/cute-frog-cartoon-illustration-vector.jpg" alt="Rana">
        </div>
        <div class="animal" data-animal="gato" data-sound="purr">
            <img src="https://img.freepik.com/premium-vector/cute-cat-standing-cartoon-vector-illustration_379823-20796.jpg?w=2000" alt="Gato">
        </div>
    </div>
    
    <div class="message-container">
        <p class="message"></p>
    </div>
    
    <div class="controls">
       
        <button id="resetBtn">🔄 Reiniciar</button>
    </div>
    
    <div class="footer">
        ¡Haz clic en tu animalito favorito para recibir un mensaje especial!
    </div>

    

    <script>
        // Sonidos para los animales
        const sounds = {
            meow: new Audio('https://www.soundjay.com/meow/sounds/cat-meow-01.mp3'),
            chirp: new Audio('https://www.soundjay.com/bird/sounds/bird-chirp-01.mp3'),
            bell: new Audio('https://www.soundjay.com/mechanical/sounds/wind-chime-01.mp3'),
            ribbit: new Audio('https://www.soundjay.com/frog/sounds/frog-ribbit-01.mp3'),
            purr: new Audio('https://www.soundjay.com/meow/sounds/cat-purring-01.mp3')
        };

        // Mensajes para cada animal
        const messages = {
            mapache: [
                "Eres tan inteligente y astuto como un mapache. ¡Nada puede detenerte!",
                "Tu curiosidad te llevará a lugares maravillosos, igual que a este mapache aventurero.",
                "Aunque a veces te escondas, siempre brillas con tu propia luz."
            ],
            pinguino: [
                "Eres tan especial y único como un pingüino en el polo norte. ¡Brilla con tu propia luz!",
                "Los desafíos de la vida son como el frío antártico, pero tú, como este pingüino, eres fuerte para superarlos.",
                "Tu corazón cálido derrite cualquier hielo, igual que el amor de estos pingüinos."
            ],
            mariposa: [
                "Como esta mariposa, estás destinado a transformarte y volar alto. ¡El cielo es tu límite!",
                "Tu belleza interior brilla como los colores de esta mariposa.",
                "Las etapas difíciles son solo tu proceso de convertirse en una hermosa mariposa."
            ],
            rana: [
                "Saltando de felicidad como esta ranita, recuerda que cada día es una nueva oportunidad para ser feliz.",
                "Tu capacidad de adaptarte es tan admirable como esta ranita en su charco.",
                "Aunque a veces te sientas pequeño, como esta rana, tienes un gran corazón y un gran potencial."
            ],
            gato: [
                "Tienes la elegancia, la curiosidad y el encanto de este gatito. ¡El mundo es tuyo para explorar!",
                "Como este gato, sabes exactamente cuándo descansar y cuándo jugar. ¡Eso es sabiduría!",
                "Tu independencia es admirable, pero recuerda que también eres amado, como este gatito mimado."
            ]
        };

        // Elementos del DOM
        const animals = document.querySelectorAll('.animal');
        const messageContainer = document.querySelector('.message-container');
        const messageText = document.querySelector('.message');
        const musicToggle = document.getElementById('musicToggle');
        const resetBtn = document.getElementById('resetBtn');
        const backgroundMusic = document.getElementById('backgroundMusic');

        // Reproducir música de fondo (con interacción del usuario primero)
        document.body.addEventListener('click', () => {
            backgroundMusic.play().catch(e => console.log("Auto-play prevented"));
        }, { once: true });

        // Control de música
        musicToggle.addEventListener('click', () => {
            if (backgroundMusic.paused) {
                backgroundMusic.play();
                musicToggle.textContent = "🔊 Música OFF";
            } else {
                backgroundMusic.pause();
                musicToggle.textContent = "🔊 Música ON";
            }
        });

        // Reiniciar
        resetBtn.addEventListener('click', () => {
            messageContainer.style.display = 'none';
        });

        // Eventos para cada animal
        animals.forEach(animal => {
            animal.addEventListener('click', () => {
                const animalType = animal.getAttribute('data-animal');
                const soundType = animal.getAttribute('data-sound');
                
                // Reproducir sonido
                sounds[soundType].currentTime = 0;
                sounds[soundType].play();
                
                // Mostrar mensaje aleatorio
                const animalMessages = messages[animalType];
                const randomMessage = animalMessages[Math.floor(Math.random() * animalMessages.length)];
                
                messageText.textContent = randomMessage;
                messageContainer.style.display = 'block';
                
                // Animación
                animal.style.transform = 'scale(0.9)';
                setTimeout(() => {
                    animal.style.transform = 'scale(1.1) rotate(5deg)';
                }, 100);
            });
        });
    </script>
</body>
</html>
