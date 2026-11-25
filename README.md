<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Portal</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            background-color: #f4f6fb;
            color: #333;
        }

        /* Sidebar */
        .sidebar {
            width: 240px;
            height: 100vh;
            background-color: #172554;
            color: white;
            position: fixed;
            padding: 25px 15px;
        }

        .sidebar h2 {
            text-align: center;
            margin-bottom: 35px;
        }

        .sidebar button {
            display: block;
            width: 100%;
            padding: 14px;
            margin-bottom: 10px;
            border: none;
            background: transparent;
            color: white;
            text-align: left;
            cursor: pointer;
            border-radius: 8px;
            font-size: 15px;
        }

        .sidebar button:hover,
        .sidebar button.active {
            background-color: #3157d5;
        }

        /* Main Content */
        .main {
            margin-left: 240px;
            padding: 30px;
        }

        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }

        header h1 {
            color: #172554;
        }

        /* Welcome Section */
        .welcome {
            background: linear-gradient(120deg, #2948b7, #5578ed);
            color: white;
            padding: 30px;
            border-radius: 12px;
            margin-bottom: 25px;
        }

        .welcome h2 {
            margin-bottom: 10px;
        }

        /* Dashboard Cards */
        .cards {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 15px;
            margin-bottom: 25px;
        }

        .card {
            background-color: white;
            padding: 22px;
            border-radius: 12px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.05);
        }

        .card h3 {
            font-size: 14px;
            color: #777;
            margin-bottom: 15px;
        }

        .card h2 {
            color: #3157d5;
            font-size: 28px;
        }

        /* Content Sections */
        .section {
            display: none;
            background-color: white;
            padding: 25px;
            border-radius: 12px;
            margin-bottom: 20px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.05);
        }

        .section.active {
            display: block;
        }

        .section h2 {
            margin-bottom: 20px;
            color: #172554;
        }

        /* Tables */
        table {
            width: 100%;
            border-collapse: collapse;
        }

        th, td {
            padding: 14px;
            text-align: left;
            border-bottom: 1px solid #eee;
        }

        th {
            background-color: #edf2ff;
            color: #172554;
        }

        /* Announcements */
        .announcement {
            padding: 15px 0;
            border-bottom: 1px solid #eee;
        }

        .announcement h3 {
            color: #3157d5;
            margin-bottom: 8px;
        }

        .announcement p {
            color: #666;
            line-height: 1.5;
        }

        /* Profile */
        .profile p {
            margin: 15px 0;
            font-size: 16px;
        }

        /* Responsive */
        @media (max-width: 850px) {
            .cards {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 600px) {
            .sidebar {
                width: 100%;
                height: auto;
                position: relative;
            }

            .sidebar h2 {
                margin-bottom: 15px;
            }

            .main {
                margin-left: 0;
                padding: 18px;
            }

            .sidebar button {
                display: inline-block;
                width: auto;
                font-size: 12px;
            }

            .cards {
                grid-template-columns: repeat(2, 1fr);
            }

            header h1 {
                font-size: 22px;
            }

            table {
                min-width: 500px;
            }

            .section {
                overflow-x: auto;
            }
        }
    </style>
</head>

<body>

    <!-- Sidebar -->
    <div class="sidebar">
        <h2>CampusHub</h2>

        <button class="active" onclick="showPage('dashboard', this)">
            Dashboard
        </button>

        <button onclick="showPage('schedule', this)">
            Class Schedule
        </button>

        <button onclick="showPage('grades', this)">
            Grades
        </button>

        <button onclick="showPage('announcements', this)">
            Announcements
        </button>

        <button onclick="showPage('profile', this)">
            Student Profile
        </button>
    </div>

    <!-- Main Content -->
    <div class="main">

        <header>
            <h1 id="pageTitle">Dashboard</h1>
            <p>Welcome, Jordan Reyes!</p>
        </header>

        <!-- Dashboard -->
        <div id="dashboard" class="section active">

            <div class="welcome">
                <h2>Welcome Back, Jordan!</h2>
                <p>
                    Welcome to your student portal.
                    Check your academic information here.
                </p>
            </div>

            <div class="cards">

                <div class="card">
                    <h3>Enrolled Subjects</h3>
                    <h2>6</h2>
                </div>

                <div class="card">
                    <h3>Average Grade</h3>
                    <h2>92.5</h2>
                </div>

                <div class="card">
                    <h3>Upcoming Classes</h3>
                    <h2>3</h2>
                </div>

                <div class="card">
                    <h3>Announcements</h3>
                    <h2>2</h2>
                </div>

            </div>

            <h2>Today's Classes</h2>

            <table>
                <tr>
                    <th>Time</th>
                    <th>Subject</th>
                    <th>Room</th>
                </tr>

                <tr>
                    <td>8:00 AM</td>
                    <td>Introduction to Computing</td>
                    <td>Room 204</td>
                </tr>

                <tr>
                    <td>10:00 AM</td>
                    <td>Programming Fundamentals</td>
                    <td>Computer Lab 1</td>
                </tr>

                <tr>
                    <td>1:00 PM</td>
                    <td>Understanding the Self</td>
                    <td>Room 108</td>
                </tr>
            </table>

        </div>

        <!-- Class Schedule -->
        <div id="schedule" class="section">

            <h2>Class Schedule</h2>

            <table>
                <tr>
                    <th>Day</th>
                    <th>Time</th>
                    <th>Subject</th>
                    <th>Room</th>
                </tr>

                <tr>
                    <td>Monday</td>
                    <td>8:00 AM - 9:30 AM</td>
                    <td>Introduction to Computing</td>
                    <td>204</td>
                </tr>

                <tr>
                    <td>Tuesday</td>
                    <td>10:00 AM - 11:30 AM</td>
                    <td>Programming Fundamentals</td>
                    <td>Lab 1</td>
                </tr>

                <tr>
                    <td>Wednesday</td>
                    <td>1:00 PM - 2:30 PM</td>
                    <td>Understanding the Self</td>
                    <td>108</td>
                </tr>

                <tr>
                    <td>Thursday</td>
                    <td>8:00 AM - 9:30 AM</td>
                    <td>Mathematics</td>
                    <td>205</td>
                </tr>

                <tr>
                    <td>Friday</td>
                    <td>10:00 AM - 11:30 AM</td>
                    <td>Purposive Communication</td>
                    <td>110</td>
                </tr>
            </table>

        </div>

        <!-- Grades -->
        <div id="grades" class="section">

            <h2>My Grades</h2>

            <table>
                <tr>
                    <th>Subject</th>
                    <th>Grade</th>
                    <th>Status</th>
                </tr>

                <tr>
                    <td>Introduction to Computing</td>
                    <td>94</td>
                    <td>Passed</td>
                </tr>

                <tr>
                    <td>Programming Fundamentals</td>
                    <td>91</td>
                    <td>Passed</td>
                </tr>

                <tr>
                    <td>Mathematics</td>
                    <td>92</td>
                    <td>Passed</td>
                </tr>

                <tr>
                    <td>Understanding the Self</td>
                    <td>93</td>
                    <td>Passed</td>
                </tr>

                <tr>
                    <td>Purposive Communication</td>
                    <td>92</td>
                    <td>Passed</td>
                </tr>
            </table>

        </div>

        <!-- Announcements -->
        <div id="announcements" class="section">

            <h2>Announcements</h2>

            <div class="announcement">
                <h3>Library Schedule Update</h3>
                <p>
                    The library will follow its regular
                    operating hours this week.
                </p>
            </div>

            <div class="announcement">
                <h3>Project Submission Reminder</h3>
                <p>
                    Please check your course pages for
                    upcoming project deadlines.
                </p>
            </div>

            <div class="announcement">
                <h3>Student Services Information</h3>
                <p>
                    Visit the student services office
                    for academic assistance.
                </p>
            </div>

        </div>

        <!-- Student Profile -->
        <div id="profile" class="section">

            <h2>Student Profile</h2>

            <div class="profile">

                <p><strong>Name:</strong> Jordan Reyes</p>

                <p><strong>Student ID:</strong> 2026-000123</p>

                <p><strong>Course:</strong> BS Information Technology</p>

                <p><strong>Year Level:</strong> 1st Year</p>

                <p><strong>Academic Year:</strong> 2026-2027</p>

                <p><strong>Email:</strong> jordan.reyes@example.com</p>

            </div>

        </div>

    </div>

    <!-- JavaScript -->
    <script>

        function showPage(page, button) {

            // Hide all sections
            let sections = document.querySelectorAll(".section");

            sections.forEach(function(section) {
                section.classList.remove("active");
            });

            // Remove active status from buttons
            let buttons = document.querySelectorAll(".sidebar button");

            buttons.forEach(function(btn) {
                btn.classList.remove("active");
            });

            // Show selected section
            document.getElementById(page).classList.add("active");

            // Highlight selected button
            button.classList.add("active");

            // Change page title
            let titles = {
                dashboard: "Dashboard",
                schedule: "Class Schedule",
                grades: "Grades",
                announcements: "Announcements",
                profile: "Student Profile"
            };

            document.getElementById("pageTitle").textContent = titles[page];

        }

    </script>

</body>
</html>
