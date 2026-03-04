<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مشروع أمان ورحمة الرقمي</title>
    <style>
        :root {
            --primary-color: #2c3e50;
            --safety-blue: #3498db;
            --mercy-green: #27ae60;
            --light-bg: #f4f7f6;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--light-bg);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
        }

        .container {
            background: white;
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            width: 90%;
            max-width: 500px;
            text-align: center;
        }

        h1 {
            color: var(--primary-color);
            margin-bottom: 0.5rem;
        }

        p.subtitle {
            color: #7f8c8d;
            margin-bottom: 2rem;
        }

        textarea {
            width: 100%;
            height: 120px;
            padding: 15px;
            border: 2px solid #ddd;
            border-radius: 10px;
            resize: none;
            font-size: 16px;
            box-sizing: border-box;
            margin-bottom: 1rem;
            transition: border-color 0.3s;
        }

        textarea:focus {
            border-color: var(--safety-blue);
            outline: none;
        }

        button {
            background-color: var(--mercy-green);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 25px;
            font-size: 18px;
            cursor: pointer;
            transition: transform 0.2s, background 0.3s;
        }

        button:hover {
            background-color: #219150;
            transform: scale(1.05);
        }

        #result-box {
            margin-top: 2rem;
            padding: 15px;
            border-radius: 10px;
            display: none;
            animation: fadeIn 0.5s ease;
        }

        .safety-theme { background-color: #ebf5fb; border-right: 5px solid var(--safety-blue); }
        .mercy-theme { background-color: #e9f7ef; border-right: 5px solid var(--mercy-green); }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>

<div class="container">
    <h1>بـوصـلة الأمـان والـرحمة</h1>
    <p class="subtitle">اكتب ما تشعر به أو موقفاً تمر به، ودع القيم ترشدك..</p>
    
    <textarea id="userInput" placeholder="مثلاً: أشعر بالخوف، أريد مساعدة شخص، كيف أتعامل مع الغضب؟"></textarea>
    
    <button onclick="analyzeSpirit()">تحليل الموقف</button>

    <div id="result-box">
        <strong id="resultTitle"></strong>
        <p id="resultText"></p>
    </div>
</div>

<script>
    function analyzeSpirit() {
        const input = document.getElementById('userInput').value;
        const resultBox = document.getElementById('result-box');
        const resultTitle = document.getElementById('resultTitle');
        const resultText = document.getElementById('resultText');

        if (input.trim() === "") {
            alert("من فضلك اكتب شيئاً أولاً!");
            return;
        }

        // منطق التحليل البسيط
        let title = "رسالة أمان ورحمة";
        let message = "جميل أنك تشاركنا خواطرك. تذكر أن الرحمة تبدأ بالرفق بنفسك، والأمان يبدأ بكلمة طيبة تنشرها لمن حولك.";
        let theme = "mercy-theme";

        if (input.includes("خوف") || input.includes("قلق") || input.includes("أمان")) {
            title = "نحو الأمان والطمأنينة";
            message = "لا تقلق، الأمان هو أساس السكينة. 'الذي أطعمهم من جوع وآمنهم من خوف'. ابحث عن الهدوء في ذكر الله ومساندة من تحب.";
            theme = "safety-theme";
        } 
        else if (input.includes("غضب") || input.includes("مشكلة") || input.includes("اعتذار")) {
            title = "منهج الرحمة";
            message = "الرحمة تسبق الغضب. تذكر أن النبي ﷺ كان أرحم الناس عند المقدرة. تنفس بعمق، فالعفو أقوى من الانتقام.";
            theme = "mercy-theme";
        }
        else if (input.includes("مساعدة") || input.includes("خير") || input.includes("فقير")) {
            title = "أنت صانع الرحمة";
            message = "ما أجمل هذا الشعور! 'ارحموا من في الأرض يرحمكم من في السماء'. عملك البسيط قد يكون أماناً لشخص آخر.";
            theme = "mercy-theme";
        }

        // عرض النتيجة
        resultBox.style.display = "block";
        resultBox.className = "result-box " + theme;
        resultTitle.innerText = title;
        resultText.innerText = message;
    }
</script>

</body>
</html>
