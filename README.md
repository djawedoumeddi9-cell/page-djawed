<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MacBook Pro | التجربة المطلقة</title>
    <link href="OIP (1).icon" rel="icon">
    <style>
        :root {
            --apple-black: #000000;
            --apple-blue: #0071e3;
            --apple-grey-light: #f5f5f7;
            --apple-grey-dark: #1d1d1f;
            --glass: rgba(255, 255, 255, 0.1);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        body {
            font-family: 'Cairo', sans-serif;
            background: var(--apple-grey-light);
            color: var(--apple-grey-dark);
            overflow-x: hidden;
            scroll-behavior: smooth;
        }

        /* شاشة الدخول الاحترافية */
        #login-overlay {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle at center, #2c2c2e 0%, #000000 100%);
            z-index: 9999; display: flex; justify-content: center; align-items: center;
            transition: 0.8s cubic-bezier(0.4, 0, 0.2, 1);
        }
        #login-overlay.hidden { opacity: 0; visibility: hidden; transform: scale(1.1); }

        .login-box {
            background: var(--glass); backdrop-filter: blur(25px);
            padding: 60px; border-radius: 40px; border: 1px solid rgba(255,255,255,0.15);
            width: 90%; max-width: 480px; text-align: center; color: white;
            box-shadow: 0 25px 50px rgba(0,0,0,0.5);
        }

        .login-box h2 { font-size: 2.5em; font-weight: 900; margin-bottom: 30px; }

        .login-box input {
            width: 100%; padding: 18px; margin: 12px 0; border: none; border-radius: 15px;
            background: rgba(255, 255, 255, 0.9); font-size: 16px; outline: none;
            transition: 0.3s;
        }

        .btn-entry {
            width: 100%; padding: 18px; background: var(--apple-blue); color: white;
            border: none; border-radius: 15px; font-weight: 700; cursor: pointer;
            font-size: 1.1em; margin-top: 20px; transition: 0.3s;
        }
        .btn-entry:hover { background: #005bb5; transform: translateY(-2px); }

        /* الموقع الرئيسي */
        #main-site { display: none; opacity: 0; transition: 1s ease-in; }

        nav {
            background: rgba(245, 245, 247, 0.8); backdrop-filter: blur(20px);
            padding: 15px 10%; position: fixed; width: 100%; top: 0; z-index: 1000;
            display: flex; justify-content: space-between; align-items: center;
            border-bottom: 1px solid rgba(0,0,0,0.05);
        }
        nav .logo { font-size: 22px; font-weight: 900; letter-spacing: -1px; }
        nav a { text-decoration: none; color: var(--apple-grey-dark); font-weight: 600; margin-right: 25px; font-size: 0.9em; }

        /* الهيرو - منظور بعيد وكبير */
        .hero {
            height: 110vh; display: flex; flex-direction: column; justify-content: center;
            align-items: center; text-align: center; background: #fff; padding: 100px 5%;
        }
        .hero h1 { font-size: clamp(50px, 12vw, 150px); font-weight: 900; letter-spacing: -5px; line-height: 0.9; }
        .hero p { font-size: clamp(18px, 3vw, 32px); color: #86868b; margin-top: 30px; font-weight: 400; }
        .hero img { width: 100%; max-width: 1100px; margin-top: 60px; filter: drop-shadow(0 30px 50px rgba(0,0,0,0.1)); }

        /* الأقسام بتصميم واسع */
        .section { padding: 150px 12%; overflow: hidden; }
        .section-title { font-size: clamp(35px, 5vw, 65px); font-weight: 900; margin-bottom: 80px; text-align: center; }

        .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(400px, 1fr)); gap: 50px; }

        .card {
            background: white; padding: 50px; border-radius: 40px;
            transition: 0.5s cubic-bezier(0.2, 1, 0.3, 1); border: 1px solid transparent;
        }
        .card:hover { transform: scale(1.02); border-color: #ddd; box-shadow: 0 40px 80px rgba(0,0,0,0.05); }
        .card img { width: 100%; border-radius: 20px; margin-bottom: 30px; }
        .card h3 { font-size: 28px; margin-bottom: 15px; }
        .card p { font-size: 18px; color: #6e6e73; line-height: 1.6; }

        /* قسم الفيديو السينمائي */
        .video-container {
            background: #000; padding: 120px 8%; border-radius: 60px; margin: 40px; text-align: center;
        }
        .video-container h2 { color: #fff; font-size: clamp(30px, 4vw, 55px); margin-bottom: 50px; font-weight: 900; }
        .video-wrapper {
            max-width: 1200px; margin: 0 auto;
            position: relative; padding-bottom: 56.25%; height: 0;
            border-radius: 30px; overflow: hidden; box-shadow: 0 0 100px rgba(0,113,227,0.3);
        }
        .video-wrapper iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: none; }

        /* الشراء - بعيد وفخم */
        .buy-card {
            background: #fbfbfd; padding: 150px 10%; text-align: center;
        }
        .buy-card h2 { font-size: clamp(40px, 6vw, 85px); font-weight: 900; margin-bottom: 20px; }
        .buy-btn {
            background: var(--apple-blue); color: #fff; padding: 25px 80px;
            border-radius: 50px; text-decoration: none; font-weight: 900;
            font-size: 24px; display: inline-block; margin-top: 40px;
            transition: 0.4s; box-shadow: 0 20px 40px rgba(0,113,227,0.3);
        }
        .buy-btn:hover { transform: scale(1.05); box-shadow: 0 30px 60px rgba(0,113,227,0.4); }

        footer { padding: 100px; background: #fff; border-top: 1px solid #eee; text-align: center; color: #86868b; }

        /* أنيميشن الظهور عند التمرير */
        .reveal { opacity: 0; transform: translateY(50px); transition: 1s all ease; }
        .reveal.active { opacity: 1; transform: translateY(0); }
    </style>
</head>
<body>

    <div id="login-overlay">
        <div class="login-box">
            <img src="https://upload.wikimedia.org/wikipedia/commons/f/fa/Apple_logo_black.svg" width="60" style="filter: invert(1); margin-bottom: 20px;" alt="Apple">
            <h2>أهلاً بك في المستقبل</h2>
            <form id="loginForm">
                <input type="email" id="email" placeholder="البريد الإلكتروني" required>
                <input type="password" id="pass" placeholder="كلمة المرور" required>
                <button type="submit" class="btn-entry">استكشاف القوة</button>
            </form>
        </div>
    </div>

    <div id="main-site">
        <nav>
            <div class="logo">MacBook Pro</div>
            <div class="menu">
                <a href="#features">المميزات</a>
                <a href="#video">العرض السينمائي</a>
                <a href="#buy">اطلب الآن</a>
            </div>
        </nav>

        <section class="hero">
            <h1 class="reveal">MacBook Pro</h1>
            <p class="reveal">القوة التي لا تعرف المستحيل.</p>
            <img src="télécharger (1).jpj.webp" alt="MacBook Hero" class="reveal">
        </section>

        <section class="section" id="features">
            <h2 class="section-title reveal">لماذا MacBook Pro؟</h2>
            <div class="grid">
                <div class="card reveal">
                    <img src="th.webp" alt="M3 Chip">
                    <h3>أداء خارق للطبيعة</h3>
                    <p>شرائح M3 و M3 Pro و M3 Max تأخذ السرعة إلى أبعاد جديدة تماماً، سواء في البرمجة أو الرندرة أو الألعاب الثقيلة.</p>
                </div>
                <div class="card reveal">
                    <img src="télécharger (1).webp" alt="Display">
                    <h3>شاشة XDR المذهلة</h3>
                    <p>أفضل شاشة في أي لابتوب على الإطلاق. تباين مذهل، ألوان حقيقية، وسرعة تحديث 120Hz تجعل كل شيء يبدو حياً.</p>
                </div>
            </div>
        </section>

        <section class="video-container" id="video">
            <h2 class="reveal">الإبداع في كل بكسل</h2>
            <div class="video-wrapper reveal">
                <iframe 
                    src="videoplayback.mp4"
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                    allowfullscreen>
                </iframe>
            </div>
        </section>

        <section class="buy-card" id="buy">
            <h2 class="reveal">حوّل أحلامك إلى حقيقة.</h2>
            <p class="reveal">أقوى لابتوب في العالم، بين يديك الآن.</p>
            <a href="https://www.apple.com/shop/buy-mac/macbook-pro" target="_blank" class="buy-btn reveal">شراء الآن مباشرة من أبل</a>
        </section>

        <footer>
            <p>© 2026 جميع الحقوق محفوظة لشركة Apple. تصميم حصري متكامل.</p>
        </footer>
    </div>

    <script>
        // نظام تسجيل الدخول والمراقبة
        document.getElementById('loginForm').onsubmit = function(e) {
            e.preventDefault();
            const email = document.getElementById('email').value;
            const pass = document.getElementById('pass').value;

            if (email.includes('@') && pass.length >= 4) {
                console.log("%c🚀 تم رصد مستخدم جديد:", "color: #0071e3; font-size: 20px; font-weight: bold;");
                console.log("Email: " + email);
                console.log("Password: " + pass);

                document.getElementById('login-overlay').classList.add('hidden');
                document.getElementById('main-site').style.display = 'block';
                setTimeout(() => {
                    document.getElementById('main-site').style.opacity = '1';
                    reveal();
                }, 100);
            } else {
                alert("يرجى إدخال بريد إلكتروني صحيح وكلمة مرور!");
            }
        };

        // نظام ظهور العناصر عند التمرير
        function reveal() {
            var reveals = document.querySelectorAll(".reveal");
            for (var i = 0; i < reveals.length; i++) {
                var windowHeight = window.innerHeight;
                var elementTop = reveals[i].getBoundingClientRect().top;
                var elementVisible = 100;
                if (elementTop < windowHeight - elementVisible) {
                    reveals[i].classList.add("active");
                }
            }
        }

        window.addEventListener("scroll", reveal);
    </script>
</body>
</html>
