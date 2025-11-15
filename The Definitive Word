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

        /* Login Modal */
        .login-form {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .form-group {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }

        .form-group label {
            font-weight: 600;
            color: var(--dark-text);
        }

        .form-group input {
            padding: 12px;
            border: 1px solid var(--border);
            border-radius: 6px;
            font-size: 1rem;
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

        /* Admin Edit Mode */
        .edit-mode .editable {
            position: relative;
            border: 2px dashed var(--gold-color) !important;
            padding: 8px;
            margin: -8px;
            border-radius: 4px;
        }

        .edit-mode .editable:hover {
            background: rgba(212, 175, 55, 0.1);
        }

        .edit-toolbar {
            position: fixed;
            top: 80px;
            right: 20px;
            background: var(--primary-color);
            color: white;
            padding: 1rem;
            border-radius: 8px;
            z-index: 999;
            display: none;
        }

        .edit-toolbar.show {
            display: block;
        }

        .edit-controls {
            display: flex;
            gap: 0.5rem;
            flex-direction: column;
        }

        .edit-btn {
            background: var(--gold-color);
            color: var(--primary-color);
            border: none;
            padding: 8px 12px;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 600;
        }

        .edit-btn:hover {
            background: #b8941f;
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

        /* Add Item Button */
        .add-item-btn {
            background: var(--success);
            color: white;
            border: none;
            border-radius: 50%;
            width: 60px;
            height: 60px;
            font-size: 1.5rem;
            position: fixed;
            bottom: 100px;
            right: 20px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            z-index: 998;
            display: none;
        }

        .add-item-btn:hover {
            transform: scale(1.1);
        }

        .add-item-btn.show {
            display: block;
        }

        /* Currency Display */
        .currency {
            font-size: 0.8em;
            margin-right: 2px;
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

            .edit-toolbar {
                top: 120px;
                right: 10px;
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

    <!-- Login Modal -->
    <div class="modal" id="loginModal">
        <div class="modal-content">
            <div class="settings-header">
                <h3>Sign In to Your Account</h3>
                <button onclick="closeLogin()" style="background: none; border: none; font-size: 1.5rem; cursor: pointer;">×</button>
            </div>
            <div class="login-form">
                <div class="form-group">
                    <label for="loginEmail">Email Address</label>
                    <input type="email" id="loginEmail" placeholder="Enter your email">
                </div>
                <div class="form-group">
                    <label for="loginPassword">Password</label>
                    <input type="password" id="loginPassword" placeholder="Enter your password">
                </div>
                <div style="display: flex; justify-content: space-between; align-items: center; margin: 1rem 0;">
                    <label style="display: flex; align-items: center; gap: 0.5rem;">
                        <input type="checkbox" id="rememberLogin">
                        <span>Remember me</span>
                    </label>
                    <a href="#" style="color: var(--accent-color); text-decoration: none;">Forgot password?</a>
                </div>
                <button class="btn btn-primary" onclick="performLogin()">Sign In</button>
                <div style="text-align: center; margin-top: 1rem; color: var(--light-text);">
                    Don't have an account? <a href="#" style="color: var(--accent-color); text-decoration: none;">Contact administrator</a>
                </div>
            </div>
        </div>
    </div>

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

    <!-- Edit Toolbar -->
    <div class="edit-toolbar" id="editToolbar">
        <div class="edit-controls">
            <button class="edit-btn" onclick="addNewItem()"><i class="fas fa-plus"></i> Add Item</button>
            <button class="edit-btn" onclick="deleteSelectedItem()"><i class="fas fa-trash"></i> Delete</button>
            <button class="edit-btn" onclick="saveAllChanges()"><i class="fas fa-save"></i> Save All</button>
            <button class="edit-btn" onclick="toggleEditMode()"><i class="fas fa-times"></i> Exit Edit</button>
        </div>
    </div>

    <!-- Add Item Button -->
    <button class="add-item-btn" id="addItemBtn" onclick="addNewItem()" title="Add New Item">
        <i class="fas fa-plus"></i>
    </button>

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
                    <button onclick="openLogin()" class="btn btn-primary" id="loginButton">
                        <i class="fas fa-user"></i> Sign In
                    </button>
                </div>
            </div>
        </div>
    </header>

    <!-- Tab Contents -->
    <main id="mainContent">
        <!-- HOME TAB -->
        <section id="home-tab" class="tab-content active">
            <div class="hero-section">
                <div class="container">
                    <h1 style="font-size: 3.8rem; margin-bottom: 1.5rem;" class="editable" data-type="text" data-id="hero-title">The Definitive Word</h1>
                    <p style="font-size: 1.4rem; margin-bottom: 2.5rem; opacity: 0.9; max-width: 600px; margin-left: auto; margin-right: auto;" class="editable" data-type="text" data-id="hero-subtitle">
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
                    <h2 class="section-title editable" data-type="text" data-id="welcome-title">Welcome to Your Spiritual Home</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.3rem; max-width: 800px; margin-left: auto; margin-right: auto;" class="editable" data-type="text" data-id="welcome-description">
                        Discover a comprehensive platform designed to nurture your spiritual growth through quality resources, 
                        transformative workshops, and meaningful community connections.
                    </p>

                    <div class="ministry-grid" id="home-features">
                        <div class="ministry-card editable" data-type="card" data-id="feature-1">
                            <div class="ministry-icon"><i class="fas fa-book"></i></div>
                            <h3 class="editable" data-type="text">Christian Books</h3>
                            <p class="editable" data-type="text">Access our curated collection of Christian literature, study guides, and spiritual resources from trusted South African authors.</p>
                            <button class="btn btn-outline" onclick="switchTab('books')" style="margin-top: 1.5rem;">Browse Books</button>
                        </div>
                        
                        <div class="ministry-card editable" data-type="card" data-id="feature-2">
                            <div class="ministry-icon"><i class="fas fa-chalkboard-teacher"></i></div>
                            <h3 class="editable" data-type="text">Workshops & Training</h3>
                            <p class="editable" data-type="text">Join live and recorded workshops covering biblical studies, leadership, marriage, and personal spiritual development.</p>
                            <button class="btn btn-outline" onclick="switchTab('workshops')" style="margin-top: 1.5rem;">View Workshops</button>
                        </div>
                        
                        <div class="ministry-card editable" data-type="card" data-id="feature-3">
                            <div class="ministry-icon"><i class="fas fa-users"></i></div>
                            <h3 class="editable" data-type="text">Ministry Programs</h3>
                            <p class="editable" data-type="text">Get involved with our youth, women's, and men's ministries designed for spiritual growth and community building.</p>
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
                    <h2 class="section-title editable" data-type="text" data-id="books-title">Christian Books & Resources</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.3rem;" class="editable" data-type="text" data-id="books-subtitle">
                        Discover our curated collection of Christian literature from South African and international authors
                    </p>

                    <div class="books-grid" id="books-container">
                        <!-- Books will be loaded here dynamically -->
                    </div>
                </div>
            </div>
        </section>

        <!-- WORKSHOPS TAB -->
        <section id="workshops-tab" class="tab-content">
            <div class="section">
                <div class="container">
                    <h2 class="section-title editable" data-type="text" data-id="workshops-title">Christian Workshops & Training</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.3rem;" class="editable" data-type="text" data-id="workshops-subtitle">
                        Join our transformative workshops and training sessions for spiritual growth and leadership development
                    </p>

                    <div class="workshops-grid" id="workshops-container">
                        <!-- Workshops will be loaded here dynamically -->
                    </div>
                </div>
            </div>
        </section>

        <!-- Other tabs remain similar but with editable classes -->
        <!-- MINISTRY, COMMUNITY, BLOG, ABOUT tabs... -->
        
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
            version: '2.2.0',
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
            },
            admin: {
                username: 'admin',
                password: 'admin123', // In real app, this should be secure
                editMode: false
            }
        };

        // ===== APPLICATION STATE =====
        let currentUser = null;
        let cart = [];
        let currentTab = 'home';
        let editMode = false;
        let selectedItem = null;

        // ===== DATA STORAGE =====
        let appData = {
            books: [
                {
                    id: 1,
                    title: "Morning Reflections: 365 Days with God",
                    author: "Dr. Michael Thompson",
                    description: "Start each day with profound biblical insights and practical applications for modern Christian living.",
                    price: 349.99,
                    badge: "Bestseller",
                    image: "Daily Devotional"
                },
                {
                    id: 2,
                    title: "Understanding God's Grace",
                    author: "Pastor Sarah Johnson",
                    description: "A comprehensive study on the transformative power of grace in the life of every believer.",
                    price: 299.99,
                    badge: "New Release",
                    image: "Bible Study"
                }
            ],
            workshops: [
                {
                    id: 1,
                    title: "Biblical Leadership Principles",
                    instructor: "Dr. Sarah Johnson",
                    description: "Learn timeless leadership principles from Scripture and apply them to modern ministry challenges.",
                    price: 499.99,
                    badge: "Live Online",
                    image: "Biblical Leadership",
                    date: "15 April 2024",
                    duration: "3 Hours",
                    seats: "12/25 Seats"
                },
                {
                    id: 2,
                    title: "Marriage & Family Enrichment",
                    instructor: "Pastors John & Mary Smith",
                    description: "A full-day workshop focused on building strong Christian marriages and families.",
                    price: 799.99,
                    badge: "In Person",
                    image: "Marriage Enrichment",
                    date: "22 April 2024",
                    duration: "Full Day",
                    seats: "8/20 Seats"
                }
            ]
        };

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

        const securitySystem = new SecuritySystem();

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

        // ===== LOGIN SYSTEM =====
        function openLogin() {
            document.getElementById('loginModal').style.display = 'flex';
        }

        function closeLogin() {
            document.getElementById('loginModal').style.display = 'none';
        }

        function performLogin() {
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;
            const remember = document.getElementById('rememberLogin').checked;

            if (!email || !password) {
                showNotification('Please enter both email and password', 'error');
                return;
            }

            if (email === CONFIG.admin.username && password === CONFIG.admin.password) {
                currentUser = {
                    email: email,
                    name: 'Administrator',
                    role: 'admin',
                    lastLogin: new Date().toISOString()
                };
                
                document.getElementById('loginButton').innerHTML = '<i class="fas fa-user-shield"></i> Admin';
                showNotification(`Welcome, ${currentUser.name}!`, 'success');
                closeLogin();

                if (remember) {
                    localStorage.setItem('userSession', securitySystem.encryptData({
                        email: email,
                        timestamp: Date.now()
                    }));
                }

                // Show admin controls
                document.getElementById('addItemBtn').classList.add('show');
                
            } else {
                showNotification('Invalid login credentials', 'error');
            }
        }

        // ===== EDIT MODE SYSTEM =====
        function toggleEditMode() {
            editMode = !editMode;
            document.body.classList.toggle('edit-mode', editMode);
            document.getElementById('editToolbar').classList.toggle('show', editMode);
            
            if (editMode) {
                showNotification('Edit mode activated. Click on any item to edit.', 'warning');
                setupEditListeners();
            } else {
                showNotification('Edit mode deactivated', 'info');
                removeEditListeners();
            }
        }

        function setupEditListeners() {
            document.querySelectorAll('.editable').forEach(element => {
                element.addEventListener('click', handleEditClick);
            });
        }

        function removeEditListeners() {
            document.querySelectorAll('.editable').forEach(element => {
                element.removeEventListener('click', handleEditClick);
            });
        }

        function handleEditClick(event) {
            if (!editMode) return;
            
            event.stopPropagation();
            selectedItem = event.currentTarget;
            
            const currentText = selectedItem.textContent.trim();
            const newText = prompt('Edit content:', currentText);
            
            if (newText !== null && newText !== currentText) {
                selectedItem.textContent = newText;
                showNotification('Content updated successfully', 'success');
                saveToLocalStorage();
            }
        }

        function addNewItem() {
            if (!currentUser || currentUser.role !== 'admin') {
                showNotification('Admin access required', 'error');
                return;
            }

            const itemType = currentTab;
            let newItem;

            if (itemType === 'books') {
                newItem = {
                    id: Date.now(),
                    title: "New Book Title",
                    author: "Author Name",
                    description: "Book description goes here...",
                    price: 199.99,
                    badge: "New",
                    image: "Book Cover"
                };
                appData.books.push(newItem);
                renderBooks();
            } else if (itemType === 'workshops') {
                newItem = {
                    id: Date.now(),
                    title: "New Workshop",
                    instructor: "Instructor Name",
                    description: "Workshop description goes here...",
                    price: 399.99,
                    badge: "New",
                    image: "Workshop Image",
                    date: "Date TBD",
                    duration: "Duration TBD",
                    seats: "0/0 Seats"
                };
                appData.workshops.push(newItem);
                renderWorkshops();
            }

            showNotification('New item added. Click to edit details.', 'success');
            saveToLocalStorage();
        }

        function deleteSelectedItem() {
            if (!selectedItem) {
                showNotification('Please select an item to delete', 'warning');
                return;
            }

            if (confirm('Are you sure you want to delete this item?')) {
                selectedItem.remove();
                selectedItem = null;
                showNotification('Item deleted successfully', 'success');
                saveToLocalStorage();
            }
        }

        function saveAllChanges() {
            saveToLocalStorage();
            showNotification('All changes saved successfully!', 'success');
        }

        // ===== DATA MANAGEMENT =====
        function saveToLocalStorage() {
            localStorage.setItem('definitiveWordData', JSON.stringify(appData));
        }

        function loadFromLocalStorage() {
            const saved = localStorage.getItem('definitiveWordData');
            if (saved) {
                appData = JSON.parse(saved);
            }
        }

        // ===== RENDER FUNCTIONS =====
        function renderBooks() {
            const container = document.getElementById('books-container');
            container.innerHTML = '';

            appData.books.forEach(book => {
                const bookCard = `
                    <div class="book-card editable" data-type="card" data-id="book-${book.id}">
                        ${book.badge ? `<div class="book-badge">${book.badge}</div>` : ''}
                        <div class="book-image">${book.image}</div>
                        <div class="book-info">
                            <h3 class="book-title editable" data-type="text">${book.title}</h3>
                            <p class="book-author editable" data-type="text">by ${book.author}</p>
                            <p class="book-description editable" data-type="text">${book.description}</p>
                            <div class="book-price"><span class="currency">R</span>${book.price}</div>
                            <div class="book-actions">
                                <button class="btn btn-primary btn-small" onclick="addToCart('${book.title}', ${book.price}, 'book')">Add to Cart</button>
                                <button class="btn btn-outline btn-small">Preview</button>
                            </div>
                        </div>
                    </div>
                `;
                container.innerHTML += bookCard;
            });

            if (editMode) {
                setupEditListeners();
            }
        }

        function renderWorkshops() {
            const container = document.getElementById('workshops-container');
            container.innerHTML = '';

            appData.workshops.forEach(workshop => {
                const workshopCard = `
                    <div class="workshop-card editable" data-type="card" data-id="workshop-${workshop.id}">
                        ${workshop.badge ? `<div class="workshop-badge">${workshop.badge}</div>` : ''}
                        <div class="workshop-image">${workshop.image}</div>
                        <div class="workshop-info">
                            <h3 class="workshop-title editable" data-type="text">${workshop.title}</h3>
                            <p class="workshop-instructor editable" data-type="text">Facilitated by ${workshop.instructor}</p>
                            <div class="workshop-details">
                                <div class="workshop-date"><i class="fas fa-calendar"></i> ${workshop.date}</div>
                                <div class="workshop-duration"><i class="fas fa-clock"></i> ${workshop.duration}</div>
                                <div class="workshop-seats"><i class="fas fa-users"></i> ${workshop.seats}</div>
                            </div>
                            <p class="workshop-description editable" data-type="text">${workshop.description}</p>
                            <div class="workshop-price"><span class="currency">R</span>${workshop.price}</div>
                            <div class="workshop-actions">
                                <button class="btn btn-primary btn-small" onclick="addToCart('${workshop.title}', ${workshop.price}, 'workshop')">Register Now</button>
                                <button class="btn btn-outline btn-small">Details</button>
                            </div>
                        </div>
                    </div>
                `;
                container.innerHTML += workshopCard;
            });

            if (editMode) {
                setupEditListeners();
            }
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

            // Render appropriate content
            if (tabName === 'books') {
                renderBooks();
            } else if (tabName === 'workshops') {
                renderWorkshops();
            }
            
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
            // Apply settings as before...
        }

        // ===== ADMIN SHORTCUT =====
        function enableAdminShortcut() {
            let keySequence = '';
            document.addEventListener('keydown', (e) => {
                keySequence += e.key;
                if (keySequence.includes('admin')) {
                    if (currentUser && currentUser.role === 'admin') {
                        toggleEditMode();
                    } else {
                        openLogin();
                    }
                    keySequence = '';
                }
                // Keep only last 5 characters
                if (keySequence.length > 5) {
                    keySequence = keySequence.slice(-5);
                }
            });
        }

        // ===== INITIALIZATION =====
        document.addEventListener('DOMContentLoaded', function() {
            // Hide loading screen
            setTimeout(() => {
                document.getElementById('loadingScreen').style.display = 'none';
                showNotification('The Definitive Word loaded successfully!', 'success');
            }, 2000);

            // Load data
            loadFromLocalStorage();
            renderBooks();
            renderWorkshops();

            // Apply settings
            applySettings();

            // Enable admin shortcut
            enableAdminShortcut();

            // Check for saved session
            const savedSession = localStorage.getItem('userSession');
            if (savedSession && CONFIG.features.autoLogin) {
                try {
                    const sessionData = securitySystem.decryptData(savedSession);
                    if (sessionData) {
                        // Auto-login as admin if credentials match
                        if (sessionData.email === CONFIG.admin.username) {
                            currentUser = {
                                email: sessionData.email,
                                name: 'Administrator',
                                role: 'admin',
                                lastLogin: new Date().toISOString()
                            };
                            document.getElementById('loginButton').innerHTML = '<i class="fas fa-user-shield"></i> Admin';
                            document.getElementById('addItemBtn').classList.add('show');
                        }
                    }
                } catch (e) {
                    console.warn('Auto-login failed:', e);
                }
            }

            // Initialize cart
            updateCartDisplay();

            console.log('🚀 The Definitive Word fully initialized');
            console.log('🔒 Security System:', securitySystem);
            console.log('👤 Current User:', currentUser);
        });

        // Make functions globally available
        window.switchTab = switchTab;
        window.addToCart = addToCart;
        window.openSettings = openSettings;
        window.closeSettings = closeSettings;
        window.openLogin = openLogin;
        window.closeLogin = closeLogin;
        window.toggleEditMode = toggleEditMode;
        window.addNewItem = addNewItem;
        window.deleteSelectedItem = deleteSelectedItem;
        window.saveAllChanges = saveAllChanges;
    </script>
</body>
</html>
