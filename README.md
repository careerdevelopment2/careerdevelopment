<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Career Development & Skill Matching</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            color: #333;
            background-color: #f8f9fa;
        }
        header {
            background-color: #007bff;
            color: #ffffff;
            padding: 30px 20px;
            text-align: center;
        }
        header h1 {
            margin: 0;
            font-size: 2.5em;
        }
        section {
            padding: 20px;
            background-color: #ffffff;
            margin: 20px auto;
            max-width: 800px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        section h2 {
            margin-top: 0;
            border-bottom: 2px solid #007bff;
            padding-bottom: 10px;
            color: #007bff;
        }
        .form-step, .checkbox-group, .recommendations {
            margin-bottom: 20px;
        }
        .form-step label, .checkbox-group label {
            display: block;
            margin-bottom: 10px;
        }
        .form-step input, .form-step select, .checkbox-group input {
            width: 100%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        .step-navigation {
            text-align: center;
            margin-top: 20px;
        }
        .step-navigation button {
            background-color: #007bff;
            color: #ffffff;
            padding: 15px;
            font-size: 1.2em;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s, transform 0.3s;
        }
        .step-navigation button:hover {
            background-color: #0056b3;
            transform: translateY(-2px);
        }
        /* Updated styles for Step 3 */
        .recommendations {
            background-color: #e9ecef;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .recommendations h3 {
            font-size: 1.5em;
            color: #007bff;
            margin-bottom: 15px;
        }
        .recommendations ul {
            list-style: none;
            padding: 0;
            margin: 0;
        }
        .recommendations li {
            background-color: #ffffff;
            border-radius: 5px;
            padding: 15px;
            margin: 10px 0;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            transition: background-color 0.3s, transform 0.3s;
        }
        .recommendations li:hover {
            background-color: #f1f3f5;
            transform: translateY(-2px);
        }
    </style>
</head>
<body>
    <header>
        <h1>Career Development & Skill Matching</h1>
    </header>

    <section id="intro-page">
        <h2>Welcome</h2>
        <p>Welcome to your ultimate career advancement tool! Our platform is designed to help you identify your strengths, explore new career paths, and receive personalized recommendations tailored to your aspirations. By starting with some basic information and selecting your skills, you’ll unlock customized job and study suggestions that align with your career goals. Begin your journey today and find the perfect match for your skills and ambitions!</p>
        <div class="step-navigation">
            <button onclick="showSection('basic-info')">Get Started</button>
        </div>
    </section>

    <section id="basic-info" style="display:none;">
        <h2>Step 1: Basic Information</h2>
        <form id="basic-info-form">
            <div class="form-step">
                <label for="name">Full Name:</label>
                <input type="text" id="name" name="name" required>
            </div>
            <div class="form-step">
                <label for="education">Highest Level of Education:</label>
                <select id="education" name="education" required>
                    <option value="">Select</option>
                    <option value="high-school">High School</option>
                    <option value="associate-degree">Associate Degree</option>
                    <option value="bachelor-degree">Bachelor's Degree</option>
                    <option value="master-degree">Master's Degree</option>
                    <option value="doctorate-degree">Doctorate Degree</option>
                </select>
            </div>
            <div class="form-step">
                <label for="year-gap">Do you have any year gaps in your education?</label>
                <select id="year-gap" name="year-gap" onchange="handleYearGapChange()" required>
                    <option value="">Select</option>
                    <option value="none">None</option>
                    <option value="1-year">1 Year</option>
                    <option value="2-years">2 Years</option>
                    <option value="3-years">3 Years or More</option>
                </select>
            </div>
            <div class="step-navigation">
                <button type="button" onclick="showSection('skill-selection')">Next</button>
            </div>
        </form>
    </section>

    <section id="skill-selection" style="display:none;">
        <h2>Step 2: Select Your Skills</h2>
        <form id="skill-form">
            <div class="checkbox-group">
                <label><input type="checkbox" name="skills" value="Programming"> Programming</label>
                <label><input type="checkbox" name="skills" value="Marketing"> Marketing</label>
                <label><input type="checkbox" name="skills" value="Design"> Design</label>
                <label><input type="checkbox" name="skills" value="Project Management"> Project Management</label>
                <label><input type="checkbox" name="skills" value="Software Development"> Software Development</label>
                <label><input type="checkbox" name="skills" value="Digital Marketing"> Digital Marketing</label>
                <label><input type="checkbox" name="skills" value="SEO"> SEO</label>
                <label><input type="checkbox" name="skills" value="Cybersecurity"> Cybersecurity</label>
                <label><input type="checkbox" name="skills" value="AI and Machine Learning"> AI and Machine Learning</label>
                <label><input type="checkbox" name="skills" value="Cloud Computing"> Cloud Computing</label>
                <label><input type="checkbox" name="skills" value="Graphic Design"> Graphic Design</label>
                <label><input type="checkbox" name="skills" value="Networking"> Networking</label>
            </div>
            <div class="step-navigation">
                <button type="button" onclick="showSection('recommendations')">Get Recommendations</button>
            </div>
        </form>
    </section>

    <section id="recommendations" style="display:none;">
        <h2>Step 3: Job and Study Recommendations</h2>
        <div id="job-recommendations" class="recommendations">
            <!-- Recommendations will be dynamically inserted here -->
        </div>
        <div id="study-recommendations" class="recommendations">
            <!-- Recommendations will be dynamically inserted here -->
        </div>
        <div class="step-navigation">
            <button type="button" onclick="showSection('intro-page')">Start Over</button>
        </div>
    </section>

    <script>
        function showSection(sectionId) {
            const sections = document.querySelectorAll('section');
            sections.forEach(section => section.style.display = 'none');
            document.getElementById(sectionId).style.display = 'block';
        }

        function handleYearGapChange() {
            const yearGap = document.getElementById('year-gap').value;
            const jobRecommendations = document.getElementById('job-recommendations');
            const studyRecommendations = document.getElementById('study-recommendations');

            if (yearGap !== "none") {
                jobRecommendations.innerHTML = `
                    <h3>Your Job Recommendations:</h3>
                    <ul>
                        <li>Freelance Web Developer</li>
                        <li>Remote Content Creator</li>
                        <li>Part-Time Customer Support</li>
                        <li>Freelance Consultant</li>
                        <li>Part-Time Project Coordinator</li>
                    </ul>`;
                studyRecommendations.innerHTML = `
                    <h3>Your Study Recommendations:</h3>
                    <ul>
                        <li>Online Certification in Digital Marketing</li>
                        <li>Part-Time Data Science Course</li>
                        <li>Short Courses in Emerging Technologies</li>
                    </ul>`;
            } else {
                jobRecommendations.innerHTML = `
                    <h3>Your Job Recommendations:</h3>
                    <ul>
                        <li>Software Engineer</li>
                        <li>Data Analyst</li>
                        <li>Marketing Manager</li>
                        <li>Project Manager</li>
                        <li>UI/UX Designer</li>
                        <li>Business Analyst</li>
                        <li>Database Administrator</li>
                        <li>Content Strategist</li>
                        <li>Digital Marketer</li>
                        <li>Product Manager</li>
                        <li>Sales Executive</li>
                        <li>Customer Success Manager</li>
                        <li>Human Resources Specialist</li>
                        <li>Financial Analyst</li>
                        <li>Healthcare Administrator</li>
                        <li>Educational Consultant</li>
                        <li>Legal Advisor</li>
                        <li>Graphic Designer</li>
                        <li>Web Developer</li>
                        <li>SEO Specialist</li>
                        <li>Cybersecurity Analyst</li>
                        <li>Cloud Solutions Architect</li>
                        <li>Freelance Consultant</li>
                        <li>Supply Chain Coordinator</li>
                        <li>Operations Manager</li>
                        <li>Research Scientist</li>
                        <li>Technical Support Specialist</li>
                        <li>Event Coordinator</li>
                        <li>Network Engineer</li>
                    </ul>`;
                studyRecommendations.innerHTML = `
                    <h3>Your Study Recommendations:</h3>
                    <ul>
                        <li>Master's in AI and Machine Learning</li>
                        <li>Certification in Cybersecurity</li>
                        <li>Advanced Data Science and Analytics Program</li>
                    </ul>`;
            }
        }
    </script>
</body>
</html>
