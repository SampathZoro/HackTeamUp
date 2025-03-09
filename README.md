<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HackTeamUp - Find Your Hackathon Team</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fa;
            color: #333;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 2rem;
        }
        
        h1 {
            color: #2c3e50;
            margin-bottom: 1rem;
            text-align: center;
        }
        
        p {
            margin-bottom: 1.5rem;
            line-height: 1.6;
            text-align: center;
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-control {
            width: 100%;
            padding: 0.75rem;
            font-size: 1rem;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        
        .btn {
            display: inline-block;
            background-color: #3498db;
            color: white;
            padding: 0.75rem 1.5rem;
            font-size: 1rem;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .btn:hover {
            background-color: #2980b9;
        }
        
        .btn-container {
            text-align: center;
            margin-top: 2rem;
        }
        
        .language-btn {
            display: inline-block;
            padding: 0.5rem 1rem;
            margin: 0.5rem;
            background-color: white;
            border: 2px solid #3498db;
            border-radius: 30px;
            color: #3498db;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .language-btn.active {
            background-color: #3498db;
            color: white;
        }
        
        .languages-container {
            text-align: center;
            margin: 2rem 0;
        }
        
        .profile-card {
            background-color: white;
            border-radius: 8px;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            display: flex;
            align-items: center;
        }
        
        .profile-pic {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background-color: #ddd;
            margin-right: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: #777;
        }
        
        .profile-info {
            flex-grow: 1;
        }
        
        .profile-actions {
            margin-left: 1rem;
        }
        
        .tab-container {
            display: none;
        }
        
        .tab-container.active {
            display: block;
        }
        
        .message-box {
            width: 100%;
            min-height: 100px;
            margin-top: 1rem;
            padding: 0.75rem;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        
        .thank-you {
            text-align: center;
            padding: 3rem;
        }
    </style>
</head>
<body>
    <!-- Tab 1: Login/Signup Page -->
    <div id="login-tab" class="tab-container active">
        <div class="container">
            <h1>HackTeamUp</h1>
            <p>Find the perfect team for your next hackathon</p>
            
            <div id="login-form">
                <h2 style="text-align: center; margin-bottom: 1.5rem;">Login</h2>
                <div class="form-group">
                    <input type="email" class="form-control" placeholder="Email">
                </div>
                <div class="form-group">
                    <input type="password" class="form-control" placeholder="Password">
                </div>
                <div class="btn-container">
                    <button class="btn" onclick="switchTab('skills-tab')">Login</button>
                </div>
                <p style="margin-top: 1rem;">
                    Don't have an account? <a href="#" onclick="toggleForms()">Sign up</a>
                </p>
            </div>
            
            <div id="signup-form" style="display: none;">
                <h2 style="text-align: center; margin-bottom: 1.5rem;">Sign Up</h2>
                <div class="form-group">
                    <input type="text" class="form-control" placeholder="Full Name">
                </div>
                <div class="form-group">
                    <input type="email" class="form-control" placeholder="Email">
                </div>
                <div class="form-group">
                    <input type="password" class="form-control" placeholder="Password">
                </div>
                <div class="form-group">
                    <input type="password" class="form-control" placeholder="Confirm Password">
                </div>
                <div class="btn-container">
                    <button class="btn" onclick="switchTab('skills-tab')">Sign Up</button>
                </div>
                <p style="margin-top: 1rem;">
                    Already have an account? <a href="#" onclick="toggleForms()">Login</a>
                </p>
            </div>
        </div>
    </div>
    
    <!-- Tab 2: Programming Languages Selection -->
    <div id="skills-tab" class="tab-container">
        <div class="container">
            <h1>Select Your Skills</h1>
            <p>Choose the programming languages you're proficient in</p>
            
            <div class="languages-container">
                <div class="language-btn" onclick="toggleLanguage(this)">Python</div>
                <div class="language-btn" onclick="toggleLanguage(this)">JavaScript</div>
                <div class="language-btn" onclick="toggleLanguage(this)">Java</div>
                <div class="language-btn" onclick="toggleLanguage(this)">C++</div>
                <div class="language-btn" onclick="toggleLanguage(this)">C#</div>
                <div class="language-btn" onclick="toggleLanguage(this)">PHP</div>
                <div class="language-btn" onclick="toggleLanguage(this)">Ruby</div>
                <div class="language-btn" onclick="toggleLanguage(this)">Swift</div>
                <div class="language-btn" onclick="toggleLanguage(this)">Kotlin</div>
                <div class="language-btn" onclick="toggleLanguage(this)">Go</div>
                <div class="language-btn" onclick="toggleLanguage(this)">TypeScript</div>
                <div class="language-btn" onclick="toggleLanguage(this)">R</div>
            </div>
            
            <div class="btn-container">
                <button class="btn" onclick="switchTab('location-tab')">Next</button>
            </div>
        </div>
    </div>
    
    <!-- Tab 3: Location Selection -->
    <div id="location-tab" class="tab-container">
        <div class="container">
            <h1>Select Your Location</h1>
            <p>Choose the city where you're currently located</p>
            
            <div class="form-group">
                <select class="form-control" id="location-select">
                    <option value="" disabled selected>Select your city</option>
                    <option value="New Delhi">New Delhi</option>
                    <option value="Mumbai">Mumbai</option>
                    <option value="Chennai">Chennai</option>
                    <option value="Kolkata">Kolkata</option>
                    <option value="Bengaluru">Bengaluru</option>
                    <option value="Hyderabad">Hyderabad</option>
                    <option value="Gandhinagar">Gandhinagar</option>
                    <option value="Lucknow">Lucknow</option>
                    <option value="Bhopal">Bhopal</option>
                    <option value="Jaipur">Jaipur</option>
                    <option value="Chandigarh">Chandigarh</option>
                    <option value="Thiruvananthapuram">Thiruvananthapuram</option>
                    <option value="Patna">Patna</option>
                    <option value="Bhubaneswar">Bhubaneswar</option>
                    <option value="Raipur">Raipur</option>
                </select>
            </div>
            
            <div class="btn-container">
                <button class="btn" onclick="switchTab('team-skills-tab')">Next</button>
            </div>
        </div>
    </div>
    
    <!-- Tab 4: Team Skills Selection -->
    <div id="team-skills-tab" class="tab-container">
        <div class="container">
            <h1>LANGUAGES LOOKING FOR</h1>
            <p>Select the programming languages you want your teammates to know</p>
            
            <div class="languages-container">
                <div class="language-btn" onclick="toggleLanguage(this)">Python</div>
                <div class="language-btn" onclick="toggleLanguage(this)">JavaScript</div>
                <div class="language-btn" onclick="toggleLanguage(this)">Java</div>
                <div class="language-btn" onclick="toggleLanguage(this)">C++</div>
                <div class="language-btn" onclick="toggleLanguage(this)">C#</div>
                <div class="language-btn" onclick="toggleLanguage(this)">PHP</div>
                <div class="language-btn" onclick="toggleLanguage(this)">Ruby</div>
                <div class="language-btn" onclick="toggleLanguage(this)">Swift</div>
                <div class="language-btn" onclick="toggleLanguage(this)">Kotlin</div>
                <div class="language-btn" onclick="toggleLanguage(this)">Go</div>
                <div class="language-btn" onclick="toggleLanguage(this)">TypeScript</div>
                <div class="language-btn" onclick="toggleLanguage(this)">R</div>
            </div>
            
            <div class="btn-container">
                <button class="btn" onclick="switchTab('profiles-tab')">Okay</button>
            </div>
        </div>
    </div>
    
    <!-- Tab 5: Profiles Page -->
    <div id="profiles-tab" class="tab-container">
        <div class="container">
            <h1>Matching Profiles</h1>
            <p>Here are some developers who match your requirements</p>
            
            <div id="profiles-container">
                <!-- Profiles will be dynamically generated -->
            </div>
        </div>
    </div>
    
    <!-- Tab 6: Messaging Page -->
    <div id="messaging-tab" class="tab-container">
        <div class="container">
            <h1>Contact <span id="message-name"></span></h1>
            <p>Send a message to connect for the hackathon</p>
            
            <div class="profile-card">
                <div class="profile-pic" id="message-profile-pic"></div>
                <div class="profile-info">
                    <h3 id="message-profile-name"></h3>
                    <p id="message-profile-email"></p>
                    <p id="message-profile-location"></p>
                </div>
            </div>
            
            <div class="form-group">
                <label for="message">Your Message:</label>
                <textarea id="message" class="message-box" placeholder="Hi, I'm looking for a team for the upcoming hackathon. Would you like to collaborate?"></textarea>
            </div>
            
            <div class="btn-container">
                <button class="btn" onclick="switchTab('thank-you-tab')">Send Message</button>
            </div>
        </div>
    </div>
    
    <!-- Tab 7: Thank You Page -->
    <div id="thank-you-tab" class="tab-container">
        <div class="container">
            <div class="thank-you">
                <h1>Thank You!</h1>
                <p>Your message has been sent successfully.</p>
                <p>We hope you find the perfect team for your next hackathon!</p>
                <div class="btn-container">
                    <button class="btn" onclick="switchTab('profiles-tab')">Find More Teammates</button>
                </div>
            </div>
        </div>
    </div>
    
    <script>
        // Toggle between login and signup forms
        function toggleForms() {
            const loginForm = document.getElementById('login-form');
            const signupForm = document.getElementById('signup-form');
            
            if (loginForm.style.display === 'none') {
                loginForm.style.display = 'block';
                signupForm.style.display = 'none';
            } else {
                loginForm.style.display = 'none';
                signupForm.style.display = 'block';
            }
        }
        
        // Switch between tabs
        function switchTab(tabId) {
            const tabs = document.querySelectorAll('.tab-container');
            tabs.forEach(tab => {
                tab.classList.remove('active');
            });
            
            document.getElementById(tabId).classList.add('active');
            
            // If switching to profiles tab, generate profiles
            if (tabId === 'profiles-tab') {
                generateProfiles();
            }
        }
        
        // Toggle language selection
        function toggleLanguage(element) {
            element.classList.toggle('active');
        }
        
        // Generate random profiles based on selected location
        function generateProfiles() {
            const location = document.getElementById('location-select').value || 'Bengaluru';
            const profilesContainer = document.getElementById('profiles-container');
            profilesContainer.innerHTML = '';
            
            const names = ['Amit Kumar', 'Priya Sharma', 'Rahul Singh', 'Ananya Patel', 'Vikram Mehta'];
            const ages = [20, 21, 22, 23, 24];
            
            for (let i = 0; i < 5; i++) {
                const profile = document.createElement('div');
                profile.className = 'profile-card';
                
                const initial = names[i].charAt(0);
                const email = names[i].toLowerCase().replace(' ', '.') + '@gmail.com';
                
                profile.innerHTML = `
                    <div class="profile-pic">${initial}</div>
                    <div class="profile-info">
                        <h3>${names[i]}</h3>
                        <p>Age: ${ages[i]}</p>
                        <p>${email}</p>
                        <p>Location: ${location}</p>
                        <p>Skills: JavaScript, Python, React</p>
                    </div>
                    <div class="profile-actions">
                        <button class="btn" onclick="openMessagePage('${names[i]}', '${initial}', '${email}', '${location}')">Message</button>
                    </div>
                `;
                
                profilesContainer.appendChild(profile);
            }
        }
        
        // Open messaging page with selected profile
        function openMessagePage(name, initial, email, location) {
            document.getElementById('message-name').textContent = name;
            document.getElementById('message-profile-pic').textContent = initial;
            document.getElementById('message-profile-name').textContent = name;
            document.getElementById('message-profile-email').textContent = email;
            document.getElementById('message-profile-location').textContent = 'Location: ' + location;
            
            switchTab('messaging-tab');
        }
    </script>
</body>
</html>
