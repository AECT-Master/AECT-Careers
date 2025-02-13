<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Job Board</title>
    <style>
        .job-board-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            font-family: Arial, sans-serif;
        }

        .job-card {
            border: 1px solid #ddd;
            padding: 20px;
            margin-bottom: 20px;
            border-radius: 5px;
            background-color: #fff;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            cursor: pointer;
            transition: transform 0.2s;
        }

        .job-card:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }

        .job-preview {
            margin-bottom: 15px;
        }

        .job-full-description {
            display: none;
            padding-top: 15px;
            border-top: 1px solid #eee;
        }

        .job-title {
            font-size: 1.5em;
            color: #2c3e50;
            margin-bottom: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .job-company {
            font-weight: bold;
            color: #7f8c8d;
            margin-bottom: 10px;
        }

        .job-location {
            color: #95a5a6;
            margin-bottom: 10px;
        }

        .job-description {
            color: #34495e;
            line-height: 1.6;
            margin-bottom: 15px;
        }

        .job-requirements {
            color: #34495e;
            margin-bottom: 15px;
        }

        .apply-button {
            background-color: #3498db;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            text-decoration: none;
            display: inline-block;
        }

        .apply-button:hover {
            background-color: #2980b9;
        }

        .delete-button {
            background-color: #e74c3c;
            color: white;
            padding: 5px 10px;
            border: none;
            border-radius: 3px;
            cursor: pointer;
            margin-left: 10px;
        }

        .delete-button:hover {
            background-color: #c0392b;
        }

        .show-more {
            color: #3498db;
            cursor: pointer;
            text-decoration: underline;
            margin-top: 10px;
            display: inline-block;
        }

        /* Admin Panel Styles */
        .admin-panel {
            background-color: #f8f9fa;
            padding: 20px;
            margin-bottom: 20px;
            border-radius: 5px;
            display: none;
        }

        .admin-form {
            display: grid;
            gap: 10px;
        }

        .admin-form input, 
        .admin-form textarea {
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }

        .admin-form button {
            background-color: #2ecc71;
            color: white;
            padding: 10px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        .admin-form button:hover {
            background-color: #27ae60;
        }

        #adminLogin {
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div class="job-board-container">
        <!-- Admin Login -->
        <div id="adminLogin">
            <input type="password" id="adminPassword" placeholder="Admin Password">
            <button onclick="checkPassword()">Login</button>
        </div>

        <!-- Admin Panel -->
        <div id="adminPanel" class="admin-panel">
            <h2>Add New Job</h2>
            <form id="jobForm" class="admin-form">
                <input type="text" id="title" placeholder="Job Title" required>
                <input type="text" id="company" placeholder="Company Name" required>
                <input type="text" id="location" placeholder="Location" required>
                <textarea id="description" placeholder="Job Description" required></textarea>
                <textarea id="requirements" placeholder="Requirements" required></textarea>
                <input type="url" id="applyLink" placeholder="Application Link" required>
                <button type="submit">Add Job</button>
            </form>
        </div>

        <!-- Job Listings -->
        <div id="jobListings"></div>
    </div>

    <script>
        // Set your admin password here
        const ADMIN_PASSWORD = 'your_secure_password_here';
        
        // Check admin password
        function checkPassword() {
            const password = document.getElementById('adminPassword').value;
            if (password === ADMIN_PASSWORD) {
                document.getElementById('adminPanel').style.display = 'block';
                document.getElementById('adminLogin').style.display = 'none';
            } else {
                alert('Incorrect password');
            }
        }

        // Initialize jobs from localStorage or start with empty array
        let jobs = JSON.parse(localStorage.getItem('jobs')) || [];

        // Add new job
        document.getElementById('jobForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const newJob = {
                id: Date.now(),
                title: document.getElementById('title').value,
                company: document.getElementById('company').value,
                location: document.getElementById('location').value,
                description: document.getElementById('description').value,
                requirements: document.getElementById('requirements').value,
                applyLink: document.getElementById('applyLink').value,
                date: new Date().toISOString()
            };

            jobs.push(newJob);
            // Sort jobs by date (newest first)
            jobs.sort((a, b) => new Date(b.date) - new Date(a.date));
            localStorage.setItem('jobs', JSON.stringify(jobs));
            
            this.reset();
            displayJobs();
        });

        // Delete job
        function deleteJob(id, event) {
            event.stopPropagation(); // Prevent triggering the job card click
            if (confirm('Are you sure you want to delete this job posting?')) {
                jobs = jobs.filter(job => job.id !== id);
                localStorage.setItem('jobs', JSON.stringify(jobs));
                displayJobs();
            }
        }

        // Toggle job description
        function toggleDescription(id) {
            const fullDescription = document.getElementById(`full-description-${id}`);
            const preview = document.getElementById(`preview-${id}`);
            const showMoreBtn = document.getElementById(`show-more-${id}`);
            
            if (fullDescription.style.display === 'none') {
                fullDescription.style.display = 'block';
                preview.style.display = 'none';
                showMoreBtn.textContent = 'Show Less';
            } else {
                fullDescription.style.display = 'none';
                preview.style.display = 'block';
                showMoreBtn.textContent = 'Show More';
            }
        }

        // Display jobs
        function displayJobs() {
            const jobListings = document.getElementById('jobListings');
            jobListings.innerHTML = '';

            jobs.forEach(job => {
                const jobCard = document.createElement('div');
                jobCard.className = 'job-card';
                
                // Create preview text (first 150 characters)
                const previewText = job.description.substring(0, 150) + '...';
                
                const isAdmin = document.getElementById('adminPanel').style.display === 'block';
                const deleteButton = isAdmin ? 
                    `<button class="delete-button" onclick="deleteJob(${job.id}, event)">Delete</button>` : '';

                jobCard.innerHTML = `
                    <div class="job-title">
                        ${job.title}
                        ${deleteButton}
                    </div>
                    <div class="job-company">${job.company}</div>
                    <div class="job-location">${job.location}</div>
                    
                    <div id="preview-${job.id}" class="job-preview">
                        <div class="job-description">${previewText}</div>
                    </div>

                    <div id="full-description-${job.id}" class="job-full-description" style="display: none;">
                        <div class="job-description">${job.description}</div>
                        <div class="job-requirements"><strong>Requirements:</strong><br>${job.requirements}</div>
                        <a href="${job.applyLink}" target="_blank" class="apply-button">Apply Now</a>
                    </div>

                    <span id="show-more-${job.id}" class="show-more" onclick="toggleDescription(${job.id})">Show More</span>
                `;

                jobListings.appendChild(jobCard);
            });
        }

        // Initial display
        displayJobs();
    </script>
</body>
</html>
