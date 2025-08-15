<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vaibhav Bhargav - Developer Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background: #0a0a0a;
            color: #ffffff;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Animated background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(45deg, #1e3c72, #2a5298, #1e3c72, #0f2027);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Floating particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .particle {
            position: absolute;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-100vh) rotate(360deg); opacity: 0; }
        }

        .main-container {
            max-width: 900px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        /* Header Banner */
        .header-banner {
            position: relative;
            border-radius: 20px;
            overflow: hidden;
            margin-bottom: 40px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
        }

        .banner-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            filter: brightness(0.8);
        }

        .header-content {
            text-align: center;
            padding: 40px 20px;
            background: rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
        }

        .name-title {
            font-size: 3.5rem;
            font-weight: 800;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 15px;
            animation: titleGlow 3s ease-in-out infinite alternate;
        }

        @keyframes titleGlow {
            0% { filter: brightness(1); }
            100% { filter: brightness(1.2); }
        }

        .subtitle {
            font-size: 1.3rem;
            color: #b8c5d6;
            font-weight: 500;
            margin-bottom: 10px;
        }

        .education {
            font-size: 1rem;
            color: #8892b0;
            font-weight: 600;
            background: rgba(255, 255, 255, 0.1);
            padding: 8px 16px;
            border-radius: 20px;
            display: inline-block;
        }

        /* About Section */
        .about-section {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 40px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
        }

        .about-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.05), transparent);
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        .about-text {
            font-size: 1.1rem;
            color: #ccd6f6;
            text-align: justify;
            position: relative;
            z-index: 2;
        }

        /* Section Headers */
        .section-header {
            font-size: 2.2rem;
            font-weight: 700;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .section-header::before {
            content: '';
            width: 6px;
            height: 40px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 3px;
            box-shadow: 0 0 20px rgba(102, 126, 234, 0.5);
        }

        .emoji {
            font-size: 2rem;
        }

        /* Connect Section */
        .connect-section {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 40px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .social-links {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 50%;
            text-decoration: none;
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            position: relative;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.3);
        }

        .social-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: left 0.6s ease;
        }

        .social-link:hover::before {
            left: 100%;
        }

        .social-link:hover {
            transform: translateY(-8px) rotate(360deg) scale(1.15);
            box-shadow: 0 20px 40px rgba(102, 126, 234, 0.5);
        }

        .social-link img {
            width: 35px;
            height: 35px;
            filter: brightness(0) invert(1);
        }

        /* Tools Section */
        .tools-section {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 25px;
            margin-top: 25px;
        }

        .tool-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 25px 20px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            border: 1px solid rgba(255, 255, 255, 0.1);
            text-decoration: none;
            color: #ccd6f6;
            position: relative;
            overflow: hidden;
        }

        .tool-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            transform: scaleX(0);
            transition: transform 0.4s ease;
        }

        .tool-item:hover::before {
            transform: scaleX(1);
        }

        .tool-item:hover {
            background: rgba(255, 255, 255, 0.1);
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(102, 126, 234, 0.2);
            border-color: rgba(102, 126, 234, 0.4);
        }

        .tool-item img {
            width: 50px;
            height: 50px;
            margin-bottom: 12px;
            transition: all 0.4s ease;
        }

        .tool-item:hover img {
            transform: scale(1.3) rotate(5deg);
            filter: drop-shadow(0 0 20px rgba(102, 126, 234, 0.6));
        }

        .tool-name {
            font-size: 0.9rem;
            font-weight: 600;
            text-align: center;
            opacity: 0.8;
            transition: opacity 0.3s ease;
        }

        .tool-item:hover .tool-name {
            opacity: 1;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .name-title {
                font-size: 2.5rem;
            }
            
            .subtitle {
                font-size: 1.1rem;
            }
            
            .main-container {
                padding: 15px;
            }
            
            .tools-grid {
                grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
                gap: 15px;
            }
            
            .social-link {
                width: 70px;
                height: 70px;
            }
        }
    </style>
</head>
<body>
    <div class="bg-animation"></div>
    
    <div class="particles" id="particles"></div>
    
    <div class="main-container">
        <!-- Header Section -->
        <div class="header-banner">
            <img src="https://github.com/user-attachments/assets/1068e776-3efe-4b76-8ba5-4cf7c370c37e" 
                 alt="Professional Banner" class="banner-image">
            <div class="header-content">
                <h1 class="name-title">Vaibhav Bhargav</h1>
                <h3 class="subtitle">Insightful Computer Science Student with Java and Full-Stack Development skills</h3>
                <div class="education">VITB'26</div>
            </div>
        </div>

        <!-- About Section -->
        <div class="about-section">
            <p class="about-text">
                Hello there! I am a Computer Science student with a strong inclination towards acquiring knowledge and contributing positively to society through the domain of technology. My primary interest lies in Front-End development, where I enjoy designing user-friendly interfaces and creating innovative solutions. I am currently working on personal projects and improving on everything Front-End related.
            </p>
        </div>

        <!-- Connect Section -->
        <div class="connect-section">
            <h3 class="section-header">
                <span class="emoji">🌐</span>
                Connect with me
            </h3>
            <div class="social-links">
                <a href="https://www.linkedin.com/in/vaibhav-bhargav-208470252/" 
                   target="_blank" class="social-link" title="LinkedIn">
                    <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="LinkedIn">
                </a>
                <a href="https://www.instagram.com/vaibhav_0310/" 
                   target="_blank" class="social-link" title="Instagram">
                    <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/instagram.svg" alt="Instagram">
                </a>
                <a href="https://leetcode.com/u/vbhargav0310/" 
                   target="_blank" class="social-link" title="LeetCode">
                    <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/leet-code.svg" alt="LeetCode">
                </a>
            </div>
        </div>

        <!-- Tools Section -->
        <div class="tools-section">
            <h2 class="section-header">
                <span class="emoji">🧰</span>
                Languages and Tools
            </h2>
            <div class="tools-grid">
                <a href="https://www.w3.org/html/" target="_blank" class="tool-item" title="HTML5">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="HTML5">
                    <span class="tool-name">HTML5</span>
                </a>
                <a href="https://www.w3schools.com/css/" target="_blank" class="tool-item" title="CSS3">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="CSS3">
                    <span class="tool-name">CSS3</span>
                </a>
                <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank" class="tool-item" title="JavaScript">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="JavaScript">
                    <span class="tool-name">JavaScript</span>
                </a>
                <a href="https://getbootstrap.com" target="_blank" class="tool-item" title="Bootstrap">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/bootstrap/bootstrap-plain-wordmark.svg" alt="Bootstrap">
                    <span class="tool-name">Bootstrap</span>
                </a>
                <a href="https://www.java.com" target="_blank" class="tool-item" title="Java">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="Java">
                    <span class="tool-name">Java</span>
                </a>
                <a href="https://www.mysql.com/" target="_blank" class="tool-item" title="MySQL">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="MySQL">
                    <span class="tool-name">MySQL</span>
                </a>
            </div>
        </div>
    </div>

    <script>
        // Create floating particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            
            for (let i = 0; i < 50; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                
                const size = Math.random() * 4 + 1;
                particle.style.width = size + 'px';
                particle.style.height = size + 'px';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDuration = (Math.random() * 20 + 10) + 's';
                particle.style.animationDelay = Math.random() * 20 + 's';
                
                particlesContainer.appendChild(particle);
            }
        }

        // Initialize particles when page loads
        window.addEventListener('load', createParticles);
    </script>
</body>
</html>
