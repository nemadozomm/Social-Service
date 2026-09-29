<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>My Website</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, Helvetica, sans-serif;
        }

        body {
            background: #0b0b0f;
            color: white;
            min-height: 100vh;
        }

        /* NAVBAR */

        nav {
            width: 100%;
            height: 70px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 7%;
            background: #111116;
            border-bottom: 1px solid #25252d;
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .logo {
            font-size: 25px;
            font-weight: bold;
            color: white;
            cursor: pointer;
        }

        .logo span {
            color: #8b5cf6;
        }

        .nav-buttons {
            display: flex;
            gap: 10px;
        }

        button {
            border: none;
            cursor: pointer;
            transition: 0.2s;
        }

        .login-btn,
        .register-btn {
            padding: 11px 20px;
            border-radius: 8px;
            font-size: 14px;
        }

        .login-btn {
            background: transparent;
            color: white;
            border: 1px solid #444;
        }

        .login-btn:hover {
            background: #222;
        }

        .register-btn {
            background: #8b5cf6;
            color: white;
        }

        .register-btn:hover {
            background: #7c3aed;
            transform: translateY(-1px);
        }

        /* HERO */

        .hero {
            min-height: calc(100vh - 70px);
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 40px 20px;
            background:
                radial-gradient(circle at top, rgba(139,92,246,0.25), transparent 35%),
                #0b0b0f;
        }

        .hero-content {
            max-width: 850px;
        }

        .badge {
            display: inline-block;
            background: rgba(139,92,246,0.12);
            border: 1px solid rgba(139,92,246,0.4);
            color: #b99cff;
            padding: 8px 14px;
            border-radius: 50px;
            margin-bottom: 25px;
            font-size: 13px;
        }

        h1 {
            font-size: clamp(45px, 8vw, 90px);
            line-height: 0.95;
            margin-bottom: 25px;
        }

        h1 span {
            color: #8b5cf6;
        }

        .hero p {
            color: #aaa;
            font-size: 18px;
            line-height: 1.6;
            max-width: 650px;
            margin: auto;
        }

        .hero-buttons {
            margin-top: 35px;
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
        }

        .main-btn {
            padding: 15px 28px;
            border-radius: 10px;
            background: #8b5cf6;
            color: white;
            font-size: 16px;
        }

        .main-btn:hover {
            background: #7c3aed;
            transform: translateY(-2px);
        }

        .secondary-btn {
            padding: 15px 28px;
            border-radius: 10px;
            background: transparent;
            color: white;
            border: 1px solid #444;
            font-size: 16px;
        }

        .secondary-btn:hover {
            background: #19191f;
        }

        /* FEATURES */

        .features {
            padding: 100px 7%;
            background: #0f0f14;
        }

        .section-title {
            text-align: center;
            font-size: 40px;
            margin-bottom: 50px;
        }

        .cards {
            max-width: 1100px;
            margin: auto;
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }

        .card {
            background: #15151c;
            border: 1px solid #282831;
            border-radius: 15px;
            padding: 30px;
            transition: 0.25s;
        }

        .card:hover {
            transform: translateY(-5px);
            border-color: #8b5cf6;
        }

        .card-icon {
            font-size: 35px;
            margin-bottom: 20px;
        }

        .card h3 {
            margin-bottom: 12px;
            font-size: 21px;
        }

        .card p {
            color: #999;
            line-height: 1.6;
        }

        /* MODAL */

        .modal {
            position: fixed;
            inset: 0;
            background: rgba(0,0,0,0.75);
            display: none;
            align-items: center;
            justify-content: center;
            padding: 20px;
            z-index: 2000;
        }

        .modal.active {
            display: flex;
        }

        .modal-box {
            width: 100%;
            max-width: 420px;
            background: #15151c;
            border: 1px solid #333;
            border-radius: 15px;
            padding: 30px;
            position: relative;
        }

        .close {
            position: absolute;
            right: 20px;
            top: 15px;
            font-size: 25px;
            color: #aaa;
            cursor: pointer;
        }

        .modal-box h2 {
            margin-bottom: 8px;
            font-size: 28px;
        }

        .modal-box p {
            color: #888;
            margin-bottom: 25px;
        }

        input {
            width: 100%;
            padding: 14px;
            margin-bottom: 15px;
            border-radius: 8px;
            border: 1px solid #333;
            background: #0d0d12;
            color: white;
            outline: none;
        }

        input:focus {
            border-color: #8b5cf6;
        }

        .submit-btn {
            width: 100%;
            padding: 14px;
            border-radius: 8px;
            background: #8b5cf6;
            color: white;
            font-size: 15px;
        }

        .submit-btn:hover {
            background: #7c3aed;
        }

        .switch {
            text-align: center;
            margin-top: 20px;
            color: #777;
            font-size: 14px;
        }

        .switch span {
            color: #a78bfa;
            cursor: pointer;
        }

        /* FOOTER */

        footer {
            padding: 30px 7%;
            text-align: center;
            border-top: 1px solid #25252d;
            color: #666;
        }

        /* USER AREA */

        .user-area {
            display: none;
            align-items: center;
            gap: 10px;
        }

        .user-area.active {
            display: flex;
        }

        .username {
            color: #aaa;
        }

        .logout {
            padding: 9px 15px;
            background: #222;
            color: white;
            border-radius: 7px;
        }

        /* MOBILE */

        @media (max-width: 750px) {

            nav {
                padding: 0 20px;
            }

            .cards {
                grid-template-columns: 1fr;
            }

            .nav-buttons {
                gap: 5px;
            }

            .login-btn,
            .register-btn {
                padding: 9px 12px;
            }

            .hero p {
                font-size: 16px;
            }
        }
    </style>
</head>

<body>

    <!-- NAVBAR -->

    <nav>

        <div class="logo" onclick="goHome()">
            My<span>Website</span>
        </div>

        <div class="nav-buttons" id="guestButtons">

            <button class="login-btn" onclick="openLogin()">
                Login
            </button>

            <button class="register-btn" onclick="openRegister()">
                Register
            </button>

        </div>

        <div class="user-area" id="userArea">

            <span class="username" id="usernameDisplay"></span>

            <button class="logout" onclick="logout()">
                Logout
            </button>

        </div>

    </nav>


    <!-- HERO -->

    <section class="hero" id="home">

        <div class="hero-content">

            <div class="badge">
                🚀 Welcome to my website
            </div>

            <h1>
                Build something<br>
                <span>amazing.</span>
            </h1>

            <p>
                A modern, responsive website that works on
                computers, phones and tablets.
            </p>

            <div class="hero-buttons">

                <button class="main-btn" onclick="openRegister()">
                    Get Started
                </button>

                <button class="secondary-btn" onclick="scrollToFeatures()">
                    Learn More
                </button>

            </div>

        </div>

    </section>


    <!-- FEATURES -->

    <section class="features" id="features">

        <h2 class="section-title">
            Features
        </h2>

        <div class="cards">

            <div class="card">

                <div class="card-icon">
                    ⚡
                </div>

                <h3>
                    Fast
                </h3>

                <p>
                    The website is lightweight and loads quickly
                    on desktop and mobile devices.
                </p>

            </div>


            <div class="card">

                <div class="card-icon">
                    🔒
                </div>

                <h3>
                    Simple
                </h3>

                <p>
                    Easy to use interface with Login and Register
                    functionality.
                </p>

            </div>


            <div class="card">

                <div class="card-icon">
                    🌍
                </div>

                <h3>
                    Worldwide
                </h3>

                <p>
                    Once uploaded to GitHub Pages, anyone with
                    the website link can access it.
                </p>

            </div>

        </div>

    </section>


    <!-- LOGIN MODAL -->

    <div class="modal" id="loginModal">

        <div class="modal-box">

            <div class="close" onclick="closeModals()">
                ×
            </div>

            <h2>
                Login
            </h2>

            <p>
                Sign in to your account
            </p>

            <input
                type="text"
                id="loginUsername"
                placeholder="Username"
            >

            <input
                type="password"
                id="loginPassword"
                placeholder="Password"
            >

            <button
                class="submit-btn"
                onclick="login()"
            >
                Login
            </button>

            <div class="switch">
                Don't have an account?
                <span onclick="switchToRegister()">
                    Register
                </span>
            </div>

        </div>

    </div>


    <!-- REGISTER MODAL -->

    <div class="modal" id="registerModal">

        <div class="modal-box">

            <div class="close" onclick="closeModals()">
                ×
            </div>

            <h2>
                Create account
            </h2>

            <p>
                Create your account below
            </p>

            <input
                type="text"
                id="registerUsername"
                placeholder="Username"
            >

            <input
                type="email"
                id="registerEmail"
                placeholder="Email"
            >

            <input
                type="password"
                id="registerPassword"
                placeholder="Password"
            >

            <button
                class="submit-btn"
                onclick="register()"
            >
                Create Account
            </button>

            <div class="switch">
                Already have an account?
                <span onclick="switchToLogin()">
                    Login
                </span>
            </div>

        </div>

    </div>


    <!-- FOOTER -->

    <footer>

        © 2026 MyWebsite. All rights reserved.

    </footer>


    <!-- JAVASCRIPT -->

    <script>

        function openLogin() {
            document
                .getElementById("loginModal")
                .classList.add("active");
        }


        function openRegister() {
            document
                .getElementById("registerModal")
                .classList.add("active");
        }


        function closeModals() {
            document
                .getElementById("loginModal")
                .classList.remove("active");

            document
                .getElementById("registerModal")
                .classList.remove("active");
        }


        function switchToRegister() {
            closeModals();
            openRegister();
        }


        function switchToLogin() {
            closeModals();
            openLogin();
        }


        function scrollToFeatures() {

            document
                .getElementById("features")
                .scrollIntoView({
                    behavior: "smooth"
                });

        }


        function goHome() {

            window.scrollTo({
                top: 0,
                behavior: "smooth"
            });

        }


        function register() {

            const username =
                document.getElementById("registerUsername").value;

            const email =
                document.getElementById("registerEmail").value;

            const password =
                document.getElementById("registerPassword").value;


            if (!username || !email || !password) {

                alert("Please fill in all fields.");

                return;
            }


            if (password.length < 6) {

                alert("Password must contain at least 6 characters.");

                return;
            }


            const user = {
                username: username,
                email: email,
                password: password
            };


            localStorage.setItem(
                "websiteUser",
                JSON.stringify(user)
            );


            alert("Account created successfully!");

            closeModals();

            showUser(username);

        }


        function login() {

            const username =
                document.getElementById("loginUsername").value;

            const password =
                document.getElementById("loginPassword").value;


            const savedUser =
                localStorage.getItem("websiteUser");


            if (!savedUser) {

                alert("No account found. Please register first.");

                return;
            }


            const user =
                JSON.parse(savedUser);


            if (
                username === user.username &&
                password === user.password
            ) {

                alert("Login successful!");

                closeModals();

                showUser(user.username);

            } else {

                alert("Incorrect username or password.");

            }

        }


        function showUser(username) {

            document
                .getElementById("guestButtons")
                .style.display = "none";

            document
                .getElementById("userArea")
                .classList.add("active");

            document
                .getElementById("usernameDisplay")
                .textContent =
                "Hello, " + username;

        }


        function logout() {

            document
                .getElementById("userArea")
                .classList.remove("active");

            document
                .getElementById("guestButtons")
                .style.display = "flex";

        }


        window.onclick = function(event) {

            if (
                event.target ===
                document.getElementById("loginModal") ||

                event.target ===
                document.getElementById("registerModal")
            ) {

                closeModals();

            }

        };


        // Check if user is already registered

        window.onload = function() {

            const savedUser =
                localStorage.getItem("websiteUser");

            if (savedUser) {

                const user =
                    JSON.parse(savedUser);

                showUser(user.username);

            }

        };

    </script>

</body>
</html>
