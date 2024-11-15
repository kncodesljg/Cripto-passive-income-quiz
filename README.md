<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crypto Passive Income Quiz</title>
    <style>
        /* Global Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background-color: #f9f9f9;
            color: #333;
            padding: 1rem;
        }

        #quiz-container {
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            width: 100%;
            max-width: 500px;
            padding: 20px;
            text-align: center;
        }

        h1 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: #4CAF50;
        }

        .question {
            font-size: 1.2rem;
            margin-bottom: 20px;
        }

        .answer-options {
            list-style: none;
            padding: 0;
            margin-bottom: 20px;
        }

        .answer-options li {
            margin-bottom: 10px;
        }

        label {
            display: block;
            cursor: pointer;
            background: #f4f4f4;
            border: 1px solid #ccc;
            padding: 10px;
            border-radius: 5px;
            transition: background 0.3s;
        }

        label:hover {
            background: #e0e0e0;
        }

        input[type="radio"] {
            display: none;
        }

        input[type="radio"]:checked + label {
            background: #4CAF50;
            color: white;
            border-color: #4CAF50;
        }

        .btn {
            display: inline-block;
            padding: 10px 20px;
            background: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            visibility: hidden;
        }

        .btn:enabled {
            visibility: visible;
        }

        .btn:hover {
            background: #45a049;
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 1.5rem;
            }

            .question {
                font-size: 1rem;
            }

            .btn {
                font-size: 0.9rem;
            }
        }
    </style>
</head>
<body>

<div id="quiz-container">
    <h1>Crypto Passive Income Quiz</h1>
    <div id="question-container">
        <!-- Questions will be dynamically loaded here -->
    </div>
    <button id="next-btn" class="btn" disabled>Next</button>
</div>

<script>
    const questions = [
        {
            question: "What is your primary goal with cryptocurrency passive income?",
            options: ["Earn small daily rewards", "Achieve long-term wealth", "Diversify my investments"],
        },
        {
            question: "How much risk are you willing to take?",
            options: ["Low risk (e.g., staking)", "Moderate risk (e.g., lending)", "High risk (e.g., yield farming)"],
        },
        {
            question: "How much capital do you plan to invest initially?",
            options: ["Less than $500", "$500 - $5000", "More than $5000"],
        },
        {
            question: "How much time are you willing to dedicate to managing your investments?",
            options: ["A few minutes daily", "A few hours weekly", "Very little time (automated solutions)"],
        },
        {
            question: "Are you interested in learning about decentralized finance (DeFi)?",
            options: ["Yes, excited about DeFi", "No, I prefer simpler options", "Maybe, if it’s easy to understand"],
            lastQuestion: true,
        }
    ];

    let currentQuestionIndex = 0;

    function loadQuestion() {
        const questionContainer = document.getElementById("question-container");
        const questionData = questions[currentQuestionIndex];
        
        questionContainer.innerHTML = `
            <div class="question">${questionData.question}</div>
            <ul class="answer-options">
                ${questionData.options.map((option, index) => `
                    <li>
                        <input type="radio" id="option-${index}" name="answer" value="${option}">
                        <label for="option-${index}">${option}</label>
                    </li>
                `).join('')}
            </ul>
        `;

        // Add event listeners to options
        document.querySelectorAll('input[name="answer"]').forEach(input => {
            input.addEventListener('change', () => {
                const nextBtn = document.getElementById("next-btn");
                nextBtn.disabled = false;

                if (questionData.lastQuestion && input.value === "Yes, excited about DeFi") {
                    nextBtn.innerText = "Submit";
                    nextBtn.onclick = () => {
                        window.location.href = "https://www.digistore24.com/redir/363385/NimsaraGunawardhana07/";
                    };
                } else {
                    nextBtn.innerText = "Next";
                    nextBtn.onclick = nextQuestion;
                }
            });
        });
    }

    function nextQuestion() {
        const nextBtn = document.getElementById("next-btn");
        nextBtn.disabled = true;

        currentQuestionIndex++;
        if (currentQuestionIndex < questions.length) {
            loadQuestion();
        } else {
            document.getElementById("quiz-container").innerHTML = `
                <h1>Thank you for completing the quiz!</h1>
            `;
        }
    }

    loadQuestion();
</script>

</body>
</html>


