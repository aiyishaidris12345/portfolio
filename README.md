<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Aiyisha Idris | CSE Student at VIT Chennai</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" rel="stylesheet">
    <style>
        :root {
            --gradient-start: #6a11cb;
            --gradient-end: #2575fc;
            --text-color: #e0f7fa;
            --card-background: rgba(255, 255, 255, 0.1);
            --navbar-bg: rgba(30, 144, 255, 0.8);
            --hover-bg: rgba(255, 255, 255, 0.2);
            --button-hover-bg: #ff7f50;
            --button-text-color: #fff;
            --accent-color: #ff6b6b;
            --shadow-color: rgba(0, 0, 0, 0.3);
            
            /* Theme toggle variables */
            --light-gradient-start: #74ebd5;
            --light-gradient-end: #ACB6E5;
            --light-text-color: #333;
            --light-card-bg: rgba(255, 255, 255, 0.8);
            --light-accent: #ff6b6b;
            --light-navbar: rgba(255, 255, 255, 0.9);
        }

        /* Dark Theme (default) */
        body.dark-theme {
            background: linear-gradient(45deg, var(--gradient-start), var(--gradient-end));
            color: var(--text-color);
        }

        /* Light Theme */
        body.light-theme {
            background: linear-gradient(45deg, var(--light-gradient-start), var(--light-gradient-end));
            color: var(--light-text-color);
        }

        body.light-theme .navbar {
            background: var(--light-navbar);
        }

        body.light-theme .navbar a {
            color: #333;
        }

        body.light-theme .certificate-card,
        body.light-theme .blog-card,
        body.light-theme .project-card,
        body.light-theme .testimonial-card {
            background: rgba(255, 255, 255, 0.5);
            color: #333;
        }

        body.light-theme h1, 
        body.light-theme h2, 
        body.light-theme h3 {
            color: #333;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
        }

        body.light-theme .profile-container,
        body.light-theme .skills-section,
        body.light-theme .certificates-section,
        body.light-theme .blog-section,
        body.light-theme .about-me-box,
        body.light-theme .projects-section,
        body.light-theme .testimonials-section {
            background: var(--light-card-bg);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
        }

        body.light-theme .skill label {
            color: #333;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Poppins', sans-serif;
            overflow-x: hidden;
            transition: background 0.5s ease;
            background-size: 400% 400%;
            animation: gradient-animation 10s ease infinite;
        }

        .glowing-text {
            font-size: 2rem;
            color: white;
            text-shadow: 0px 0px 10px var(--accent-color), 
                         0px 0px 20px var(--accent-color), 
                         0px 0px 30px var(--accent-color);
        }

        @keyframes gradient-animation {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        @keyframes slide-in {
            from {
                transform: translateX(-100%);
                opacity: 0;
            }
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        .moving-text {
            font-size: 1.5rem;
            animation: slide-in 3s ease-in-out infinite alternate;
        }

        .hero h1:hover {
            color: var(--accent-color);
            transform: scale(1.2);
            transition: transform 0.3s ease, color 0.3s ease;
        }

        .navbar {
            position: fixed;
            width: 100%;
            background: var(--navbar-bg);
            display: flex;
            justify-content: space-around;
            padding: 15px;
            z-index: 1000;
            backdrop-filter: blur(10px);
            border-bottom: 2px solid rgba(255, 255, 255, 0.1);
        }

        .navbar a {
            color: var(--text-color);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            position: relative;
            font-size: 1.1rem;
            padding: 8px 15px;
            border-radius: 5px;
        }

        .navbar a:hover {
            background: var(--hover-bg);
            color: #fff;
            transform: scale(1.1);
        }

        .navbar a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 3px;
            bottom: -5px;
            left: 0;
            background-color: var(--accent-color);
            transition: width 0.5s;
        }

        .navbar a:hover::after {
            width: 100%;
        }

        .hero {
            display: flex;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            padding: 50px;
            text-align: center;
            flex-direction: column;
            position: relative;
        }

        .profile-container {
            display: flex;
            align-items: center;
            background: var(--card-background);
            padding: 60px;
            border-radius: 20px;
            box-shadow: 0 15px 35px var(--shadow-color);
            backdrop-filter: blur(10px);
            margin-top: 80px;
        }

        .profile-image {
            width: 300px;
            height: 300px;
            border-radius: 50%;
            object-fit: cover;
            border: 6px solid var(--text-color);
            margin-right: 40px;
            box-shadow: 0 8px 15px var(--shadow-color);
        }

        .contact-section {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 70vh;
            text-align: center;
            flex-direction: column;
            padding: 20px;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }

        .contact-links a {
            color: var(--text-color);
            text-decoration: none;
            font-size: 24px;
            transition: transform 0.3s ease;
            padding: 12px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            width: 60px;
            height: 60px;
        }

        .contact-links a:hover {
            transform: scale(1.2);
            background: var(--button-hover-bg);
        }

        .certificates-section,
        .skills-section,
        .testimonials-section {
            max-width: 1100px;
            margin: 50px auto;
            padding: 40px;
            background: var(--card-background);
            border-radius: 15px;
            box-shadow: 0 4px 10px var(--shadow-color);
            backdrop-filter: blur(10px);
        }

        .certificates-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
            margin-top: 20px;
        }

        .certificate-card {
            background: rgba(255, 255, 255, 0.05);
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            width: 300px;
            box-shadow: 0 4px 6px var(--shadow-color);
            transition: transform 0.3s ease;
        }

        .certificate-card:hover {
            transform: scale(1.05);
        }

        .certificate-card img {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-radius: 8px;
        }

        .certificate-card h3 {
            font-size: 1.2rem;
            margin: 10px 0;
            color: #fff;
        }

        .certificate-card p {
            font-size: 0.9rem;
            color: #ddd;
            padding: 0 10px 10px;
        }

        .certificate-card a {
            display: inline-block;
            margin: 10px 0;
            padding: 10px 20px;
            background: var(--accent-color);
            color: var(--button-text-color);
            text-decoration: none;
            font-weight: bold;
            border-radius: 5px;
            transition: background 0.3s ease;
        }

        .certificate-card a:hover {
            background: #e0554a;
        }

        h1, h2 {
            color: #fff;
            text-shadow: 2px 2px 4px var(--shadow-color);
            margin-bottom: 20px;
        }

        .testimonials-section {
            padding: 70px;
            background: var(--card-background);
            border-radius: 15px;
            box-shadow: 0 15px 35px var(--shadow-color);
            backdrop-filter: blur(10px);
            max-width: 1100px;
            margin: 50px auto;
        }

        .testimonials-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            justify-items: center;
        }

        .testimonial-card {
            background: rgba(255, 255, 255, 0.05);
            padding: 25px;
            border-radius: 10px;
            text-align: center;
            width: 100%;
            box-shadow: 0 4px 6px var(--shadow-color);
            transition: transform 0.3s ease;
            position: relative;
        }

        .testimonial-card:hover {
            transform: scale(1.05);
        }

        .testimonial-card h3 {
            font-size: 1.5rem;
            color: #fff;
            margin-bottom: 10px;
        }

        .testimonial-card p {
            color: #ddd;
            margin: 10px 0;
            font-style: italic;
        }

        .testimonial-card .quote-icon {
            position: absolute;
            top: 20px;
            left: 20px;
            opacity: 0.2;
            font-size: 24px;
            color: var(--accent-color);
        }

        .testimonial-card .author {
            font-weight: bold;
            margin-top: 15px;
        }

        .testimonial-card .company {
            font-size: 0.9rem;
            opacity: 0.8;
        }

        .blog-section {
            padding: 70px;
            background: var(--card-background);
            border-radius: 15px;
            box-shadow: 0 15px 35px var(--shadow-color);
            margin: 50px auto;
            backdrop-filter: blur(10px);
            max-width: 1100px;
        }

        .blog-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            justify-items: center;
        }

        .blog-card {
            background: rgba(255, 255, 255, 0.05);
            padding: 25px;
            border-radius: 10px;
            text-align: center;
            width: 100%;
            box-shadow: 0 4px 6px var(--shadow-color);
            transition: transform 0.3s ease;
        }

        .blog-card:hover {
            transform: scale(1.05);
        }

        .blog-card h3 {
            font-size: 1.5rem;
            color: #fff;
            margin-bottom: 10px;
        }

        .blog-card p {
            color: #ddd;
            margin-bottom: 15px;
        }

        .blog-card a {
            color: var(--accent-color);
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s ease;
        }

        .blog-card a:hover {
            color: #e0554a;
        }

        .skill {
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .skill label {
            font-size: 1.1rem;
            color: var(--text-color);
            flex: 1;
        }

        .skill-bar-container {
            flex: 2;
            height: 20px;
            background-color: rgba(255, 255, 255, 0.3);
            border-radius: 10px;
            position: relative;
        }

        .skill-bar {
            height: 100%;
            border-radius: 10px;
            background: linear-gradient(to right, var(--accent-color), #ff9e64);
            position: relative;
            transition: width 1s ease;
        }

        .skill-percentage {
            position: absolute;
            right: 10px;
            top: 50%;
            transform: translateY(-50%);
            color: white;
            font-weight: bold;
            font-size: 0.9rem;
        }

        .projects-section {
            max-width: 1100px;
            margin: 50px auto;
            padding: 50px;
            background: var(--card-background);
            border-radius: 15px;
            box-shadow: 0 15px 35px var(--shadow-color);
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
            width: 100%;
            margin-top: 20px;
        }
        
        .project-card {
            background: rgba(255, 255, 255, 0.05);
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 4px 6px var(--shadow-color);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            color: white;
            cursor: pointer;
            height: 150px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .project-card:hover{
            transform: translateY(-10px);
            box-shadow: 0 15px 20px var(--shadow-color);
        }
        
        .about-me-box{
            background: var(--card-background);
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 4px 6px var(--shadow-color);
            max-width: 800px;
            margin: 0 auto;
        }

        .project-modal {
            display: none;
            position: fixed;
            z-index: 1001;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0, 0, 0, 0.7);
        }

        .project-modal-content {
            background: linear-gradient(135deg, #2c3e50, #34495e);
            color: white;
            margin: 10% auto;
            padding: 30px;
            border: 1px solid #888;
            width: 80%;
            max-width: 700px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            position: relative;
            animation: modalFadeIn 0.4s;
        }

        @keyframes modalFadeIn {
            from {opacity: 0; transform: translateY(-50px);}
            to {opacity: 1; transform: translateY(0);}
        }

        .project-modal-content h2 {
            color: #fff;
            margin-bottom: 20px;
            text-shadow: 1px 1px 3px rgba(0,0,0,0.3);
        }

        .project-modal-content p {
            color: #ddd;
            margin-bottom: 15px;
            line-height: 1.6;
        }

        .project-modal-content .close {
            position: absolute;
            top: 20px;
            right: 25px;
            color: #fff;
            font-size: 32px;
            font-weight: bold;
            transition: color 0.3s;
        }

        .project-modal-content .close:hover {
            color: var(--accent-color);
            text-decoration: none;
            cursor: pointer;
        }

        #contact-form {
            max-width: 500px;
            width: 100%;
            margin: 0 auto 30px;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        #contact-form input,
        #contact-form textarea {
            width: 100%;
            padding: 15px;
            border: none;
            border-radius: 8px;
            font-family: 'Poppins', sans-serif;
            background: rgba(255, 255, 255, 0.1);
            color: white;
            transition: all 0.3s ease;
        }
        
        #contact-form input:focus,
        #contact-form textarea:focus {
            outline: none;
            box-shadow: 0 0 10px var(--accent-color);
            background: rgba(255, 255, 255, 0.2);
        }
        
        body.light-theme #contact-form input,
        body.light-theme #contact-form textarea {
            background: rgba(255, 255, 255, 0.8);
            color: #333;
        }
        
        #contact-form textarea {
            min-height: 150px;
            resize: vertical;
        }
        
        #contact-form button {
            background: linear-gradient(45deg, var(--accent-color), #ff9a8b);
            color: white;
            border: none;
            padding: 15px 30px;
            border-radius: 30px;
            cursor: pointer;
            font-family: 'Poppins', sans-serif;
            font-weight: 600;
            font-size: 1rem;
            transition: all 0.3s;
            box-shadow: 0 4px 10px rgba(255, 107, 107, 0.4);
        }
        
        #contact-form button:hover {
            transform: translateY(-5px);
            box-shadow: 0 7px 15px rgba(255, 107, 107, 0.6);
        }
        
        #form-status {
            margin-top: 15px;
            font-weight: bold;
        }

        /* Theme Toggle Styles */
        .theme-toggle {
            position: fixed;
            top: 100px;
            right: 30px;
            z-index: 1000;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .theme-toggle p {
            margin-bottom: 10px;
            font-weight: 600;
            color: white;
            text-shadow: 1px 1px 3px rgba(0,0,0,0.3);
        }

        .toggle-switch {
            position: relative;
            width: 80px;
            height: 40px;
            background: linear-gradient(to right, #30cfd0, #330867);
            border-radius: 30px;
            padding: 5px;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            transition: all 0.3s ease;
        }

        .toggle-switch::before {
            content: "";
            position: absolute;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            top: 5px;
            left: 5px;
            background: white;
            transition: transform 0.3s ease, background 0.3s ease;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }

        .toggle-icons {
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 10px;
            box-sizing: border-box;
        }

        .toggle-icons i {
            color: white;
            font-size: 14px;
            z-index: 1;
        }

        .theme-toggle input {
            display: none;
        }

        .theme-toggle input:checked + .toggle-switch::before {
            transform: translateX(40px);
            background: #ffdb58;
        }

        .theme-toggle input:checked + .toggle-switch {
            background: linear-gradient(to right, #ff7e5f, #feb47b);
        }

        canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.5;
            pointer-events: none;
        }

        section {
            position: relative;
        }

        @media (max-width: 992px) {
            .profile-container {
                flex-direction: column;
                padding: 30px;
            }
            
            .profile-image {
                margin-right: 0;
                margin-bottom: 20px;
                width: 200px;
                height: 200px;
            }
            
            .testimonials-section,
            .blog-section,
            .projects-section {
                padding: 40px 20px;
            }
            
            .navbar {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .navbar a {
                margin: 5px;
                font-size: 0.9rem;
            }
            
            .skill {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .skill-bar-container {
                width: 100%;
                margin-top: 10px;
            }
            
            .theme-toggle {
                top: 170px;
                right: 10px;
            }
        }

        @media (max-width: 576px) {
            .hero {
                padding: 30px 15px;
            }
            
            .certificates-section,
            .skills-section,
            .testimonials-section {
                padding: 20px;
            }
            
            .project-modal-content {
                width: 95%;
                margin: 20% auto;
                padding: 20px;
            }
        }
        
        /* Animation for the moving particles */
        @keyframes floatAnimation {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
    </style>
</head>
<body class="dark-theme">

    <nav class="navbar">
        <a href="#home">Home</a>
        <a href="#about">About Me</a>
        <a href="#skills">Skills</a>
        <a href="#certificates">Certificates</a>
        <a href="#projects">Projects</a>
        <a href="#testimonials">Testimonials</a>
        <a href="#blog">Blog</a>
        <a href="#contact">Contact</a>
    </nav>
    
    <!-- Theme Toggle Button -->
    <div class="theme-toggle">
        <p>Theme</p>
        <input type="checkbox" id="theme-toggle">
        <label for="theme-toggle" class="toggle-switch">
            <div class="toggle-icons">
                <i class="fas fa-moon"></i>
                <i class="fas fa-sun"></i>
            </div>
        </label>
    </div>
   
    

    <section id="home" class="hero">
        
        <div class="profile-container">
            
            <img src="C:\Users\lenovo\Desktop\aiyishaphoto.jpeg" alt="Aiyisha Idris" class="profile-image">
            <div>
                <h1 class="glowing-text">Aiyisha Idris</h1>
                <p class="moving-text">Transforming complex challenges into elegant digital solutions</p>
                <p>Computer Coder | Technology Innovator | Creative Problem Solver</p>
                <p>Hi, I'm Aiyisha Idris, a CSE student at VIT Chennai passionate about technology and innovation.</p>
            <!-- Read Aloud Button -->
            <button id="readAloudButton" style="padding: 10px 20px; font-size: 1rem; background-color: var(--accent-color); color: white; border: none; border-radius: 5px; cursor: pointer;">
                Read Aloud
            </button>
            
            </div>
            <div id="additionalDescription" style="display: none; margin-top: 30px; text-align: center;">
                <h2>About Me</h2>
                <p>
                    I am a curious and driven individual with a deep interest in software development, artificial intelligence, and problem-solving. 
                    At VIT Chennai, I have honed my skills in programming, teamwork, and leadership. My goal is to contribute to impactful projects 
                    that push the boundaries of technology while empowering communities. I also enjoy exploring creative pursuits like writing blogs 
                    and mentoring peers.
                </p>
            </div>
            
        
            
        </div>
    </section>

    <section id="about" class="hero">
        <div class="about-me-box">
            <h1><u>About Me</u></h1>
            <p>I'm a passionate second-year B.Tech CSE AIML student at Vellore Institute Of Technology Chennai, driven by the desire to innovate and excel in the realm of technology. My focus lies in coding and web design, where I strive to create impactful digital experiences. My career aspiration is to join a leading MNC, leveraging my skills to contribute to cutting-edge projects and continuously grow as a software developer. I am committed to exploring new technologies and applying them to solve real-world problems.</p>
        </div>
    </section>

    <section id="skills" class="skills-section">
        <h2>Skills</h2>
        <div class="skill">
            <label for="web-programming">Web Programming</label>
            <div class="skill-bar-container">
                <div class="skill-bar" style="width: 80%">
                    <span class="skill-percentage">80%</span>
                </div>
            </div>
        </div>
        <div class="skill">
            <label for="machine-learning">Machine Learning</label>
            <div class="skill-bar-container">
                <div class="skill-bar" style="width: 70%">
                    <span class="skill-percentage">70%</span>
                </div>
            </div>
        </div>
        <div class="skill">
            <label for="javascript">Javascript</label>
            <div class="skill-bar-container">
                <div class="skill-bar" style="width: 85%">
                    <span class="skill-percentage">85%</span>
                </div>
            </div>
        </div>
        <div class="skill">
            <label for="artificial-intelligence">Artificial Intelligence</label>
            <div class="skill-bar-container">
                <div class="skill-bar" style="width: 75%">
                    <span class="skill-percentage">75%</span>
                </div>
            </div>
        </div>
        <div class="skill">
            <label for="java">Java</label>
            <div class="skill-bar-container">
                <div class="skill-bar" style="width: 65%">
                    <span class="skill-percentage">65%</span>
                </div>
            </div>
        </div>
        <div class="skill">
            <label for="python">Python</label>
            <div class="skill-bar-container">
                <div class="skill-bar" style="width: 90%">
                    <span class="skill-percentage">90%</span>
                </div>
            </div>
        </div>
        <div class="skill">
            <label for="c-cpp">C and C++</label>
            <div class="skill-bar-container">
                <div class="skill-bar" style="width: 80%">
                    <span class="skill-percentage">80%</span>
                </div>
            </div>
        </div>
    </section>
    
    <section class="certificates-section" id="certificates">
        <h2>Certificates</h2>
        <div class="certificates-container">
            <div class="certificate-card">
                <img src="C:\Users\lenovo\Desktop\c1.png" alt="Certificate 1">
                <h3>Web Development</h3>
                <p>Issued by NCERT Institute</p>
                <a href="#" onclick="showCertificate(this)">View Certificate</a>
            </div>
            <div class="certificate-card">
                <img src="C:\Users\lenovo\Desktop\a3.webp" alt="Certificate 2">
                <h3>UI/UX Design</h3>
                <p>Issued by MIT University</p>
                <a href="#" onclick="showCertificate(this)">View Certificate</a>
            </div>
            <div class="certificate-card">
                <img src="C:\Users\lenovo\Desktop\a4.webp" alt="Certificate 3">
                <h3>Python Coding</h3>
                <p>Issued by DEVTools University</p>
                <a href="#" onclick="showCertificate(this)">View Certificate</a>
            </div>
        </div>
    </section>
    
    <section id="projects" class="projects-section">
        <h2>Projects</h2>
        <div class="projects-grid">
            <div class="project-card" onclick="openProject('project1')">AI Recommendation System</div>
            <div class="project-card" onclick="openProject('project2')">Keyword Detection using AI Tools</div>
            <div class="project-card" onclick="openProject('project4')">Crowd Management during festivals</div>
            <div class="project-card" onclick="openProject('project5')">Real-time Anomaly Detection</div>
            <div class="project-card" onclick="openProject('project6')">Hospital Management System</div>
        </div>
    </section>

    <!-- Project Modals -->
    <div id="project1Modal" class="project-modal">
        <div class="project-modal-content">
            <span class="close" onclick="closeModal('project1Modal')">&times;</span>
            <h2>AI Recommendation System</h2>
            <p>Developed an AI-powered recommendation system that suggests products based on user behavior and preferences. The system uses machine learning algorithms to analyze user data and provide personalized recommendations in real-time.</p>
            <p>Technologies used: Python, TensorFlow, SQL, Flask</p>
        </div>
    </div>

    <div id="project2Modal" class="project-modal">
        <div class="project-modal-content">
            <span class="close" onclick="closeModal('project2Modal')">&times;</span>
            <h2>Keyword Detection using AI Tools</h2>
            <p>Created a natural language processing tool that identifies and extracts keywords from large text documents. This system helps in summarizing content and identifying key topics and trends within textual data.</p>
            <p>Technologies used: Python, NLTK, spaCy, Flask</p>
        </div>
    </div>

    <div id="project3Modal" class="project-modal">
        <div class="project-modal-content">
            <span class="close" onclick="closeModal('project3Modal')">&times;</span>
            <h2>Emotion And Tone Detection Using DL</h2>
            <p>Built a deep learning model that analyzes text to detect emotions and tone. The application can identify various emotional states such as happiness, sadness, anger, and neutrality from written content, helping with sentiment analysis.</p>
            <p>Technologies used: Python, PyTorch, BERT, Web API</p>
        </div>
    </div>

    <div id="project4Modal" class="project-modal">
        <div class="project-modal-content">
            <span class="close" onclick="closeModal('project4Modal')">&times;</span>
            <h2>Crowd Management during festivals</h2>
            <p>Developed a system for monitoring and managing crowd density during large festivals. Using computer vision techniques, this solution helps prevent overcrowding and improves safety at large public gatherings.</p>
            <p>Technologies used: Python, OpenCV, TensorFlow, IoT sensors</p>
        </div>
    </div>

    <div id="project5Modal" class="project-modal">
        <div class="project-modal-content">
            <span class="close" onclick="closeModal('project5Modal')">&times;</span>
            <h2>Real-time Anomaly Detection</h2>
            <p>Implemented a real-time system that detects unusual patterns and anomalies in data streams. This project is applicable for network security, fraud detection, and monitoring industrial systems.</p>
            <p>Technologies used: Python, Kafka, Spark, Machine Learning algorithms</p>
        </div>
    </div>

    <div id="project6Modal" class="project-modal">
        <div class="project-modal-content">
            <span class="close" onclick="closeModal('project6Modal')">&times;</span>
            <h2>Hospital Management System</h2>
            <p>Created a comprehensive hospital management system that streamlines patient registration, appointment scheduling, medical records management, and billing processes.</p>
            <p>Technologies used: Java, Spring Boot, MySQL, React.js</p>
        </div>
    </div>

    <section id="testimonials" class="testimonials-section">
        <h2>Testimonials</h2>
        <div class="testimonials-container">
            <div class="testimonial-card">
                <div class="quote-icon"><i class="fas fa-quote-left"></i></div>
                <p>"Aiyisha demonstrated exceptional skill and dedication during her internship. Her problem-solving abilities and technical knowledge were impressive."</p>
                <div class="author">Dr. Rajesh Kumar</div>
                <div class="company">Professor, VIT Chennai</div>
            </div>
            <div class="testimonial-card">
                <div class="quote-icon"><i class="fas fa-quote-left"></i></div>
                <p>"Working with Aiyisha on our project was a pleasure. She brings creativity and technical excellence to the table."</p>
                <div class="author">Sahishna Rajesh</div>
                <div class="company">2nd Year student at VIT Chennai</div>
            </div>
            <div class="testimonial-card">
                <div class="quote-icon"><i class="fas fa-quote-left"></i></div>
                <p>"Aiyisha's attention to detail and innovative approach to coding challenges sets her apart from her peers."</p>
                <div class="author">Vikram Sharma</div>
                <div class="company">Senior Developer, 4th Year student at VIT Chennai</div>
            </div>
        </div>
    </section>

    <section id="blog" class="blog-section">
        <h2>Blog Posts</h2>
        <div class="blog-container">
            <div class="blog-card">
                <h3>The Future of AI in Healthcare</h3>
                <p>Exploring how artificial intelligence is revolutionizing medical diagnoses, treatment plans, and patient care.</p>
                <a href="#">Read More</a>
            </div>
            <div class="blog-card">
                <h3>Building Responsive Web Apps</h3>
                <p>Tips and techniques for creating web applications that work seamlessly across all devices and screen sizes.</p>
                <a href="#">Read More</a>
            </div>
            <div class="blog-card">
                <h3>Machine Learning for Beginners</h3>
                <p>A step-by-step guide to getting started with machine learning, covering key concepts and practical applications.</p>
                <a href="#">Read More</a>
            </div>
        </div>
    </section>

    <section id="contact" class="contact-section">
        <h2>Get In Touch</h2>
        <form id="contact-form">
            <div class="form-group">
                <input type="text" id="name" placeholder="Your Name" required>
            </div>
            <div class="form-group">
                <input type="email" id="email" placeholder="Your Email" required>
            </div>
            <div class="form-group">
                <input type="text" id="subject" placeholder="Subject">
            </div>
            <div class="form-group">
                <textarea id="message" placeholder="Your Message" required></textarea>
            </div>
            <button type="submit">Send Message</button>
            <div id="form-status"></div>
        </form>
        <div class="contact-links">
            <a href="#" aria-label="LinkedIn"><i class="fab fa-linkedin-in"></i></a>
            <a href="#" aria-label="GitHub"><i class="fab fa-github"></i></a>
            <a href="#" aria-label="Twitter"><i class="fab fa-twitter"></i></a>
            <a href="#" aria-label="Email"><i class="fas fa-envelope"></i></a>
        </div>
    </section>

    <canvas id="particles"></canvas>

    <script>
        // Particle animation for background
        const canvas = document.getElementById('particles');
        const ctx = canvas.getContext('2d');

        // Set canvas dimensions
        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        resizeCanvas();
        window.addEventListener('resize', resizeCanvas);

        // Particle class
        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 3 + 1;
                this.speedX = Math.random() * 2 - 1;
                this.speedY = Math.random() * 2 - 1;
                this.color = `rgba(255, 255, 255, ${Math.random() * 0.5})`;
            }

            update() {
                this.x += this.speedX;
                this.y += this.speedY;

                if (this.x > canvas.width || this.x < 0) {
                    this.speedX = -this.speedX;
                }
                if (this.y > canvas.height || this.y < 0) {
                    this.speedY = -this.speedY;
                }
            }

            draw() {
                ctx.fillStyle = this.color;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        // Create particle array
        const particles = [];
        for (let i = 0; i < 150; i++) {
            particles.push(new Particle());
        }

        // Animation function
        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            
            for (let i = 0; i < particles.length; i++) {
                particles[i].update();
                particles[i].draw();
                
                // Connect particles within range
                for (let j = i; j < particles.length; j++) {
                    const dx = particles[i].x - particles[j].x;
                    const dy = particles[i].y - particles[j].y;
                    const distance = Math.sqrt(dx * dx + dy * dy);
                    
                    if (distance < 100) {
                        ctx.beginPath();
                        ctx.strokeStyle = `rgba(255, 255, 255, ${0.1 - distance/1000})`;
                        ctx.lineWidth = 0.5;
                        ctx.moveTo(particles[i].x, particles[i].y);
                        ctx.lineTo(particles[j].x, particles[j].y);
                        ctx.stroke();
                    }
                }
            }
            
            requestAnimationFrame(animate);
        }
        animate();
         // Particle animation
         document.addEventListener('DOMContentLoaded', function() {
            const canvas = document.getElementById('particles');
            const ctx = canvas.getContext('2d');
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
            
            let particlesArray = [];
            
            // Create particle class
            class Particle {
                constructor() {
                    this.x = Math.random() * canvas.width;
                    this.y = Math.random() * canvas.height;
                    this.size = Math.random() * 5 + 1;
                    this.speedX = Math.random() * 3 - 1.5;
                    this.speedY = Math.random() * 3 - 1.5;
                    this.color = `rgba(255, 255, 255, ${Math.random() * 0.5})`;
                }
                
                update() {
                    this.x += this.speedX;
                    this.y += this.speedY;
                    
                    if (this.size > 0.2) this.size -= 0.1;
                    
                    if (this.x < 0 || this.x > canvas.width) this.speedX *= -1;
                    if (this.y < 0 || this.y > canvas.height) this.speedY *= -1;
                }
                
                draw() {
                    ctx.fillStyle = this.color;
                    ctx.beginPath();
                    ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                    ctx.fill();
                }
            }
            
            function init() {
                particlesArray = [];
                for (let i = 0; i < 100; i++) {
                    particlesArray.push(new Particle());
                }
            }
            
            function animate() {
                ctx.clearRect(0, 0, canvas.width, canvas.height);
                for (let i = 0; i < particlesArray.length; i++) {
                    particlesArray[i].update();
                    particlesArray[i].draw();
                    
                    // Connect particles with lines
                    for (let j = i; j < particlesArray.length; j++) {
                        const dx = particlesArray[i].x - particlesArray[j].x;
                        const dy = particlesArray[i].y - particlesArray[j].y;
                        const distance = Math.sqrt(dx * dx + dy * dy);
                        
                        if (distance < 100) {
                            ctx.beginPath();
                            ctx.strokeStyle = `rgba(255, 255, 255, ${0.5 - distance/100})`;
                            ctx.lineWidth = 0.2;
                            ctx.moveTo(particlesArray[i].x, particlesArray[i].y);
                            ctx.lineTo(particlesArray[j].x, particlesArray[j].y);
                            ctx.stroke();
                        }
                    }
                    
                    // Remove particles
                    if (particlesArray[i].size <= 0.2) {
                        particlesArray.splice(i, 1);
                        i--;
                        // Add new particle
                        particlesArray.push(new Particle());
                    }
                }
                requestAnimationFrame(animate);
            }
            
            // Handle window resize
            window.addEventListener('resize', function() {
                canvas.width = window.innerWidth;
                canvas.height = window.innerHeight;
                init();
            });
            
            init();
            animate();
            
            // Create particles on mouse move
            window.addEventListener('mousemove', function(e) {
                for (let i = 0; i < 3; i++) {
                    let particle = new Particle();
                    particle.x = e.x;
                    particle.y = e.y;
                    particlesArray.push(particle);
                }
            });
        });

        // Project modal functions
        function openProject(projectId) {
            document.getElementById(projectId + 'Modal').style.display = 'block';
        }

        function closeModal(modalId) {
            document.getElementById(modalId).style.display = 'none';
        }

        // Close modal if clicked outside of content
        window.onclick = function(event) {
            const modals = document.getElementsByClassName('project-modal');
            for (let i = 0; i < modals.length; i++) {
                if (event.target === modals[i]) {
                    modals[i].style.display = 'none';
                }
            }
        }

        // Certificate viewer
        function showCertificate(element) {
            const imgSrc = element.parentElement.querySelector('img').src;
            const title = element.parentElement.querySelector('h3').textContent;
            
            // Create modal for certificate
            const modal = document.createElement('div');
            modal.style.position = 'fixed';
            modal.style.top = '0';
            modal.style.left = '0';
            modal.style.width = '100%';
            modal.style.height = '100%';
            modal.style.backgroundColor = 'rgba(0,0,0,0.9)';
            modal.style.zIndex = '1001';
            modal.style.display = 'flex';
            modal.style.justifyContent = 'center';
            modal.style.alignItems = 'center';
            modal.style.flexDirection = 'column';
            
            // Add certificate image
            const img = document.createElement('img');
            img.src = imgSrc;
            img.style.maxWidth = '80%';
            img.style.maxHeight = '80%';
            img.style.border = '5px solid white';
            img.style.borderRadius = '10px';
            
            // Add title
            const titleElem = document.createElement('h3');
            titleElem.textContent = title;
            titleElem.style.color = 'white';
            titleElem.style.marginTop = '20px';
            
            // Add close button
            const closeBtn = document.createElement('span');
            closeBtn.textContent = '×';
            closeBtn.style.position = 'absolute';
            closeBtn.style.top = '20px';
            closeBtn.style.right = '30px';
            closeBtn.style.color = 'white';
            closeBtn.style.fontSize = '40px';
            closeBtn.style.cursor = 'pointer';
            closeBtn.onclick = function() {
                document.body.removeChild(modal);
            };
            
            modal.appendChild(img);
            modal.appendChild(titleElem);
            modal.appendChild(closeBtn);
            document.body.appendChild(modal);
        }

        // Theme toggle
        const themeToggle = document.getElementById('theme-toggle');
        
        themeToggle.addEventListener('change', function() {
            if (this.checked) {
                document.body.classList.remove('dark-theme');
                document.body.classList.add('light-theme');
            } else {
                document.body.classList.remove('light-theme');
                document.body.classList.add('dark-theme');
            }
        });
        
        // Form submission
        const contactForm = document.getElementById('contact-form');
        const formStatus = document.getElementById('form-status');
        
        contactForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            formStatus.textContent = 'Sending...';
            
            // Simulate form submission
            setTimeout(() => {
                formStatus.textContent = 'Message sent successfully!';
                formStatus.style.color = '#4CAF50';
                contactForm.reset();
                
                // Clear success message after 3 seconds
                setTimeout(() => {
                    formStatus.textContent = '';
                }, 3000);
            }, 1500);
        });
        
    document.getElementById("readAloudButton").addEventListener("click", function () {
        const textToRead = document.querySelector(".profile-container").innerText;
        const speech = new SpeechSynthesisUtterance(textToRead);
        speech.lang = "en-US"; // Set language
        speech.rate = 1; // Set reading speed
        speech.pitch = 1; // Set pitch
        window.speechSynthesis.speak(speech);
    });
    
    </script>
</body>
</html>
