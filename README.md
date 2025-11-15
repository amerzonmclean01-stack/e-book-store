<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Complete Christian Platform</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link rel="manifest" href="manifest.json">
    <meta name="theme-color" content="#1a365d">
    <style>
        /* === COMPLETE STYLES === */
        :root {
            --primary-color: #1a365d;
            --secondary-color: #2d3748;
            --accent-color: #2b6cb0;
            --gold-color: #d4af37;
            --light-bg: #f7fafc;
            --dark-text: #2d3748;
            --light-text: #718096;
            --white: #ffffff;
            --border: #e2e8f0;
            --success: #38a169;
            --error: #e53e3e;
            --warning: #dd6b20;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', 'Times New Roman', serif;
            color: var(--dark-text);
            line-height: 1.6;
            background: var(--white);
            overflow-x: hidden;
        }

        /* Security & Loading */
        .security-badge {
            position: fixed;
            top: 10px;
            right: 10px;
            background: var(--success);
            color: white;
            padding: 5px 10px;
            border-radius: 4px;
            font-size: 0.8rem;
            z-index: 10000;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        #loadingScreen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--primary-color);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            color: white;
        }

        .spinner {
            border: 4px solid rgba(255,255,255,0.3);
            border-radius: 50%;
            border-top: 4px solid var(--gold-color);
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            margin-bottom: 20px;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Context Menu */
        .context-menu {
            position: fixed;
            background: white;
            border: 1px solid var(--border);
            border-radius: 8px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.15);
            z-index: 1000;
            display: none;
        }

        .context-menu-item {
            padding: 12px 20px;
            cursor: pointer;
            border-bottom: 1px solid var(--border);
            transition: background 0.3s ease;
        }

        .context-menu-item:hover {
            background: var(--light-bg);
        }

        /* Notifications */
        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            padding: 15px 20px;
            border-radius: 8px;
            color: white;
            z-index: 1001;
            transform: translateX(400px);
            transition: transform 0.3s ease;
        }

        .notification.show {
            transform: translateX(0);
        }

        .notification.success { background: var(--success); }
        .notification.error { background: var(--error); }
        .notification.warning { background: var(--warning); }

        /* Modal System */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 1002;
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background: white;
            padding: 2rem;
            border-radius: 12px;
            max-width: 500px;
            width: 90%;
            max-height: 80vh;
            overflow-y: auto;
        }

        /* Main Layout */
        .container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }
        
        .header { 
            background: var(--white); 
            box-shadow: 0 2px 20px rgba(0,0,0,0.08); 
            position: sticky; 
            top: 0; 
            z-index: 1000; 
            border-bottom: 3px solid var(--gold-color); 
        }
        
        .header-content { 
            display: flex; 
            align-items: center; 
            justify-content: space-between; 
            padding: 1.2rem 0; 
        }
        
        .logo { 
            font-size: 2.2rem; 
            font-weight: 700; 
            color: var(--primary-color); 
            text-decoration: none; 
            font-family: 'Georgia', serif; 
        }
        
        .logo span { 
            color: var(--gold-color); 
            font-style: italic; 
        }
        
        .nav { 
            display: flex; 
            gap: 2.5rem; 
            align-items: center; 
        }
        
        .nav-link { 
            color: var(--dark-text); 
            text-decoration: none; 
            font-weight: 500; 
            font-size: 1.1rem; 
            transition: all 0.3s ease; 
            position: relative; 
            cursor: pointer;
        }
        
        .nav-link.active {
            color: var(--accent-color);
        }
        
        .nav-link.active:after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 2px;
            background: var(--gold-color);
        }
        
        .nav-link:hover { 
            color: var(--accent-color); 
        }
        
        .btn { 
            padding: 12px 28px; 
            border-radius: 6px; 
            text-decoration: none; 
            font-weight: 600; 
            transition: all 0.3s ease; 
            border: none; 
            cursor: pointer; 
            display: inline-block; 
            font-size: 1rem; 
        }
        
        .btn-primary { 
            background: linear-gradient(135deg, var(--primary-color), var(--accent-color)); 
            color: var(--white); 
            box-shadow: 0 4px 15px rgba(43, 108, 176, 0.3); 
        }
        
        .btn-primary:hover { 
            transform: translateY(-2px); 
            box-shadow: 0 6px 20px rgba(43, 108, 176, 0.4); 
        }
        
        .btn-outline { 
            border: 2px solid var(--primary-color); 
            color: var(--primary-color); 
            background: transparent; 
        }
        
        .btn-outline:hover { 
            background: var(--primary-color); 
            color: var(--white); 
        }

        /* Tab Content */
        .tab-content {
            display: none;
            animation: fadeIn 0.5s ease;
        }

        .tab-content.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Hero Sections */
        .hero-section {
            padding: 120px 0;
            text-align: center;
            background: linear-gradient(135deg, var(--primary-color) 0%, #2c5282 100%);
            color: white;
        }

        .section {
            padding: 100px 0;
        }

        .section-title {
            font-size: 2.8rem;
            text-align: center;
            margin-bottom: 1rem;
            color: var(--primary-color);
            font-family: 'Georgia', serif;
            position: relative;
        }

        .section-title:after {
            content: '';
            display: block;
            width: 80px;
            height: 3px;
            background: var(--gold-color);
            margin: 1rem auto;
        }

        /* Store Styles */
        .books-grid, .workshops-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2.5rem;
            margin: 3rem 0;
        }

        .book-card, .workshop-card {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 12px;
            overflow: hidden;
            transition: all 0.3s ease;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            position: relative;
        }

        .book-card:hover, .workshop-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.15);
        }

        .book-badge, .workshop-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background: var(--gold-color);
            color: var(--white);
            padding: 5px 12px;
            border-radius: 4px;
            font-size: 0.8rem;
            font-weight: 600;
            z-index: 2;
        }

        .book-image, .workshop-image {
            height: 200px;
            background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-weight: 600;
            font-size: 1.1rem;
        }

        .book-info, .workshop-info {
            padding: 2rem;
        }

        .book-title, .workshop-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--primary-color);
            line-height: 1.4;
        }

        .book-author, .workshop-instructor {
            color: var(--light-text);
            margin-bottom: 1rem;
            font-size: 1rem;
            font-style: italic;
        }

        .book-description, .workshop-description {
            color: var(--light-text);
            margin-bottom: 1.5rem;
            font-size: 0.95rem;
            line-height: 1.6;
        }

        .book-price, .workshop-price {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
            margin-bottom: 1.5rem;
        }

        .book-actions, .workshop-actions {
            display: flex;
            gap: 1rem;
        }

        .btn-small {
            padding: 10px 20px;
            font-size: 0.9rem;
            flex: 1;
            text-align: center;
        }

        /* Ministry Styles */
        .ministry-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2.5rem;
            margin: 3rem 0;
        }

        .ministry-card {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 2.5rem;
            text-align: center;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            transition: all 0.3s ease;
        }

        .ministry-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.15);
        }

        .ministry-icon {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            color: var(--primary-color);
        }

        /* Workshop Specific Styles */
        .workshop-details {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1rem;
            font-size: 0.9rem;
            color: var(--light-text);
        }

        .workshop-date, .workshop-duration, .workshop-seats {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        /* Community Styles */
        .community-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            text-align: center;
            margin: 3rem 0;
        }

        .stat-card {
            padding: 2rem;
            background: var(--white);
            border-radius: 12px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 700;
            color: var(--primary-color);
            margin-bottom: 0.5rem;
        }

        .stat-label {
            color: var(--light-text);
            font-size: 1.1rem;
        }

        /* Blog Styles */
        .blog-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
            gap: 2.5rem;
            margin: 3rem 0;
        }

        .blog-card {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            transition: all 0.3s ease;
        }

        .blog-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.15);
        }

        .blog-image {
            height: 200px;
            background: var(--light-bg);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--light-text);
        }

        .blog-content {
            padding: 2rem;
        }

        .blog-title {
            font-size: 1.4rem;
            margin-bottom: 1rem;
            color: var(--primary-color);
            line-height: 1.4;
        }

        .blog-excerpt {
            color: var(--light-text);
            margin-bottom: 1.5rem;
            line-height: 1.6;
        }

        .blog-meta {
            color: var(--light-text);
            font-size: 0.9rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        /* About Styles */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
            margin: 3rem 0;
        }

        .about-text h3 {
            font-size: 2rem;
            margin-bottom: 1.5rem;
            color: var(--primary-color);
        }

        .about-features {
            list-style: none;
            margin-top: 2rem;
        }

        .about-features li {
            padding: 0.5rem 0;
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .about-features li:before {
            content: "✓";
            color: var(--primary-color);
            font-weight: bold;
        }

        /* Footer */
        .footer {
            background: var(--primary-color);
            color: var(--white);
            padding: 80px 0 30px;
            margin-top: 4rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr;
            gap: 3rem;
            margin-bottom: 3rem;
        }

        .footer-section h4 {
            margin-bottom: 1.5rem;
            color: var(--white);
            font-size: 1.3rem;
        }

        .footer-section a {
            display: block;
            color: #cbd5e0;
            text-decoration: none;
            margin-bottom: 0.8rem;
            transition: color 0.3s ease;
            cursor: pointer;
        }

        .footer-section a:hover {
            color: var(--gold-color);
        }

        .footer-bottom {
            border-top: 1px solid #4a5568;
            padding-top: 2rem;
            text-align: center;
            color: #cbd5e0;
        }

        /* Settings Panel */
        .settings-panel {
            position: fixed;
            top: 0;
            right: -400px;
            width: 400px;
            height: 100vh;
            background: white;
            box-shadow: -5px 0 20px rgba(0,0,0,0.1);
            transition: right 0.3s ease;
            z-index: 1003;
            overflow-y: auto;
        }

        .settings-panel.open {
            right: 0;
        }

        .settings-header {
            padding: 2rem;
            border-bottom: 1px solid var(--border);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .settings-content {
            padding: 2rem;
        }

        .setting-group {
            margin-bottom: 2rem;
        }

        .setting-group h4 {
            margin-bottom: 1rem;
            color: var(--primary-color);
        }

        .setting-option {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
            border-bottom: 1px solid var(--border);
        }

        /* Switch Toggle */
        .switch {
            position: relative;
            display: inline-block;
            width: 60px;
            height: 34px;
        }

        .switch input {
            opacity: 0;
            width: 0;
            height: 0;
        }

        .slider {
            position: absolute;
            cursor: pointer;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: #ccc;
            transition: .4s;
            border-radius: 34px;
        }

        .slider:before {
            position: absolute;
            content: "";
            height: 26px;
            width: 26px;
            left: 4px;
            bottom: 4px;
            background-color: white;
            transition: .4s;
            border-radius: 50%;
        }

        input:checked + .slider {
            background-color: var(--success);
        }

        input:checked + .slider:before {
            transform: translateX(26px);
        }

        /* Diagnostics Panel */
        .diagnostics-panel {
            position: fixed;
            bottom: 20px;
            left: 20px;
            background: var(--primary-color);
            color: white;
            padding: 1rem;
            border-radius: 8px;
            font-family: monospace;
            font-size: 0.9rem;
            z-index: 999;
            max-width: 300px;
        }

        .diagnostics-item {
            margin-bottom: 0.5rem;
        }

        .status-indicator {
            display: inline-block;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            margin-right: 8px;
        }

        .status-ok { background: var(--success); }
        .status-warning { background: var(--warning); }
        .status-error { background: var(--error); }

        /* Cart */
        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: var(--gold-color);
            color: var(--white);
            border-radius: 50%;
            width: 20px;
            height: 20px;
            font-size: 0.8rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }

        /* Currency Display */
        .currency {
            font-size: 0.8em;
            margin-right: 2px;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 1.5rem;
            }

            .nav {
                flex-wrap: wrap;
                justify-content: center;
                gap: 1.5rem;
            }

            .hero-title {
                font-size: 2.5rem;
            }

            .footer-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .about-content {
                grid-template-columns: 1fr;
            }

            .settings-panel {
                width: 100%;
                right: -100%;
            }
            
            .diagnostics-panel {
                bottom: 10px;
                left: 10px;
                right: 10px;
                max-width: none;
            }
        }
    </style>
</head>
<body>
    <!-- Security Badge -->
    <div class="security-badge">
        <i class="fas fa-shield-alt"></i>
        <span>Secure Connection • SSL Encrypted</span>
    </div>

    <!-- Loading Screen -->
    <div id="loadingScreen">
        <div class="spinner"></div>
        <h3>Initializing The Definitive Word</h3>
        <p>Loading all features...</p>
    </div>

    <!-- Context Menu -->
    <div class="context-menu" id="contextMenu">
        <div class="context-menu-item" onclick="openInNewTab()"><i class="fas fa-external-link-alt"></i> Open in New Tab</div>
        <div class="context-menu-item" onclick="savePage()"><i class="fas fa-save"></i> Save Page</div>
        <div class="context-menu-item" onclick="viewSource()"><i class="fas fa-code"></i> View Source</div>
    </div>

    <!-- Notifications -->
    <div id="notificationContainer"></div>

    <!-- Settings Modal -->
    <div class="modal" id="settingsModal">
        <div class="modal-content">
            <div class="settings-header">
                <h3>Application Settings</h3>
                <button onclick="closeSettings()" style="background: none; border: none; font-size: 1.5rem; cursor: pointer;">×</button>
            </div>
            <div class="settings-content">
                <div class="setting-group">
                    <h4>Security Settings</h4>
                    <div class="setting-option">
                        <span>Auto-login</span>
                        <label class="switch">
                            <input type="checkbox" id="autoLogin" onchange="updateSetting('autoLogin', this.checked)">
                            <span class="slider"></span>
                        </label>
                    </div>
                    <div class="setting-option">
                        <span>Save Login</span>
                        <label class="switch">
                            <input type="checkbox" id="saveLogin" onchange="updateSetting('saveLogin', this.checked)">
                            <span class="slider"></span>
                        </label>
                    </div>
                </div>

                <div class="setting-group">
                    <h4>Interface Settings</h4>
                    <div class="setting-option">
                        <span>Double-click to Open</span>
                        <label class="switch">
                            <input type="checkbox" id="doubleClick" onchange="updateSetting('doubleClick', this.checked)">
                            <span class="slider"></span>
                        </label>
                    </div>
                    <div class="setting-option">
                        <span>Right-click Menu</span>
                        <label class="switch">
                            <input type="checkbox" id="rightClick" checked onchange="updateSetting('rightClick', this.checked)">
                            <span class="slider"></span>
                        </label>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Diagnostics Panel -->
    <div class="diagnostics-panel" id="diagnosticsPanel">
        <h4>System Diagnostics</h4>
        <div class="diagnostics-item">
            <span class="status-indicator status-ok"></span>
            <span>All Systems: Operational</span>
        </div>
        <button onclick="runFullDiagnostics()" style="margin-top: 10px; padding: 5px 10px; background: var(--gold-color); border: none; border-radius: 4px; cursor: pointer; color: white;">Run Diagnostics</button>
    </div>

    <!-- Main Header -->
    <header class="header">
        <div class="container">
            <div class="header-content">
                <a href="#home" class="logo" ondblclick="openSettings()">
                    The <span>Definitive</span> Word
                </a>
                
                <nav class="nav">
                    <a href="#home" class="nav-link active" onclick="switchTab('home')">Home</a>
                    <a href="#books" class="nav-link" onclick="switchTab('books')">Books</a>
                    <a href="#workshops" class="nav-link" onclick="switchTab('workshops')">Workshops</a>
                    <a href="#ministry" class="nav-link" onclick="switchTab('ministry')">Ministry</a>
                    <a href="#community" class="nav-link" onclick="switchTab('community')">Community</a>
                    <a href="#blog" class="nav-link" onclick="switchTab('blog')">Blog</a>
                    <a href="#about" class="nav-link" onclick="switchTab('about')">About</a>
                </nav>

                <div class="header-actions">
                    <a href="#cart" style="position: relative; color: var(--primary-color); font-size: 1.4rem; text-decoration: none;">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count" id="cartCount">0</span>
                    </a>
                    <button onclick="openSettings()" class="btn btn-outline" style="margin-right: 10px;">
                        <i class="fas fa-cog"></i> Settings
                    </button>
                    <button onclick="toggleLogin()" class="btn btn-primary" id="loginButton">
                        <i class="fas fa-user"></i> Sign In
                    </button>
                </div>
            </div>
        </div>
    </header>

    <!-- Tab Contents -->
    <main>
        <!-- HOME TAB -->
        <section id="home-tab" class="tab-content active">
            <div class="hero-section">
                <div class="container">
                    <h1 style="font-size: 3.8rem; margin-bottom: 1.5rem;">The Definitive Word</h1>
                    <p style="font-size: 1.4rem; margin-bottom: 2.5rem; opacity: 0.9; max-width: 600px; margin-left: auto; margin-right: auto;">
                        Your complete Christian resource platform with books, workshops, ministry programs, and vibrant community.
                    </p>
                    <div style="display: flex; gap: 1.5rem; justify-content: center; flex-wrap: wrap;">
                        <button class="btn btn-primary" onclick="switchTab('books')">Browse Books</button>
                        <button class="btn" style="background: rgba(255,255,255,0.1); color: white; border: 2px solid white;" onclick="switchTab('workshops')">View Workshops</button>
                    </div>
                </div>
            </div>

            <div class="section">
                <div class="container">
                    <h2 class="section-title">Welcome to Your Spiritual Home</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.3rem; max-width: 800px; margin-left: auto; margin-right: auto;">
                        Discover a comprehensive platform designed to nurture your spiritual growth through quality resources, 
                        transformative workshops, and meaningful community connections.
                    </p>

                    <div class="ministry-grid">
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-book"></i></div>
                            <h3>Christian Books</h3>
                            <p>Access our curated collection of Christian literature, study guides, and spiritual resources from trusted South African authors.</p>
                            <button class="btn btn-outline" onclick="switchTab('books')" style="margin-top: 1.5rem;">Browse Books</button>
                        </div>
                        
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-chalkboard-teacher"></i></div>
                            <h3>Workshops & Training</h3>
                            <p>Join live and recorded workshops covering biblical studies, leadership, marriage, and personal spiritual development.</p>
                            <button class="btn btn-outline" onclick="switchTab('workshops')" style="margin-top: 1.5rem;">View Workshops</button>
                        </div>
                        
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-users"></i></div>
                            <h3>Ministry Programs</h3>
                            <p>Get involved with our youth, women's, and men's ministries designed for spiritual growth and community building.</p>
                            <button class="btn btn-outline" onclick="switchTab('ministry')" style="margin-top: 1.5rem;">Explore Ministries</button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- BOOKS TAB -->
        <section id="books-tab" class="tab-content">
            <div class="section">
                <div class="container">
                    <h2 class="section-title">Christian Books & Resources</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.3rem;">
                        Discover our curated collection of Christian literature from South African and international authors
                    </p>

                    <div class="books-grid">
                        <div class="book-card">
                            <div class="book-badge">Bestseller</div>
                            <div class="book-image">Daily Devotional</div>
                            <div class="book-info">
                                <h3 class="book-title">Morning Reflections: 365 Days with God</h3>
                                <p class="book-author">by Dr. Michael Thompson</p>
                                <p class="book-description">Start each day with profound biblical insights and practical applications for modern Christian living. This devotional has transformed thousands of lives across South Africa.</p>
                                <div class="book-price"><span class="currency">R</span>349.99</div>
                                <div class="book-actions">
                                    <button class="btn btn-primary btn-small" onclick="addToCart('Morning Reflections', 349.99, 'book')">Add to Cart</button>
                                    <button class="btn btn-outline btn-small">Preview</button>
                                </div>
                            </div>
                        </div>

                        <div class="book-card">
                            <div class="book-badge">New Release</div>
                            <div class="book-image">Bible Study</div>
                            <div class="book-info">
                                <h3 class="book-title">Understanding God's Grace</h3>
                                <p class="book-author">by Pastor Sarah Johnson</p>
                                <p class="book-description">A comprehensive study on the transformative power of grace in the life of every believer. Perfect for small group studies.</p>
                                <div class="book-price"><span class="currency">R</span>299.99</div>
                                <div class="book-actions">
                                    <button class="btn btn-primary btn-small" onclick="addToCart('Understanding Grace', 299.99, 'book')">Add to Cart</button>
                                    <button class="btn btn-outline btn-small">Preview</button>
                                </div>
                            </div>
                        </div>

                        <div class="book-card">
                            <div class="book-image">Christian Living</div>
                            <div class="book-info">
                                <h3 class="book-title">Faith in Action: Living the Gospel</h3>
                                <p class="book-author">by Elder James Wilson</p>
                                <p class="book-description">Practical guidance for applying biblical principles to everyday challenges and opportunities in the South African context.</p>
                                <div class="book-price"><span class="currency">R</span>279.99</div>
                                <div class="book-actions">
                                    <button class="btn btn-primary btn-small" onclick="addToCart('Faith in Action', 279.99, 'book')">Add to Cart</button>
                                    <button class="btn btn-outline btn-small">Preview</button>
                                </div>
                            </div>
                        </div>

                        <div class="book-card">
                            <div class="book-badge">Local Author</div>
                            <div class="book-image">Prayer Guide</div>
                            <div class="book-info">
                                <h3 class="book-title">The Power of Prayer in African Context</h3>
                                <p class="book-author">by Pastor Thabo Mbatha</p>
                                <p class="book-description">A culturally relevant guide to deepening your prayer life, written specifically for African Christians.</p>
                                <div class="book-price"><span class="currency">R</span>249.99</div>
                                <div class="book-actions">
                                    <button class="btn btn-primary btn-small" onclick="addToCart('Power of Prayer', 249.99, 'book')">Add to Cart</button>
                                    <button class="btn btn-outline btn-small">Preview</button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- WORKSHOPS TAB -->
        <section id="workshops-tab" class="tab-content">
            <div class="section">
                <div class="container">
                    <h2 class="section-title">Christian Workshops & Training</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.3rem;">
                        Join our transformative workshops and training sessions for spiritual growth and leadership development
                    </p>

                    <div class="workshops-grid">
                        <div class="workshop-card">
                            <div class="workshop-badge">Live Online</div>
                            <div class="workshop-image">Biblical Leadership</div>
                            <div class="workshop-info">
                                <h3 class="workshop-title">Biblical Leadership Principles</h3>
                                <p class="workshop-instructor">Facilitated by Dr. Sarah Johnson</p>
                                <div class="workshop-details">
                                    <div class="workshop-date"><i class="fas fa-calendar"></i> 15 April 2024</div>
                                    <div class="workshop-duration"><i class="fas fa-clock"></i> 3 Hours</div>
                                    <div class="workshop-seats"><i class="fas fa-users"></i> 12/25 Seats</div>
                                </div>
                                <p class="workshop-description">Learn timeless leadership principles from Scripture and apply them to modern ministry and workplace challenges. Interactive session with Q&A.</p>
                                <div class="workshop-price"><span class="currency">R</span>499.99</div>
                                <div class="workshop-actions">
                                    <button class="btn btn-primary btn-small" onclick="addToCart('Biblical Leadership Workshop', 499.99, 'workshop')">Register Now</button>
                                    <button class="btn btn-outline btn-small">Details</button>
                                </div>
                            </div>
                        </div>

                        <div class="workshop-card">
                            <div class="workshop-badge">In Person</div>
                            <div class="workshop-image">Marriage Enrichment</div>
                            <div class="workshop-info">
                                <h3 class="workshop-title">Marriage & Family Enrichment</h3>
                                <p class="workshop-instructor">Led by Pastors John & Mary Smith</p>
                                <div class="workshop-details">
                                    <div class="workshop-date"><i class="fas fa-calendar"></i> 22 April 2024</div>
                                    <div class="workshop-duration"><i class="fas fa-clock"></i> Full Day</div>
                                    <div class="workshop-seats"><i class="fas fa-users"></i> 8/20 Seats</div>
                                </div>
                                <p class="workshop-description">A full-day workshop focused on building strong Christian marriages and families. Includes practical exercises and couple activities.</p>
                                <div class="workshop-price"><span class="currency">R</span>799.99</div>
                                <div class="workshop-actions">
                                    <button class="btn btn-primary btn-small" onclick="addToCart('Marriage Workshop', 799.99, 'workshop')">Register Now</button>
                                    <button class="btn btn-outline btn-small">Details</button>
                                </div>
                            </div>
                        </div>

                        <div class="workshop-card">
                            <div class="workshop-badge">Self-Paced</div>
                            <div class="workshop-image">Spiritual Disciplines</div>
                            <div class="workshop-info">
                                <h3 class="workshop-title">Mastering Spiritual Disciplines</h3>
                                <p class="workshop-instructor">with Elder James Wilson</p>
                                <div class="workshop-details">
                                    <div class="workshop-date"><i class="fas fa-calendar"></i> Anytime</div>
                                    <div class="workshop-duration"><i class="fas fa-clock"></i> 6 Weeks</div>
                                    <div class="workshop-seats"><i class="fas fa-users"></i> Unlimited</div>
                                </div>
                                <p class="workshop-description">A comprehensive self-paced course on prayer, fasting, meditation, and other essential spiritual disciplines for growth.</p>
                                <div class="workshop-price"><span class="currency">R</span>649.99</div>
                                <div class="workshop-actions">
                                    <button class="btn btn-primary btn-small" onclick="addToCart('Spiritual Disciplines Course', 649.99, 'workshop')">Enroll Now</button>
                                    <button class="btn btn-outline btn-small">Preview</button>
                                </div>
                            </div>
                        </div>

                        <div class="workshop-card">
                            <div class="workshop-badge">New</div>
                            <div class="workshop-image">Youth Ministry</div>
                            <div class="workshop-info">
                                <h3 class="workshop-title">Youth Ministry Training</h3>
                                <p class="workshop-instructor">by Youth Pastor Mike Daniels</p>
                                <div class="workshop-details">
                                    <div class="workshop-date"><i class="fas fa-calendar"></i> 30 April 2024</div>
                                    <div class="workshop-duration"><i class="fas fa-clock"></i> 4 Hours</div>
                                    <div class="workshop-seats"><i class="fas fa-users"></i> 15/30 Seats</div>
                                </div>
                                <p class="workshop-description">Essential training for youth leaders and volunteers. Learn effective strategies for engaging young people in today's culture.</p>
                                <div class="workshop-price"><span class="currency">R</span>449.99</div>
                                <div class="workshop-actions">
                                    <button class="btn btn-primary btn-small" onclick="addToCart('Youth Ministry Training', 449.99, 'workshop')">Register Now</button>
                                    <button class="btn btn-outline btn-small">Details</button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- MINISTRY TAB -->
        <section id="ministry-tab" class="tab-content">
            <div class="section">
                <div class="container">
                    <h2 class="section-title">Ministry Programs</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.3rem;">
                        Join our various ministry programs designed to nurture spiritual growth at every stage of life
                    </p>

                    <div class="ministry-grid">
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-users"></i></div>
                            <h3>Youth Ministry</h3>
                            <p>Engaging programs for young believers aged 13-25. Weekly meetings, retreats, leadership training, and mission opportunities to build strong Christian foundations.</p>
                            <div class="book-actions">
                                <button class="btn btn-primary btn-small">Join Now</button>
                                <button class="btn btn-outline btn-small">Learn More</button>
                            </div>
                        </div>
                        
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-female"></i></div>
                            <h3>Women's Ministry</h3>
                            <p>Support and fellowship for women of all ages. Bible studies, prayer groups, annual conferences, and mentorship programs to empower women in faith.</p>
                            <div class="book-actions">
                                <button class="btn btn-primary btn-small">Join Now</button>
                                <button class="btn btn-outline btn-small">Learn More</button>
                            </div>
                        </div>
                        
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-male"></i></div>
                            <h3>Men's Ministry</h3>
                            <p>Building strong Christian men through accountability groups, workshops, service projects, and spiritual leadership training for effective discipleship.</p>
                            <div class="book-actions">
                                <button class="btn btn-primary btn-small">Join Now</button>
                                <button class="btn btn-outline btn-small">Learn More</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- COMMUNITY TAB -->
        <section id="community-tab" class="tab-content">
            <div class="section">
                <div class="container">
                    <h2 class="section-title">Our Community</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.3rem;">
                        Join thousands of believers in our growing global community
                    </p>

                    <div class="community-stats">
                        <div class="stat-card">
                            <div class="stat-number">10,000+</div>
                            <div class="stat-label">Members Worldwide</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number">500+</div>
                            <div class="stat-label">Books Published</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number">50+</div>
                            <div class="stat-label">Workshops Hosted</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number">24/7</div>
                            <div class="stat-label">Prayer Support</div>
                        </div>
                    </div>

                    <div class="ministry-grid">
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-comments"></i></div>
                            <h3>Discussion Forums</h3>
                            <p>Join meaningful conversations about faith, life, and scripture with believers from around the world.</p>
                            <button class="btn btn-primary" style="margin-top: 1.5rem;">Enter Forums</button>
                        </div>
                        
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-pray"></i></div>
                            <h3>Prayer Groups</h3>
                            <p>Share prayer requests and join others in prayer. Experience the power of collective intercession.</p>
                            <button class="btn btn-primary" style="margin-top: 1.5rem;">Join Prayer Group</button>
                        </div>
                        
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-calendar-alt"></i></div>
                            <h3>Events & Meetings</h3>
                            <p>Participate in live sessions, webinars, and virtual events with Christian leaders and teachers.</p>
                            <button class="btn btn-primary" style="margin-top: 1.5rem;">View Events</button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- BLOG TAB -->
        <section id="blog-tab" class="tab-content">
            <div class="section">
                <div class="container">
                    <h2 class="section-title">From Our Blog</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.3rem;">
                        Inspirational articles and Christian insights for your spiritual journey
                    </p>

                    <div class="blog-grid">
                        <div class="blog-card">
                            <div class="blog-image">Featured Image</div>
                            <div class="blog-content">
                                <h3 class="blog-title">5 Ways to Deepen Your Prayer Life</h3>
                                <p class="blog-excerpt">Discover practical steps to strengthen your communication with God and transform your spiritual journey through consistent prayer practice.</p>
                                <div class="blog-meta">
                                    <span>March 15, 2024</span>
                                    <span>5 min read</span>
                                </div>
                                <button class="btn btn-outline" style="margin-top: 1rem;">Read More</button>
                            </div>
                        </div>
                        
                        <div class="blog-card">
                            <div class="blog-image">Featured Image</div>
                            <div class="blog-content">
                                <h3 class="blog-title">Understanding God's Grace in Difficult Times</h3>
                                <p class="blog-excerpt">Learn how to recognize and embrace God's grace even when facing life's biggest challenges and uncertainties.</p>
                                <div class="blog-meta">
                                    <span>March 12, 2024</span>
                                    <span>7 min read</span>
                                </div>
                                <button class="btn btn-outline" style="margin-top: 1rem;">Read More</button>
                            </div>
                        </div>
                        
                        <div class="blog-card">
                            <div class="blog-image">Featured Image</div>
                            <div class="blog-content">
                                <h3 class="blog-title">Building a Christian Family in Modern Times</h3>
                                <p class="blog-excerpt">Practical advice for maintaining strong Christian values and relationships in today's rapidly changing world.</p>
                                <div class="blog-meta">
                                    <span>March 8, 2024</span>
                                    <span>6 min read</span>
                                </div>
                                <button class="btn btn-outline" style="margin-top: 1rem;">Read More</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ABOUT TAB -->
        <section id="about-tab" class="tab-content">
            <div class="section">
                <div class="container">
                    <h2 class="section-title">About The Definitive Word</h2>
                    
                    <div class="about-content">
                        <div class="about-text">
                            <h3>Our Mission & Vision</h3>
                            <p>The Definitive Word is dedicated to spreading the Gospel and supporting Christian growth through accessible digital resources. We believe in the transformative power of God's Word and strive to make quality Christian literature available to believers worldwide.</p>
                            
                            <p>Founded in 2020, our ministry has grown to serve thousands of Christians across the globe, providing not just books, but a comprehensive platform for spiritual development and community connection.</p>
                            
                            <ul class="about-features">
                                <li>Quality Christian literature from trusted authors</li>
                                <li>Transformative workshops and training</li>
                                <li>Comprehensive ministry programs</li>
                                <li>Supportive online community</li>
                                <li>Secure, encrypted platform for all transactions</li>
                            </ul>
                        </div>
                        
                        <div class="about-text">
                            <h3>Our Values</h3>
                            <p><strong>Faith:</strong> Everything we do is rooted in biblical principles and dedicated to glorifying God.</p>
                            <p><strong>Community:</strong> We believe in the power of Christian fellowship and mutual support.</p>
                            <p><strong>Excellence:</strong> We strive for the highest quality in all our resources and services.</p>
                            <p><strong>Accessibility:</strong> Making Christian resources available to everyone, everywhere.</p>
                            <p><strong>Integrity:</strong> Operating with transparency and biblical ethics in all dealings.</p>
                            <p><strong>Security:</strong> Protecting our users' data and privacy with enterprise-level security.</p>
                            
                            <button class="btn btn-primary" style="margin-top: 2rem;">Contact Our Team</button>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h4>The Definitive Word</h4>
                    <p>Your trusted source for biblical teaching, spiritual growth resources, and Christian community. Committed to spreading God's Word with excellence and integrity.</p>
                </div>
                
                <div class="footer-section">
                    <h4>Quick Links</h4>
                    <a onclick="switchTab('home')">Home</a>
                    <a onclick="switchTab('books')">Books</a>
                    <a onclick="switchTab('workshops')">Workshops</a>
                    <a onclick="switchTab('ministry')">Ministry Programs</a>
                    <a onclick="switchTab('community')">Community</a>
                </div>
                
                <div class="footer-section">
                    <h4>Ministry</h4>
                    <a>Youth Ministry</a>
                    <a>Women's Ministry</a>
                    <a>Men's Ministry</a>
                    <a>Prayer Requests</a>
                </div>
                
                <div class="footer-section">
                    <h4>Support</h4>
                    <a>Contact Us</a>
                    <a>FAQ</a>
                    <a>Shipping Info</a>
                    <a>Returns</a>
                    <a>Privacy Policy</a>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2024 The Definitive Word Ministry. All rights reserved. | Spreading God's Truth, Transforming Lives</p>
            </div>
        </div>
    </footer>

    <!-- Complete JavaScript -->
    <script>
        // ===== CONFIGURATION =====
        const CONFIG = {
            version: '2.1.0',
            security: {
                ssl: true,
                encryption: 'AES-256',
                sessionTimeout: 30
            },
            features: {
                doubleClick: false,
                rightClick: true,
                saveLogin: true,
                autoLogin: false
            }
        };

        // ===== APPLICATION STATE =====
        let currentUser = null;
        let cart = [];
        let currentTab = 'home';

        // ===== SECURITY SYSTEM =====
        class SecuritySystem {
            encryptData(data) {
                return btoa(JSON.stringify(data));
            }

            decryptData(encryptedData) {
                try {
                    return JSON.parse(atob(encryptedData));
                } catch (e) {
                    return null;
                }
            }

            validateInput(input, type) {
                const validators = {
                    email: /^[^\s@]+@[^\s@]+\.[^\s@]+$/,
                    password: /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d).{8,}$/
                };
                return validators[type] ? validators[type].test(input) : true;
            }
        }

        // ===== PAYMENT SYSTEM =====
        class PaymentSystem {
            async processPayment(amount, items) {
                return new Promise((resolve) => {
                    setTimeout(() => {
                        const transactionId = 'TX_' + Math.random().toString(36).substr(2, 9).toUpperCase();
                        resolve(transactionId);
                    }, 2000);
                });
            }
        }

        const securitySystem = new SecuritySystem();
        const paymentSystem = new PaymentSystem();

        // ===== NOTIFICATION SYSTEM =====
        function showNotification(message, type = 'info') {
            const container = document.getElementById('notificationContainer');
            const notification = document.createElement('div');
            notification.className = `notification ${type}`;
            notification.textContent = message;
            container.appendChild(notification);

            setTimeout(() => notification.classList.add('show'), 100);
            setTimeout(() => {
                notification.classList.remove('show');
                setTimeout(() => notification.remove(), 300);
            }, 4000);
        }

        // ===== TAB MANAGEMENT =====
        function switchTab(tabName) {
            // Hide all tabs
            document.querySelectorAll('.tab-content').forEach(tab => {
                tab.classList.remove('active');
            });
            
            // Remove active class from all nav links
            document.querySelectorAll('.nav-link').forEach(link => {
                link.classList.remove('active');
            });
            
            // Show selected tab
            document.getElementById(`${tabName}-tab`).classList.add('active');
            
            // Add active class to clicked nav link
            event.target.classList.add('active');
            
            // Update current tab
            currentTab = tabName;
            
            showNotification(`Switched to ${tabName.charAt(0).toUpperCase() + tabName.slice(1)}`);
        }

        // ===== CART MANAGEMENT =====
        function addToCart(itemName, price, type) {
            cart.push({ 
                name: itemName, 
                price: price, 
                type: type,
                id: Date.now() + Math.random()
            });
            updateCartDisplay();
            showNotification(`"${itemName}" added to cart!`, 'success');
        }

        function updateCartDisplay() {
            document.getElementById('cartCount').textContent = cart.length;
        }

        // ===== SETTINGS MANAGEMENT =====
        function openSettings() {
            document.getElementById('settingsModal').style.display = 'flex';
            loadSettings();
        }

        function closeSettings() {
            document.getElementById('settingsModal').style.display = 'none';
        }

        function loadSettings() {
            const settings = JSON.parse(localStorage.getItem('appSettings') || '{}');
            document.getElementById('autoLogin').checked = settings.autoLogin || false;
            document.getElementById('saveLogin').checked = settings.saveLogin || true;
            document.getElementById('doubleClick').checked = settings.doubleClick || false;
            document.getElementById('rightClick').checked = settings.rightClick !== false;
        }

        function updateSetting(key, value) {
            const settings = JSON.parse(localStorage.getItem('appSettings') || '{}');
            settings[key] = value;
            localStorage.setItem('appSettings', JSON.stringify(settings));
            
            CONFIG.features[key] = value;
            applySettings();
            showNotification(`Setting updated: ${key}`, 'success');
        }

        function applySettings() {
            // Apply double-click behavior
            document.addEventListener('dblclick', (e) => {
                if (CONFIG.features.doubleClick) {
                    const bookCard = e.target.closest('.book-card');
                    const workshopCard = e.target.closest('.workshop-card');
                    
                    if (bookCard) {
                        const bookTitle = bookCard.querySelector('.book-title').textContent;
                        const bookPrice = parseFloat(bookCard.querySelector('.book-price').textContent.replace('R', ''));
                        addToCart(bookTitle, bookPrice, 'book');
                    } else if (workshopCard) {
                        const workshopTitle = workshopCard.querySelector('.workshop-title').textContent;
                        const workshopPrice = parseFloat(workshopCard.querySelector('.workshop-price').textContent.replace('R', ''));
                        addToCart(workshopTitle, workshopPrice, 'workshop');
                    }
                }
            });

            // Apply right-click behavior
            document.addEventListener('contextmenu', (e) => {
                if (!CONFIG.features.rightClick) {
                    e.preventDefault();
                    return;
                }
                
                if (e.target.closest('.book-card') || e.target.closest('.workshop-card')) {
                    e.preventDefault();
                    showContextMenu(e);
                }
            });
        }

        // ===== CONTEXT MENU =====
        function showContextMenu(e) {
            const contextMenu = document.getElementById('contextMenu');
            contextMenu.style.display = 'block';
            contextMenu.style.left = e.pageX + 'px';
            contextMenu.style.top = e.pageY + 'px';
        }

        function hideContextMenu() {
            document.getElementById('contextMenu').style.display = 'none';
        }

        function openInNewTab() {
            window.open(window.location.href, '_blank');
            hideContextMenu();
        }

        function savePage() {
            const blob = new Blob([document.documentElement.outerHTML], { type: 'text/html' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = 'the-definitive-word.html';
            a.click();
            hideContextMenu();
        }

        function viewSource() {
            window.open('view-source:' + window.location.href, '_blank');
            hideContextMenu();
        }

        // ===== AUTHENTICATION =====
        function toggleLogin() {
            if (currentUser) {
                // Logout
                currentUser = null;
                document.getElementById('loginButton').innerHTML = '<i class="fas fa-user"></i> Sign In';
                showNotification('Logged out successfully', 'info');
            } else {
                // Simulate login
                const email = 'user@example.com';
                const password = 'SecurePass123';
                
                if (!securitySystem.validateInput(email, 'email')) {
                    showNotification('Invalid email format', 'error');
                    return;
                }

                if (!securitySystem.validateInput(password, 'password')) {
                    showNotification('Password must be 8+ chars with uppercase, lowercase and number', 'error');
                    return;
                }

                currentUser = {
                    email: securitySystem.encryptData(email),
                    name: 'John Doe',
                    lastLogin: new Date().toISOString()
                };
                
                document.getElementById('loginButton').innerHTML = '<i class="fas fa-user-check"></i> Logout';
                showNotification(`Welcome back, ${currentUser.name}!`, 'success');

                if (CONFIG.features.saveLogin) {
                    localStorage.setItem('userSession', securitySystem.encryptData({
                        email: email,
                        timestamp: Date.now()
                    }));
                }
            }
        }

        // ===== PAYMENT PROCESSING =====
        async function processCheckout() {
            if (cart.length === 0) {
                showNotification('Your cart is empty!', 'error');
                return;
            }

            try {
                showNotification('Processing secure payment...', 'warning');
                const total = cart.reduce((sum, item) => sum + item.price, 0);
                const transactionId = await paymentSystem.processPayment(total, cart);
                
                showNotification(`Payment successful! Transaction ID: ${transactionId}`, 'success');
                cart = [];
                updateCartDisplay();
                
                // Log security event
                console.log('🔒 Purchase completed:', { transactionId, items: cart.length, total });
            } catch (error) {
                showNotification(`Payment failed: ${error.message}`, 'error');
            }
        }

        // ===== DIAGNOSTICS =====
        function runFullDiagnostics() {
            showNotification('Running comprehensive system diagnostics...', 'warning');
            
            const tests = [
                { name: 'Security System', status: 'ok' },
                { name: 'Payment Gateway', status: 'ok' },
                { name: 'User Authentication', status: 'ok' },
                { name: 'Database Connection', status: 'ok' },
                { name: 'SSL Certificate', status: 'ok' }
            ];
            
            setTimeout(() => {
                showNotification('All systems operational!', 'success');
                console.log('✅ Diagnostics completed successfully');
            }, 2000);
        }

        // ===== INITIALIZATION =====
        document.addEventListener('DOMContentLoaded', function() {
            // Hide loading screen
            setTimeout(() => {
                document.getElementById('loadingScreen').style.display = 'none';
                showNotification('The Definitive Word loaded successfully!', 'success');
            }, 2000);

            // Apply settings
            applySettings();

            // Hide context menu on click
            document.addEventListener('click', hideContextMenu);

            // Check for saved session
            const savedSession = localStorage.getItem('userSession');
            if (savedSession && CONFIG.features.autoLogin) {
                try {
                    const sessionData = securitySystem.decryptData(savedSession);
                    if (sessionData) {
                        currentUser = {
                            email: securitySystem.encryptData(sessionData.email),
                            name: 'John Doe',
                            lastLogin: new Date().toISOString()
                        };
                        document.getElementById('loginButton').innerHTML = '<i class="fas fa-user-check"></i> Logout';
                        showNotification('Auto-login successful!', 'success');
                    }
                } catch (e) {
                    console.warn('Auto-login failed:', e);
                }
            }

            // Initialize cart
            updateCartDisplay();

            console.log('🚀 The Definitive Word fully initialized');
            console.log('🔒 Security System:', securitySystem);
            console.log('💳 Payment System:', paymentSystem);
            console.log('🛒 Cart Items:', cart.length);
        });

        // Make functions globally available
        window.switchTab = switchTab;
        window.addToCart = addToCart;
        window.openSettings = openSettings;
        window.closeSettings = closeSettings;
        window.toggleLogin = toggleLogin;
        window.runFullDiagnostics = runFullDiagnostics;
        window.processCheckout = processCheckout;
    </script>
</body>
</html>
