<!DOCTYPE html>
<html lang="gu">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ધોરણ ૮ - સમાનાર્થી અને વિરુદ્ધાર્થી ક્વિઝ</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #f5f7fa, #c3cfe2);
      margin: 0;
      padding: 20px;
    }
    .container {
      max-width: 800px;
      margin: 0 auto;
      background: white;
      border-radius: 15px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.1);
      padding: 30px;
    }
    h1 {
      text-align: center;
      color: #2c3e50;
      margin-bottom: 30px;
    }
    .question {
      font-size: 1.2rem;
      margin: 25px 0;
      font-weight: bold;
      color: #34495e;
    }
    .options {
      display: flex;
      flex-direction: column;
      gap: 12px;
    }
    .option {
      padding: 15px;
      border: 2px solid #ddd;
      border-radius: 10px;
      cursor: pointer;
      transition: all 0.3s;
      font-size: 1.1rem;
    }
    .option:hover {
      background: #f8f9fa;
      border-color: #3498db;
    }
    .option.correct {
      background: #d4edda;
      border-color: #28a745;
      color: #155724;
    }
    .option.wrong {
      background: #f8d7da;
      border-color: #dc3545;
      color: #721c24;
    }
    .result {
      margin-top: 10px;
      font-weight: bold;
      font-size: 1.1rem;
    }
    .score {
      text-align: center;
      font-size: 1.5rem;
      margin: 30px 0;
      color: #2c3e50;
    }
    button {
      background: #3498db;
      color: white;
      border: none;
      padding: 12px 25px;
      border-radius: 8px;
      cursor: pointer;
      font-size: 1.1rem;
      margin: 20px auto;
      display: block;
    }
    button:hover {
      background: #2980b9;
    }
    .footer {
      text-align: center;
      margin-top: 30px;
      color: #7f8c8d;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>🧠 ધોરણ ૮ ગુજરાતી ક્વિઝ<br>સમાનાર્થી અને વિરુદ્ધાર્થી</h1>
    
    <div id="quiz">
      <!-- Questions will be loaded here by JavaScript -->
    </div>

    <div class="score" id="score">સ્કોર: 0 / 15</div>
    <button onclick="restartQuiz()">નવી ક્વિઝ શરૂ કરો</button>
  </div>

  <script>
    const questions = [
      {
        q: "1. પરિવાર શબ્દનો સમાનાર્થી છે?",
        options: ["કુટુંબ", "શત્રુ", "અપાર", "અંધકાર"],
        answer: 0
      },
      {
        q: "2. મિત્ર શબ્દનો સમાનાર્થી છે?",
        options: ["શત્રુ", "સખા", "વિરોધ", "દુ:ખ"],
        answer: 1
      },
      {
        q: "3. સુગંધ શબ્દનો સમાનાર્થી છે?",
        options: ["દુર્ગંધ", "સોંધ", "અંધકાર", "નીચું"],
        answer: 1
      },
      {
        q: "4. જન્મ શબ્દનો સમાનાર્થી છે?",
        options: ["મૃત્યુ", "ઉત્પત્તિ", "અપકાર", "અશુભ"],
        answer: 1
      },
      {
        q: "5. યશ શબ્દનો સમાનાર્થી છે?",
        options: ["કીર્તિ", "અપયશ", "ભય", "અંત"],
        answer: 0
      },
      {
        q: "6. સુખ શબ્દનો વિરુદ્ધાર્થી છે?",
        options: ["આનંદ", "દુ:ખ", "હર્ષ", "સંતોષ"],
        answer: 1
      },
      {
        q: "7. પ્રકાશ શબ્દનો વિરુદ્ધાર્થી છે?",
        options: ["અંધકાર", "ઉજાસ", "સૂર્ય", "દીવો"],
        answer: 0
      },
      {
        q: "8. મિત્ર શબ્દનો વિરુદ્ધાર્થી છે?",
        options: ["સખા", "શત્રુ", "ભાઈ", "પિતા"],
        answer: 1
      },
      {
        q: "9. ઊંચું શબ્દનો વિરુદ્ધાર્થી છે?",
        options: ["નીચું", "લાંબું", "મોટું", "સારું"],
        answer: 0
      },
      {
        q: "10. સત્ય શબ્દનો વિરુદ્ધાર્થી છે?",
        options: ["અસત્ય", "સાચું", "ખરું", "નિર્દોષ"],
        answer: 0
      },
      {
        q: "11. ગરમ શબ્દનો વિરુદ્ધાર્થી છે?",
        options: ["ઠંડું", "તાપ", "અગ્નિ", "ઉષ્ણ"],
        answer: 0
      },
      {
        q: "12. જન્મ શબ્દનો વિરુદ્ધાર્થી છે?",
        options: ["મૃત્યુ", "ઉત્પત્તિ", "આરંભ", "પ્રારંભ"],
        answer: 0
      },
      {
        q: "13. વાયરો શબ્દનો સમાનાર્થી છે?",
        options: ["પવન", "પાણી", "અગ્નિ", "પૃથ્વી"],
        answer: 0
      },
      {
        q: "14. આનંદ શબ્દનો સમાનાર્થી છે?",
        options: ["શોક", "હર્ષ", "અંધકાર", "નિરાશા"],
        answer: 1
      },
      {
        q: "15. સુગંધ શબ્દનો વિરુદ્ધાર્થી છે?",
        options: ["સોંધ", "દુર્ગંધ", "મીઠાશ", "સ્વાદ"],
        answer: 1
      }
    ];

    let currentQuestion = 0;
    let score = 0;
    let answered = false;

    function loadQuestion() {
      const quizDiv = document.getElementById('quiz');
      quizDiv.innerHTML = `
        <div class="question">${questions[currentQuestion].q}</div>
        <div class="options" id="options"></div>
      `;

      const optionsDiv = document.getElementById('options');
      questions[currentQuestion].options.forEach((option, index) => {
        const div = document.createElement('div');
        div.className = 'option';
        div.textContent = option;
        div.onclick = () => selectAnswer(index, div);
        optionsDiv.appendChild(div);
      });

      answered = false;
      updateScore();
    }

    function selectAnswer(selectedIndex, element) {
      if (answered) return;
      answered = true;

      const correctIndex = questions[currentQuestion].answer;
      const options = document.querySelectorAll('.option');

      options.forEach((opt, i) => {
        if (i === correctIndex) {
          opt.classList.add('correct');
        }
        if (i === selectedIndex && i !== correctIndex) {
          opt.classList.add('wrong');
        }
      });

      if (selectedIndex === correctIndex) {
        score++;
      }

      updateScore();

      // Auto move to next after 1.5 seconds
      setTimeout(() => {
        currentQuestion++;
        if (currentQuestion < questions.length) {
          loadQuestion();
        } else {
          showFinalResult();
        }
      }, 1500);
    }

    function updateScore() {
      document.getElementById('score').textContent = `સ્કોર: ${score} / ${questions.length}`;
    }

    function showFinalResult() {
      const quizDiv = document.getElementById('quiz');
      const percentage = Math.round((score / questions.length) * 100);
      
      let message = '';
      if (percentage >= 80) message = '🎉 ઉત્તમ! તમે ખૂબ સારું પ્રદર્શન કર્યું છે!';
      else if (percentage >= 60) message = '👍 સારું! વધુ પ્રેક્ટિસ કરો.';
      else message = '📚 વધુ અભ્યાસ કરવાની જરૂર છે.';

      quizDiv.innerHTML = `
        <h2 style="text-align:center; color:#2c3e50;">ક્વિઝ પૂર્ણ!</h2>
        <div style="text-align:center; font-size:2rem; margin:30px 0;">
          તમારો સ્કોર: <strong>${score} / ${questions.length}</strong><br>
          (${percentage}%)
        </div>
        <p style="text-align:center; font-size:1.3rem;">${message}</p>
      `;
    }

    function restartQuiz() {
      currentQuestion = 0;
      score = 0;
      loadQuestion();
    }

    // Start the quiz
    window.onload = loadQuestion;
  </script>

  <div class="footer">
    ધોરણ ૮ ગુજરાતી સ્વાધ્યાયપોથી આધારિત ક્વિઝ | Made for Dipak
  </div>
</body>
</html>