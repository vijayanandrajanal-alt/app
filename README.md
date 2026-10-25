# app
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSE Compass Clone | Student Portal</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --sidebar-bg: #0f172a;
            --main-bg: #f1f5f9;
            --accent-blue: #3b82f6;
            --text-main: #1e293b;
            --text-muted: #64748b;
            --white: #ffffff;
            --transition: all 0.3s ease;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            background-color: var(--main-bg);
            color: var(--text-main);
            display: flex;
            height: 100vh;
            overflow: hidden;
        }

        /* --- SIDEBAR --- */
        .sidebar {
            width: 260px;
            background-color: var(--sidebar-bg);
            color: white;
            display: flex;
            flex-direction: column;
            padding: 20px;
            transition: var(--transition);
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 800;
            margin-bottom: 40px;
            display: flex;
            align-items: center;
            gap: 12px;
            color: var(--accent-blue);
        }

        .nav-menu {
            list-style: none;
            flex-grow: 1;
        }

        .nav-item {
            padding: 12px 15px;
            margin-bottom: 8px;
            border-radius: 8px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 12px;
            transition: var(--transition);
            color: #cbd5e1;
            text-decoration: none;
        }

        .nav-item:hover, .nav-item.active {
            background-color: rgba(59, 130, 246, 0.15);
            color: white;
        }

        .nav-item.active {
            background-color: var(--accent-blue);
        }

        /* --- MAIN CONTENT --- */
        .main-content {
            flex-grow: 1;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
        }

        /* Header Area */
        header {
            background: var(--white);
            padding: 20px 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
        }

        .search-bar {
            position: relative;
            width: 400px;
        }

        .search-bar input {
            width: 100%;
            padding: 10px 15px 10px 40px;
            border: 1px solid #e2e8f0;
            border-radius: 10px;
            outline: none;
            font-size: 0.9rem;
            transition: var(--transition);
        }

        .search-bar input:focus { border-color: var(--accent-blue); box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.1); }

        .search-bar i {
            position: absolute;
            left: 12px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-muted);
        }

        .user-profile {
            display: flex;
            align-items: center;
            gap: 12px;
            font-weight: 500;
        }

        .user-avatar {
            width: 35px;
            height: 35px;
            background: var(--accent-blue);
            border-radius: 50%;
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* Dashboard Grid */
        .dashboard {
            padding: 40px;
        }

        .welcome-section {
            margin-bottom: 30px;
        }

        .welcome-section h1 { font-size: 1.8rem; margin-bottom: 5px; }
        .welcome-section p { color: var(--text-muted); }

        .resource-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
        }

        .card {
            background: var(--white);
            padding: 25px;
            border-radius: 16px;
            box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1);
            transition: var(--transition);
            border: 1px solid transparent;
            cursor: pointer;
        }

        .card:hover {
            transform: translateY(-5px);
            border-color: var(--accent-blue);
        }

        .card-icon {
            width: 45px;
            height: 45px;
            background: #eff6ff;
            color: var(--accent-blue);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            margin-bottom: 20px;
        }

        .card h3 { margin-bottom: 10px; font-size: 1.1rem; }
        .card p { color: var(--text-muted); font-size: 0.9rem; line-height: 1.5; }

    </style>
</head>
<body>

    <!-- Sidebar -->
    <div class="sidebar">
        <div class="logo">
            <i class="fas fa-compass"></i> CSE Compass
        </div>
        <ul class="nav-menu">
            <li><a href="#" class="nav-item active"><i class="fas fa-home"></i> Dashboard</a></li>
            <li><a href="#" class="nav-item"><i class="fas fa-map"></i> Learning Roadmaps</a></li>
            <li><a href="#" class="nav-item"><i class="fas fa-book"></i> Digital Library</a></li>
            <li><a href="#" class="nav-item"><i class="fas fa-code"></i> Project Ideas</a></li>
            <li><a href="#" class="nav-item"><i class="fas fa-graduation-cap"></i> Certification</a></li>
            <li><a href="#" class="nav-item"><i class="fas fa-cog"></i> Settings</a></li>
        </ul>
    </div>

    <!-- Main Content -->
    <div class="main-content">
        <header>
            <div class="search-bar">
                <i class="fas fa-search"></i>
                <input type="text" placeholder="Search resources, notes, tools...">
            </div>
            <div class="user-profile">
                <span>Student Account</span>
                <div class="user-avatar">JS</div>
            </div>
        </header>

        <div class="dashboard">
            <div class="welcome-section">
                <h1>Welcome back, Scholar! 👋</h1>
                <p>Explore the curated path to becoming a Software Engineer.</p>
            </div>

            <div class="resource-grid">
                <!-- Resource Card -->
                <div class="card">
                    <div class="card-icon"><i class="fas fa-brain"></i></div>
                    <h3>Data Structures</h3>
                    <p>Arrays, Linked Lists, Trees and Graphs. Essential for technical interviews.</p>
                </div>

                <div class="card">
                    <div class="card-icon"><i class="fas fa-microchip"></i></div>
                    <h3>Computer OS</h3>
                    <p>Process management, Memory allocation and File systems guide.</p>
                </div>

                <div class="card">
                    <div class="card-icon"><i class="fas fa-server"></i></div>
                    <h3>Backend Dev</h3>
                    <p>Node.js, Django and Spring Boot roadmap with database integration.</p>
                </div>

                <div class="card">
                    <div class="card-icon"><i class="fas fa-laptop-code"></i></div>
                    <h3>Frontend Dev</h3>
                    <p>Modern React, Tailwind CSS and TypeScript masterclass resources.</p>
                </div>

                <div class="card">
                    <div class="card-icon"><i class="fas fa-shield-virus"></i></div>
                    <h3>Cyber Security</h3>
                    <p>OWASP Top 10, Network Security and Penetration testing basics.</p>
                </div>

                <div class="card">
                    <div class="card-icon"><i class="fas fa-database"></i></div>
                    <h3>DBMS</h3>
                    <p>SQL vs NoSQL. Normalization and Indexing optimization techniques.</p>
                </div>
            </div>
        </div>
    </div>

</body>
</html>
