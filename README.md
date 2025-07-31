<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- Chosen Palette: Calm & Assuring -->
    <!-- Application Structure Plan: The SPA is structured as a single-page, scrollable form that directly mirrors the four sections of the source survey. This linear flow is the most intuitive for a user filling out a questionnaire. A sticky progress bar at the top provides visual feedback on completion. Each section is presented as a distinct card to group related questions, improving readability and focus. The primary interaction is filling out the form, culminating in a submission button with a confirmation message. This structure was chosen for its simplicity, direct translation of the source material, and user-friendliness for a data-collection task. -->
    <!-- Visualization & Content Choices: The goal is data collection, not data visualization. Therefore, instead of charts, the focus is on creating a high-quality, interactive user interface for the form. Likert scales are implemented as custom-styled radio button groups for better usability than standard radios. Checkboxes are also custom-styled for a consistent look. A dynamic progress bar (Goal: Inform) visually communicates completion status to the user, enhancing engagement. All diagrams or structural elements are built with structured HTML and Tailwind CSS. This approach prioritizes a seamless user experience for the primary task: completing the survey. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <title>BME Handyman Perth - Operational Assessment</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #F0F4F8;
            color: #102A43;
        }
        .card {
            background-color: #FFFFFF;
            border-radius: 1rem;
            padding: 2rem;
            box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.05), 0 4px 6px -4px rgb(0 0 0 / 0.05);
            margin-bottom: 2rem;
        }
        .progress-bar-container {
            background-color: #D9E2EC;
        }
        .progress-bar {
            background-color: #3B82F6;
            transition: width 0.3s ease-in-out;
        }
        input[type="radio"], input[type="checkbox"] {
            position: absolute;
            opacity: 0;
            width: 0;
            height: 0;
        }
        .radio-label, .checkbox-label {
            cursor: pointer;
            padding: 0.75rem 1.25rem;
            border-radius: 0.5rem;
            border: 2px solid #D9E2EC;
            transition: all 0.2s ease;
            display: block;
            text-align: center;
        }
        input[type="radio"]:checked + .radio-label,
        input[type="checkbox"]:checked + .checkbox-label {
            background-color: #3B82F6;
            color: #FFFFFF;
            border-color: #3B82F6;
            font-weight: 600;
        }
        input[type="radio"]:focus + .radio-label,
        input[type="checkbox"]:focus + .checkbox-label {
            box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.4);
        }
        .scale-group {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
            gap: 0.5rem;
        }
        .checkbox-group {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 0.75rem;
        }
        textarea {
            background-color: #F0F4F8;
            border: 2px solid #D9E2EC;
            border-radius: 0.5rem;
            padding: 0.75rem;
            transition: border-color 0.2s ease;
        }
        textarea:focus {
            outline: none;
            border-color: #3B82F6;
            box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.4);
        }
        .form-question {
            margin-bottom: 2rem;
        }
        .question-text {
            font-weight: 600;
            color: #334E68;
            margin-bottom: 1rem;
            display: block;
        }
    </style>
</head>
<body>

    <header class="sticky top-0 z-10 bg-white/80 backdrop-blur-md shadow-sm">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="py-4">
                <h1 class="text-xl font-bold text-center">BME Handyman Perth - Operational Assessment</h1>
                <div class="progress-bar-container w-full h-2 rounded-full mt-2 overflow-hidden">
                    <div id="progressBar" class="progress-bar h-full rounded-full" style="width: 0%;"></div>
                </div>
            </div>
        </div>
    </header>

    <main class="container mx-auto p-4 sm:p-6 lg:p-8 max-w-4xl">
        <div class="text-center mb-12">
            <h2 class="text-3xl font-bold mb-2">Help Us Understand Your Business</h2>
            <p class="text-lg text-[#486581]">Your insights will help us identify how AroFlo can best support your growth. Please answer the following questions.</p>
        </div>

        <form id="assessmentForm">
            
            <section id="section1" class="card">
                <h3 class="text-2xl font-bold mb-6 border-b pb-4">Section 1: Operational Efficiency & Productivity</h3>
                
                <div class="form-question">
                    <label class="question-text">1.1 On a scale of 1 to 5, how much time do you estimate your team spends on administrative tasks each week?</label>
                    <div class="scale-group">
                        <div><input type="radio" name="q1_1" id="q1_1_1" value="1"><label for="q1_1_1" class="radio-label">1<span class="hidden sm:inline"> (0-5h)</span></label></div>
                        <div><input type="radio" name="q1_1" id="q1_1_2" value="2"><label for="q1_1_2" class="radio-label">2<span class="hidden sm:inline"> (6-10h)</span></label></div>
                        <div><input type="radio" name="q1_1" id="q1_1_3" value="3"><label for="q1_1_3" class="radio-label">3<span class="hidden sm:inline"> (11-20h)</span></label></div>
                        <div><input type="radio" name="q1_1" id="q1_1_4" value="4"><label for="q1_1_4" class="radio-label">4<span class="hidden sm:inline"> (21-30h)</span></label></div>
                        <div><input type="radio" name="q1_1" id="q1_1_5" value="5"><label for="q1_1_5" class="radio-label">5<span class="hidden sm:inline"> (30+h)</span></label></div>
                    </div>
                </div>

                <div class="form-question">
                    <label class="question-text">1.2 What are your biggest frustrations when managing multiple jobs? (Select all that apply)</label>
                    <div class="checkbox-group">
                        <div><input type="checkbox" name="q1_2" id="q1_2_1" value="scheduling"><label for="q1_2_1" class="checkbox-label">Scheduling conflicts</label></div>
                        <div><input type="checkbox" name="q1_2" id="q1_2_2" value="tracking"><label for="q1_2_2" class="checkbox-label">Tracking job progress</label></div>
                        <div><input type="checkbox" name="q1_2" id="q1_2_3" value="paperwork"><label for="q1_2_3" class="checkbox-label">Manual paperwork</label></div>
                        <div><input type="checkbox" name="q1_2" id="q1_2_4" value="coordination"><label for="q1_2_4" class="checkbox-label">Coordinating team members</label></div>
                        <div><input type="checkbox" name="q1_2" id="q1_2_5" value="quoting"><label for="q1_2_5" class="checkbox-label">Slow quoting process</label></div>
                        <div><input type="checkbox" name="q1_2" id="q1_2_6" value="overview"><label for="q1_2_6" class="checkbox-label">Lack of clear overview</label></div>
                    </div>
                </div>

                <div class="form-question">
                    <label class="question-text">1.3 How long does it typically take to send a finalized quote after an inquiry?</label>
                    <div class="checkbox-group">
                        <div><input type="radio" name="q1_3" id="q1_3_1" value="<24h"><label for="q1_3_1" class="radio-label">Less than 24 hours</label></div>
                        <div><input type="radio" name="q1_3" id="q1_3_2" value="1-2d"><label for="q1_3_2" class="radio-label">1-2 days</label></div>
                        <div><input type="radio" name="q1_3" id="q1_3_3" value="3-5d"><label for="q1_3_3" class="radio-label">3-5 days</label></div>
                        <div><input type="radio" name="q1_3" id="q1_3_4" value=">5d"><label for="q1_3_4" class="radio-label">More than 5 days</label></div>
                    </div>
                </div>
            </section>

            <section id="section2" class="card">
                <h3 class="text-2xl font-bold mb-6 border-b pb-4">Section 2: Client Experience & Communication</h3>
                
                <div class="form-question">
                    <label class="question-text">2.1 On a scale of 1 to 5, how satisfied are you with your current client communication process?</label>
                    <div class="scale-group">
                        <div><input type="radio" name="q2_1" id="q2_1_1" value="1"><label for="q2_1_1" class="radio-label">1 (Not)</label></div>
                        <div><input type="radio" name="q2_1" id="q2_1_2" value="2"><label for="q2_1_2" class="radio-label">2 (Slightly)</label></div>
                        <div><input type="radio" name="q2_1" id="q2_1_3" value="3"><label for="q2_1_3" class="radio-label">3 (Mod.)</label></div>
                        <div><input type="radio" name="q2_1" id="q2_1_4" value="4"><label for="q2_1_4" class="radio-label">4 (Very)</label></div>
                        <div><input type="radio" name="q2_1" id="q2_1_5" value="5"><label for="q2_1_5" class="radio-label">5 (Ext.)</label></div>
                    </div>
                </div>

                <div class="form-question">
                    <label class="question-text">2.2 How important is offering automated reminders or a client portal?</label>
                    <div class="checkbox-group">
                        <div><input type="radio" name="q2_2" id="q2_2_1" value="not"><label for="q2_2_1" class="radio-label">Not important</label></div>
                        <div><input type="radio" name="q2_2" id="q2_2_2" value="slightly"><label for="q2_2_2" class="radio-label">Slightly important</label></div>
                        <div><input type="radio" name="q2_2" id="q2_2_3" value="moderately"><label for="q2_2_3" class="radio-label">Moderately important</label></div>
                        <div><input type="radio" name="q2_2" id="q2_2_4" value="very"><label for="q2_2_4" class="radio-label">Very important</label></div>
                    </div>
                </div>
            </section>

            <section id="section3" class="card">
                <h3 class="text-2xl font-bold mb-6 border-b pb-4">Section 3: Scalability, Growth & Risk Mitigation</h3>
                
                <div class="form-question">
                    <label class="question-text">3.1 What are your biggest concerns about future growth? (Select all that apply)</label>
                    <div class="checkbox-group">
                        <div><input type="checkbox" name="q3_1" id="q3_1_1" value="admin"><label for="q3_1_1" class="checkbox-label">Admin burden</label></div>
                        <div><input type="checkbox" name="q3_1" id="q3_1_2" value="job_mgmt"><label for="q3_1_2" class="checkbox-label">Managing more jobs</label></div>
                        <div><input type="checkbox" name="q3_1" id="q3_1_3" value="quality"><label for="q3_1_3" class="checkbox-label">Maintaining quality</label></div>
                        <div><input type="checkbox" name="q3_1" id="q3_1_4" value="training"><label for="q3_1_4" class="checkbox-label">Training new staff</label></div>
                        <div><input type="checkbox" name="q3_1" id="q3_1_5" value="compliance"><label for="q3_1_5" class="checkbox-label">Ensuring compliance</label></div>
                        <div><input type="checkbox" name="q3_1" id="q3_1_6" value="errors"><label for="q3_1_6" class="checkbox-label">Risk of errors</label></div>
                    </div>
                </div>

                <div class="form-question">
                    <label class="question-text">3.2 On a scale of 1 to 5, how confident are you in your current system for managing safety and compliance?</label>
                    <div class="scale-group">
                        <div><input type="radio" name="q3_2" id="q3_2_1" value="1"><label for="q3_2_1" class="radio-label">1 (Not)</label></div>
                        <div><input type="radio" name="q3_2" id="q3_2_2" value="2"><label for="q3_2_2" class="radio-label">2 (Slightly)</label></div>
                        <div><input type="radio" name="q3_2" id="q3_2_3" value="3"><label for="q3_2_3" class="radio-label">3 (Mod.)</label></div>
                        <div><input type="radio" name="q3_2" id="q3_2_4" value="4"><label for="q3_2_4" class="radio-label">4 (Very)</label></div>
                        <div><input type="radio" name="q3_2" id="q3_2_5" value="5"><label for="q3_2_5" class="radio-label">5 (Ext.)</label></div>
                    </div>
                </div>
            </section>

            <section id="section4" class="card">
                <h3 class="text-2xl font-bold mb-6 border-b pb-4">Section 4: Data-Driven Insights & Profitability</h3>
                
                <div class="form-question">
                    <label class="question-text">4.1 What operational insights beyond financials would be most valuable? (Select all that apply)</label>
                    <div class="checkbox-group">
                        <div><input type="checkbox" name="q4_1" id="q4_1_1" value="job_profit"><label for="q4_1_1" class="checkbox-label">Job profitability by type</label></div>
                        <div><input type="checkbox" name="q4_1" id="q4_1_2" value="completion_time"><label for="q4_1_2" class="checkbox-label">Avg. job completion time</label></div>
                        <div><input type="checkbox" name="q4_1" id="q4_1_3" value="team_util"><label for="q4_1_3" class="checkbox-label">Team utilization rates</label></div>
                        <div><input type="checkbox" name="q4_1" id="q4_1_4" value="cust_sat"><label for="q4_1_4" class="checkbox-label">Customer satisfaction scores</label></div>
                        <div><input type="checkbox" name="q4_1" id="q4_1_5" value="demand_trends"><label for="q4_1_5" class="checkbox-label">Service demand trends</label></div>
                        <div><input type="checkbox" name="q4_1" id="q4_1_6" value="material_cost"><label for="q4_1_6" class="checkbox-label">Cost of materials per job</label></div>
                    </div>
                </div>
                
                <div class="form-question">
                    <label for="q4_2" class="question-text">4.2 If you had real-time data on job costs and resource use, how might that impact your strategic planning?</label>
                    <textarea id="q4_2" name="q4_2" rows="4" class="w-full" placeholder="e.g., adjust pricing, focus on more profitable services, optimize team schedules..."></textarea>
                </div>
            </section>

            <div class="text-center mt-8">
                <button type="submit" class="bg-[#3B82F6] text-white font-bold py-3 px-8 rounded-lg shadow-lg hover:bg-blue-700 transition-colors">Submit Assessment</button>
            </div>
        </form>
    </main>

    <div id="thankYouModal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center p-4 hidden">
        <div class="bg-white rounded-lg shadow-xl p-8 text-center max-w-sm">
            <h2 class="text-2xl font-bold mb-4">Thank You!</h2>
            <p class="text-[#486581] mb-6">Your responses have been recorded. We appreciate you taking the time to share these valuable insights. We will be in touch shortly to discuss how AroFlo can help you achieve your business goals.</p>
            <button id="closeModal" class="bg-gray-200 text-[#102A43] font-bold py-2 px-6 rounded-lg hover:bg-gray-300 transition-colors">Close</button>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const form = document.getElementById('assessmentForm');
            const sections = document.querySelectorAll('main section');
            const progressBar = document.getElementById('progressBar');
            const modal = document.getElementById('thankYouModal');
            const closeModalBtn = document.getElementById('closeModal');
            
            const totalQuestions = document.querySelectorAll('.form-question').length;

            function updateProgress() {
                const answeredQuestions = document.querySelectorAll('input:checked, textarea:not(:placeholder-shown)').length;
                const progress = (answeredQuestions / totalQuestions) * 100;
                progressBar.style.width = `${progress}%`;
            }

            form.addEventListener('change', updateProgress);
            form.addEventListener('keyup', updateProgress);

            form.addEventListener('submit', (e) => {
                e.preventDefault();
                modal.classList.remove('hidden');
            });

            closeModalBtn.addEventListener('click', () => {
                modal.classList.add('hidden');
                form.reset();
                updateProgress();
            });
        });
    </script>
</body>
</html>
