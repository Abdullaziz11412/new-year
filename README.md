<!DOCTYPE html>
<html lang="ar">
<head>
    <link rel="stylesheet" href="styles.css">
    <style>
        body, html {
            margin: 0;
            padding: 0;
            height: 100%;
            overflow: hidden; /* لمنع التمرير */
            font-family: Arial, sans-serif; /* استخدام خط بسيط */
        }

        #backgroundVideo {
            position: fixed;
            top: 0;            /* وضع الفيديو في الأعلى */
            left: 0;           /* وضع الفيديو إلى اليسار */
            width: 100%;      /* عرض الفيديو 100% */
            height: 100%;     /* طول الفيديو 100% */
            z-index: -1;      /* وضع الفيديو وراء المحتوى */
            object-fit: cover; /* يجعل الفيديو يغطي المنطقة المحددة بشكل جيد */
        }

        .container {
            position: relative; /* لجعل المحتوى فوق الفيديو */
            z-index: 1;
            max-width: 800px;
            margin: auto;
            padding: 20px;
            color: white; /* اجعل النص واضحًا على الخلفية */
        }

        .section {
            background-color: rgba(52, 73, 94, 0.8); /* لون خلفية القطعة مع شفافية */
            margin: 20px 0;
            padding: 15px;
            border-radius: 8px;
            cursor: pointer; /* تغيير شكل المؤشر عند المرور */
            transition: transform 0.3s; /* تأثير التحويل */
        }

        .section:hover {
            transform: scale(1.05); /* تكبير عند التمرير */
        }

        h1, h2 {
            text-align: center;
        }

        .link {
            display: block;
            text-align: center;
            margin-top: 20px;
            color: #3498db; /* لون الرابط */
            text-decoration: none;
        }

        .link:hover {
            text-decoration: underline; /* تأثير عند التمرير على الرابط */
        }

        .question-box {
            background-color: rgba(128, 128, 128, 0.5); /* لون رمادي شفاف */
            padding: 20px;
            border-radius: 8px;
            text-align: center; /* توسيط النص */
            margin: 20px 0;
        }

        .question-text {
            color: #ffffff; /* لون الكحلي */
            font-size: 1.5em; /* حجم الخط أكبر */
        }

        .hidden-text {
            display: none; /* إخفاء النص في البداية */
            margin-top: 10px;
            color: white; /* لون النص */
            transition: opacity 0.5s; /* تأثير انتقال */
        }

        /* أنماط نص رسالة الخطأ */
        #response {
            color: red;
            font-size: 1.5em; /* حجم الخط أكبر */
            text-align: center; /* توسيط النص */
            width: 100%; /* عرض كامل */
            margin-top: 20px; /* مساحة فوق النص */
        }
    </style>
</head>
<body>
    <video autoplay muted loop id="backgroundVideo">
        <source src="video.mp4" type="video/mp4">
        متصفحك لا يدعم فيديو HTML5.
    </video>
    
    <div class="container">
        <h1>Hello Ethar</h1>
        
        <div class="section" id="section1">
            <h2>I missed you</h2>
            <p class="hidden-text">I miss you always. I know you make me nervous, but I don't like to start the year without you because you are a beautiful person in my life.</p>
        </div>

        <div class="section" id="section2">
            <h2>You are a bastard</h2>
            <p class="hidden-text">You're a badass. Your behavior made me very angry the last time you spoke to me, but I forgive you.</p>
        </div>

        <div class="section" id="section3">
            <h2>Happy New Year to us</h2>
            <p class="hidden-text">Every year, we love each other very much, but there is one thing you have to answer. There is a question. If you answer it, a link will appear for you. Click on it. I miss you, and I hope we can go back to the same way as before after all of this, because I really missed you. Abdullaziz I love you very much.</p>
        </div>

        <div class="question-box">
            <h2 class="question-text">Question</h2>
            <p class="question-text">What year was I born?</p>
            <input type="text" id="yearInput" placeholder="Enter the year here">
            <button onclick="checkYear()">Send</button>
        </div>
        
        <p id="response"></p> <!-- سيتم عرض نص الخطأ هنا -->
        <a id="link" href="https://youtu.be/6eRqQImINlU?si=W8u8HrXwTlrO9YIM" class="link" style="display: none;">I love you, Ethar. Click here</a>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const sections = document.querySelectorAll('.section');
            sections.forEach(section => {
                section.addEventListener('click', () => {
                    const hiddenText = section.querySelector('.hidden-text');
                    hiddenText.style.display = hiddenText.style.display === 'block' ? 'none' : 'block';
                    hiddenText.style.opacity = hiddenText.style.opacity === '1' ? '0' : '1'; // تأثير الانتقال
                });
            });
        });

        function checkYear() {
            const yearInput = document.getElementById('yearInput').value;
            const response = document.getElementById('response');
            const link = document.getElementById('link');
            
            if (yearInput === '2001') {
                response.textContent = ''; // مسح أي رسالة سابقة
                link.style.display = 'block'; // إظهار الرابط
            } else {
                response.textContent = 'افااا ياحمارة';
                link.style.display = 'none'; // إخفاء الرابط
            }
        }
    </script>
</body>
</html>
