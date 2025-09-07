# questionnairecoaching
Questionnaire coaching
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trouve ton coaching idéal - Peak My Performance</title>
    <meta name="description" content="Questionnaire personnalisé pour trouver la formule de coaching sportif adaptée à tes besoins">
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }
        
        .container {
            max-width: 400px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            text-align: center;
        }
        
        .question-card {
            display: none;
            animation: fadeIn 0.5s ease-in;
        }
        
        .question-card.active {
            display: block;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        h1 {
            color: #333;
            margin-bottom: 10px;
            font-size: 1.8em;
        }
        
        .subtitle {
            color: #666;
            margin-bottom: 30px;
            font-size: 0.9em;
        }
        
        .question {
            font-size: 1.2em;
            font-weight: bold;
            color: #333;
            margin-bottom: 25px;
            line-height: 1.4;
        }
        
        .options {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-bottom: 30px;
        }
        
        .option {
            background: #f8f9fa;
            border: 2px solid #e9ecef;
            border-radius: 15px;
            padding: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 500;
        }
        
        .option:hover {
            background: #e3f2fd;
            border-color: #2196f3;
            transform: translateY(-2px);
        }
        
        .option.selected {
            background: #2196f3;
            color: white;
            border-color: #1976d2;
        }
        
        .next-btn {
            background: linear-gradient(45deg, #2196f3, #21cbf3);
            color: white;
            border: none;
            border-radius: 25px;
            padding: 15px 30px;
            font-size: 1em;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            opacity: 0.5;
            pointer-events: none;
        }
        
        .next-btn.enabled {
            opacity: 1;
            pointer-events: auto;
        }
        
        .next-btn:hover.enabled {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(33, 150, 243, 0.4);
        }
        
        .progress {
            width: 100%;
            height: 6px;
            background: #e9ecef;
            border-radius: 3px;
            margin-bottom: 30px;
            overflow: hidden;
        }
        
        .progress-bar {
            height: 100%;
            background: linear-gradient(45deg, #2196f3, #21cbf3);
            width: 0%;
            transition: width 0.5s ease;
        }
        
        .result {
            background: linear-gradient(45deg, #4caf50, #45a049);
            color: white;
            border-radius: 15px;
            padding: 25px;
            margin-top: 20px;
        }
        
        .result h2 {
            margin: 0 0 15px 0;
            font-size: 1.5em;
        }
        
        .result p {
            margin: 10px 0;
            line-height: 1.5;
        }
        
        .cta {
            background: white;
            color: #4caf50;
            border: none;
            border-radius: 25px;
            padding: 12px 25px;
            font-weight: bold;
            margin: 10px 5px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .cta:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        .emoji {
            font-size: 2em;
            margin-bottom: 15px;
        }
        
        .footer {
            margin-top: 20px;
            font-size: 0.8em;
            color: #666;
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Question 1 -->
        <div class="question-card active" id="q1">
            <div class="progress">
                <div class="progress-bar" style="width: 20%"></div>
            </div>
            <div class="emoji">🏃‍♂️</div>
            <h1>Trouve ton coaching idéal !</h1>
            <p class="subtitle">Quelques questions pour personnaliser ton accompagnement</p>
            <div class="question">Quel est ton sport principal ?</div>
            <div class="options">
                <div class="option" onclick="selectAnswer(1, 'triathlon', this)">🏊‍♂️🚴‍♂️🏃‍♂️ Triathlon</div>
                <div class="option" onclick="selectAnswer(1, 'running', this)">🏃‍♂️ Course à pied</div>
                <div class="option" onclick="selectAnswer(1, 'cycling', this)">🚴‍♂️ Cyclisme</div>
                <div class="option" onclick="selectAnswer(1, 'swimming', this)">🏊‍♂️ Natation</div>
                <div class="option" onclick="selectAnswer(1, 'other', this)">💪 Autre sport</div>
            </div>
            <button class="next-btn" onclick="goToQuestion(2)">Suivant</button>
        </div>

        <!-- Question 2 -->
        <div class="question-card" id="q2">
            <div class="progress">
                <div class="progress-bar" style="width: 40%"></div>
            </div>
            <div class="emoji">📈</div>
            <div class="question">Quel est ton niveau actuel ?</div>
            <div class="options">
                <div class="option" onclick="selectAnswer(2, 'beginner', this)">🌱 Débutant (- 1 an)</div>
                <div class="option" onclick="selectAnswer(2, 'intermediate', this)">📈 Intermédiaire (1-3 ans)</div>
                <div class="option" onclick="selectAnswer(2, 'advanced', this)">🏆 Confirmé (3+ ans)</div>
                <div class="option" onclick="selectAnswer(2, 'competition', this)">🥇 Compétition</div>
            </div>
            <button class="next-btn" onclick="goToQuestion(3)">Suivant</button>
        </div>

        <!-- Question 3 -->
        <div class="question-card" id="q3">
            <div class="progress">
                <div class="progress-bar" style="width: 60%"></div>
            </div>
            <div class="emoji">🎯</div>
            <div class="question">Quel est ton objectif principal ?</div>
            <div class="options">
                <div class="option" onclick="selectAnswer(3, 'health', this)">💪 Forme & bien-être</div>
                <div class="option" onclick="selectAnswer(3, 'performance', this)">🚀 Améliorer mes performances</div>
                <div class="option" onclick="selectAnswer(3, 'competition', this)">🏅 Préparer une compétition</div>
                <div class="option" onclick="selectAnswer(3, 'comeback', this)">🔄 Reprendre après blessure</div>
            </div>
            <button class="next-btn" onclick="goToQuestion(4)">Suivant</button>
        </div>

        <!-- Question 4 -->
        <div class="question-card" id="q4">
            <div class="progress">
                <div class="progress-bar" style="width: 80%"></div>
            </div>
            <div class="emoji">💰</div>
            <div class="question">Quel budget pour ton coaching ?</div>
            <div class="options">
                <div class="option" onclick="selectAnswer(4, 'budget1', this)">📊 55-75€/mois</div>
                <div class="option" onclick="selectAnswer(4, 'budget2', this)">📈 75-90€/mois</div>
                <div class="option" onclick="selectAnswer(4, 'budget3', this)">🚀 90-150€/mois</div>
                <div class="option" onclick="selectAnswer(4, 'flexible', this)">✨ Budget flexible</div>
            </div>
            <button class="next-btn" onclick="goToQuestion(5)">Suivant</button>
        </div>

        <!-- Question 5 -->
        <div class="question-card" id="q5">
            <div class="progress">
                <div class="progress-bar" style="width: 100%"></div>
            </div>
            <div class="emoji">📞</div>
            <div class="question">Quel niveau de suivi préfères-tu ?</div>
            <div class="options">
                <div class="option" onclick="selectAnswer(5, 'basic', this)">📱 Suivi mensuel simple</div>
                <div class="option" onclick="selectAnswer(5, 'regular', this)">💬 Messages + appel mensuel</div>
                <div class="option" onclick="selectAnswer(5, 'premium', this)">🔥 Suivi illimité + analyses</div>
            </div>
            <button class="next-btn" onclick="showResult()">Voir mon coaching !</button>
        </div>

        <!-- Résultats -->
        <div class="question-card" id="result">
            <div class="emoji" id="result-emoji">🎉</div>
            <div class="result">
                <h2>Ta formule idéale :</h2>
                <p id="result-formula"></p>
                <p id="result-description"></p>
                <button class="cta" onclick="contact()">Me contacter</button>
            </div>
            <div class="footer">
                <p>Peak My Performance - Coaching sportif personnalisé</p>
            </div>
        </div>
    </div>

    <script>
        let answers = {};

        function selectAnswer(questionNum, value, element) {
            answers[`q${questionNum}`] = value;
            
            const options = element.parentNode.querySelectorAll('.option');
            options.forEach(option => option.classList.remove('selected'));
            
            element.classList.add('selected');
            
            const nextBtn = element.closest('.question-card').querySelector('.next-btn');
            nextBtn.classList.add('enabled');
        }

        function goToQuestion(questionNum) {
            const currentQuestionNum = questionNum - 1;
            if (!answers[`q${currentQuestionNum}`]) {
                return;
            }
            
            document.querySelectorAll('.question-card').forEach(card => {
                card.classList.remove('active');
            });
            
            document.getElementById(`q${questionNum}`).classList.add('active');
        }

        function showResult() {
            if (!answers.q5) {
                return;
            }
            
            const recommendation = calculateRecommendation();
            
            document.getElementById('result-emoji').textContent = recommendation.emoji;
            document.getElementById('result-formula').textContent = recommendation.name;
            document.getElementById('result-description').textContent = recommendation.description;
            
            document.querySelectorAll('.question-card').forEach(card => {
                card.classList.remove('active');
            });
            document.getElementById('result').classList.add('active');
        }

        function calculateRecommendation() {
            const sport = answers.q1;
            const level = answers.q2;
            const objective = answers.q3;
            const budget = answers.q4;
            const support = answers.q5;

            if (sport === 'triathlon') {
                if (budget === 'budget3' || support === 'premium' || level === 'competition') {
                    return {
                        name: 'HAUT NIVEAU 🏆',
                        description: 'Suivi hebdomadaire, analyses complètes, réathlétisation intégrée',
                        emoji: '🏆'
                    };
                } else if (budget === 'budget2' || support === 'regular' || level === 'advanced') {
                    return {
                        name: 'ÉQUILIBRE',
                        description: 'Suivi bi-mensuel, analyse vidéo, bilan posture',
                        emoji: '⚖️'
                    };
                } else {
                    return {
                        name: 'BASIQUE',
                        description: 'Programme personnalisé, suivi mensuel',
                        emoji: '🌟'
                    };
                }
            } else {
                if (budget === 'budget2' || budget === 'budget3' || support === 'regular' || support === 'premium' || level === 'advanced' || level === 'competition') {
                    return {
                        name: 'Performance Plus',
                        description: 'Suivi renforcé, analyse technique, bilan posture',
                        emoji: '🚀'
                    };
                } else {
                    return {
                        name: 'Essentiel Plus',
                        description: 'Programme personnalisé, bases essentielles',
                        emoji: '✨'
                    };
                }
            }
        }

        function contact() {
            const formulaName = document.getElementById('result-formula').textContent;
            const message = `Bonjour ! Je viens de faire votre questionnaire coaching. Ma formule recommandée est : ${formulaName}. Pouvez-vous me donner plus d'infos sur cette formule et les tarifs ? Merci !`;
            
            const phoneNumber = '33695453283';
            const encodedMessage = encodeURIComponent(message);
            
            window.open(`https://wa.me/${phoneNumber}?text=${encodedMessage}`, '_blank');
        }
    </script>
</body>
</html>
