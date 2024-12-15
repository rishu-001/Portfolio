<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Creative Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600&family=Zilla+Slab:wght@400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #3498db;
            --secondary-color: #2ecc71;
            --accent-color: #e74c3c;
            --background-color: #f0f4f8;
            --text-color: #2c3e50;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background-color: var(--background-color);
            color: var(--text-color);
            line-height: 1.6;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Navigation Bar */
        nav {
            background-color: rgb(15, 233, 179);
            padding: 10px 0;
            position: sticky;
            top: 0;
            z-index: 10;
        }

        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
        }

        nav ul li {
            margin: 0 20px;
        }

        nav ul li a {
            text-decoration: none;
            color: white;
            font-weight: bold;
            font-size: 1.2em;
            text-transform: uppercase;
            padding: 8px 16px;
            border-radius: 30px;
            transition: background-color 0.3s ease;
        }

        nav ul li a:hover {
            background-color: var(--secondary-color);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        header {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            text-align: center;
            padding: 60px 20px;
            position: relative;
            overflow: hidden;
            clip-path: polygon(0 0, 100% 0, 100% 85%, 0 100%);
        }

        .profile-wrapper {
            display: flex;
            flex-direction: column;
            align-items: center;
            position: relative;
        }

        .profile-image {
            width: 250px;
            height: 250px;
            border-radius: 50%;
            border: 7px solid white;
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
            transition: transform 0.4s ease;
        }

        .profile-image:hover {
            transform: scale(1.05) rotate(3deg);
        }

        .dynamic-background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(52,152,219,0.5), rgba(46,204,113,0.5));
            z-index: -1;
            animation: backgroundShift 10s ease infinite alternate;
        }

        @keyframes backgroundShift {
            0% {
                transform: rotate(0deg) scale(1);
            }
            100% {
                transform: rotate(10deg) scale(1.1);
            }
        }

        header h1 {
            font-family: 'Zilla Slab', serif;
            font-size: 3.5em;
            margin-top: 20px;
            text-shadow: 3px 3px 6px rgba(0,0,0,0.3);
        }

        header p {
            font-size: 1.2em;
            opacity: 0.9;
            margin-top: 10px;
        }

        .section {
            background: white;
            margin-top: 30px;
            border-radius: 15px;
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
            padding: 35px;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 5px;
            height: 100%;
            background: linear-gradient(var(--primary-color), var(--secondary-color));
        }

        .section:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }

        .section h2 {
            color: var(--primary-color);
            font-family: 'Zilla Slab', serif;
            border-bottom: 3px solid var(--accent-color);
            padding-bottom: 10px;
            margin-bottom: 20px;
        }

        .project {
            background-color: #f9f9ff;
            border-left: 5px solid var(--secondary-color);
            padding: 20px;
            margin-bottom: 20px;
            border-radius: 5px;
            transition: all 0.3s ease;
        }

        .project:hover {
            transform: translateX(10px);
            background-color: #f0f0ff;
        }

        .project h3 {
            color: var(--primary-color);
            margin-bottom: 10px;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
        }

        .contact-links a {
            text-decoration: none;
            color: white;
            padding: 12px 25px;
            border-radius: 30px;
            transition: all 0.3s ease;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            text-transform: uppercase;
            font-weight: 600;
            letter-spacing: 1px;
        }

        .contact-links a:hover {
            transform: scale(1.1) translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }

        footer {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            text-align: center;
            padding: 25px;
            margin-top: 30px;
        }

        @media (max-width: 768px) {
            header h1 {
                font-size: 2.5em;
            }
            .profile-image {
                width: 200px;
                height: 200px;
            }
            .contact-links {
                flex-direction: column;
                align-items: center;
            }
            .contact-links a {
                width: 200px;
                text-align: center;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation Bar -->
    <nav>
        <ul>
            <li><a href="#about">About</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <header>
        <div class="dynamic-background"></div>
        <div class="container">
            <div class="profile-wrapper">
                <!-- Replace this image src with your own image path -->
                <img src="Screenshot 2024-12-15 005223.png" alt="Your Profile Picture" class="profile-image" >
                <h1>Rishu Pandey</h1>
                <p>Innovative Web Developer | Creative Problem Solver | Tech Enthusiast</p>
            </div>
        </div>
    </header>

    <div class="container">
        <section class="section" id="about">
            <h2>About Me</h2>
            <p>I'm a passionate tech innovator who believes in the power of creative thinking and cutting-edge technology. My journey is about transforming complex challenges into elegant, user-centric solutions that make a real difference.</p>
        </section>

        <section class="section" id="education">
            <h2>Education</h2>
            <p>
                <strong>KIET Group of Institutions</strong><br>
                Bachelor of Technology in Computer Science<br>
                Expected Graduation: 2028<br>
            </p>
        </section>

        <section class="section" id="projects">
            <h2>Featured Projects</h2>
            <div class="project">
                <h3>Basic Calculator</h3>
                <p>Designed a simple funtional Calculator using C programming Language. It allows user to perform basic arithmetric Operations.</p>
            </div>
            <div class="project">
                <h3>Spotify Clone</h3>
                <p>Created an online clone for spotify using HTML & CSS.</p>
            </div>
        </section>

        <section class="section" id="skills">
            <h2>Skills</h2>
            <div class="project">
                <h3><ul>HTML</ul><ul>CSS</ul><ul>JAVASCRIPT</ul></h3>
            </div>
            <div class="project">
                <h3><ul>C</ul><ul>C++</ul><ul>PYTHON</ul></h3>
            </div>
        </section>

        <section class="section" id="contact">
            <h2>Connect With Me</h2>
            <div class="contact-links">
                <a href="https://www.instagram.com/_rishu_pandey__01/profilecard/?igsh=OG0zYWtycHhxd2I1" target="_blank">Instagram</a>
                <a href="https://www.linkedin.com/in/rishu-pandey-b46557328?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app" target="_blank">LinkedIn</a>
                <a href="https://github.com/rishu-001" target="_blank">GitHub</a>
            </div>
        </section>
    </div>

    <footer>
        <p>© 2024 Rishu Pandey | Crafted with Innovation & Passion</p>
    </footer>
</body>
</html>
