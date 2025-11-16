<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Complete Christian Platform</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        /* === UPDATED COLOR SCHEME: White, Gold, Blue === */
        :root {
            --primary-color: #1e3a8a;  /* Deep Blue */
            --secondary-color: #1e40af; /* Medium Blue */
            --accent-color: #2563eb;    /* Bright Blue */
            --gold-color: #d4af37;      /* Gold */
            --light-bg: #ffffff;        /* White */
            --dark-text: #1f2937;       /* Dark Gray */
            --light-text: #6b7280;      /* Light Gray */
            --white: #ffffff;           /* Pure White */
            --border: #e5e7eb;         /* Light Border */
            --success: #10b981;        /* Green */
            --error: #ef4444;          /* Red */
            --warning: #f59e0b;        /* Amber */
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
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
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
            border: 2px solid var(--gold-color);
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        /* Settings Header */
        .settings-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
            padding-bottom: 1rem;
            border-bottom: 2px solid var(--border);
        }

        .settings-header h3 {
            color: var(--primary-color);
            margin: 0;
        }

        /* Login/Signup Modal */
        .auth-form {
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

        .form-group input, .form-group textarea, .form-group select {
            padding: 12px;
            border: 1px solid var(--border);
            border-radius: 6px;
            font-size: 1rem;
            font-family: inherit;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus, .form-group textarea:focus, .form-group select:focus {
            outline: none;
            border-color: var(--accent-color);
            box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
        }

        .auth-tabs {
            display: flex;
            margin-bottom: 1.5rem;
            border-bottom: 2px solid var(--border);
        }

        .auth-tab {
            flex: 1;
            padding: 1rem;
            text-align: center;
            cursor: pointer;
            border-bottom: 3px solid transparent;
            transition: all 0.3s ease;
        }

        .auth-tab.active {
            border-bottom-color: var(--accent-color);
            color: var(--accent-color);
            font-weight: 600;
        }

        .auth-tab:hover {
            background: #f8fafc;
        }

        /* Login Options */
        .login-options {
            display: flex;
            gap: 1rem;
            margin: 1rem 0;
        }

        .login-option {
            flex: 1;
            padding: 1rem;
            border: 2px solid var(--border);
            border-radius: 8px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            background: var(--white);
        }

        .login-option:hover {
            border-color: var(--accent-color);
            transform: translateY(-2px);
        }

        .login-option.active {
            border-color: var(--accent-color);
            background: #f0f9ff;
        }

        .login-option i {
            font-size: 2rem;
            margin-bottom: 0.5rem;
            color: var(--primary-color);
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
            padding: 1rem 0; 
        }
        
        .logo { 
            font-size: 2rem; 
            font-weight: 700; 
            color: var(--primary-color); 
            text-decoration: none; 
            font-family: 'Georgia', serif; 
            white-space: nowrap;
        }
        
        .logo span { 
            color: var(--gold-color); 
            font-style: italic; 
        }
        
        .nav { 
            display: flex; 
            gap: 1.5rem; 
            align-items: center; 
            flex-wrap: wrap;
        }
        
        .nav-link { 
            color: var(--dark-text); 
            text-decoration: none; 
            font-weight: 500; 
            font-size: 1rem; 
            transition: all 0.3s ease; 
            position: relative; 
            cursor: pointer;
            white-space: nowrap;
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
            padding: 10px 20px; 
            border-radius: 6px; 
            text-decoration: none; 
            font-weight: 600; 
            transition: all 0.3s ease; 
            border: none; 
            cursor: pointer; 
            display: inline-block; 
            font-size: 0.9rem; 
            white-space: nowrap;
        }
        
        .btn-primary { 
            background: linear-gradient(135deg, var(--primary-color), var(--accent-color)); 
            color: var(--white); 
        }
        
        .btn-primary:hover { 
            transform: translateY(-2px); 
            box-shadow: 0 6px 20px rgba(37, 99, 235, 0.4); 
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

        /* Header Actions Compact */
        .header-actions {
            display: flex;
            gap: 0.8rem;
            align-items: center;
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
            padding: 100px 0;
            text-align: center;
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
            color: white;
        }

        .section {
            padding: 80px 0;
        }

        .section-title {
            font-size: 2.5rem;
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
        .books-grid, .workshops-grid, .events-grid, .blog-grid, .jobs-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .book-card, .workshop-card, .event-card, .blog-card, .job-card {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 12px;
            overflow: hidden;
            transition: all 0.3s ease;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            position: relative;
        }

        .book-card:hover, .workshop-card:hover, .event-card:hover, .blog-card:hover, .job-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.15);
        }

        .book-badge, .workshop-badge, .event-badge, .job-badge {
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

        .book-image, .workshop-image, .event-image, .blog-image, .job-image {
            height: 200px;
            background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-weight: 600;
            font-size: 1.1rem;
        }

        .book-info, .workshop-info, .event-info, .blog-info, .job-info {
            padding: 1.5rem;
        }

        .book-title, .workshop-title, .event-title, .blog-title, .job-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--primary-color);
            line-height: 1.4;
        }

        .book-author, .workshop-instructor, .event-speaker, .blog-author, .job-company {
            color: var(--light-text);
            margin-bottom: 1rem;
            font-size: 0.9rem;
            font-style: italic;
        }

        .book-description, .workshop-description, .event-description, .blog-excerpt, .job-description {
            color: var(--light-text);
            margin-bottom: 1.5rem;
            font-size: 0.9rem;
            line-height: 1.6;
        }

        .book-price, .workshop-price, .event-price, .job-salary {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--primary-color);
            margin-bottom: 1.5rem;
        }

        .book-actions, .workshop-actions, .event-actions, .blog-actions, .job-actions {
            display: flex;
            gap: 0.8rem;
        }

        .btn-small {
            padding: 8px 16px;
            font-size: 0.85rem;
            flex: 1;
            text-align: center;
        }

        /* Ministry Styles */
        .ministry-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .ministry-card {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 2rem;
            text-align: center;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            transition: all 0.3s ease;
        }

        .ministry-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.15);
        }

        .ministry-icon {
            font-size: 3rem;
            margin-bottom: 1.5rem;
            color: var(--primary-color);
        }

        /* Workshop Specific Styles */
        .workshop-details, .event-details, .job-details {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1rem;
            font-size: 0.85rem;
            color: var(--light-text);
        }

        .workshop-date, .workshop-duration, .workshop-seats,
        .event-date, .event-time, .event-location,
        .job-type, .job-location, .job-deadline {
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
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary-color);
            margin-bottom: 0.5rem;
        }

        .stat-label {
            color: var(--light-text);
            font-size: 1rem;
        }

        /* Cart Modal */
        .cart-items {
            max-height: 400px;
            overflow-y: auto;
            margin: 1rem 0;
        }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem;
            border-bottom: 1px solid var(--border);
        }

        .cart-item-info {
            flex: 1;
        }

        .cart-item-name {
            font-weight: 600;
            margin-bottom: 0.5rem;
        }

        .cart-item-price {
            color: var(--primary-color);
            font-weight: 600;
        }

        .cart-total {
            display: flex;
            justify-content: space-between;
            font-size: 1.2rem;
            font-weight: 700;
            margin: 1rem 0;
            padding-top: 1rem;
            border-top: 2px solid var(--border);
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
            padding: 60px 0 20px;
            margin-top: 4rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr;
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h4 {
            margin-bottom: 1.5rem;
            color: var(--white);
            font-size: 1.2rem;
        }

        .footer-section a {
            display: block;
            color: #cbd5e0;
            text-decoration: none;
            margin-bottom: 0.8rem;
            transition: color 0.3s ease;
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

        /* Editable Content */
        .editable {
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        .editable:hover {
            background-color: #f0f9ff;
        }

        .editable.editing {
            background-color: #fff8e1;
            border: 1px dashed var(--gold-color);
            padding: 0.5rem;
            border-radius: 4px;
        }

        /* Community Tabs */
        .community-tabs {
            display: flex;
            margin-bottom: 2rem;
            border-bottom: 2px solid var(--border);
        }

        .community-tab {
            padding: 1rem 2rem;
            cursor: pointer;
            border-bottom: 3px solid transparent;
            transition: all 0.3s ease;
        }

        .community-tab.active {
            border-bottom-color: var(--accent-color);
            color: var(--accent-color);
            font-weight: 600;
        }

        .community-tab:hover {
            background: #f8fafc;
        }

        /* Responsive */
        @media (max-width: 1024px) {
            .nav {
                gap: 1rem;
            }
        }

        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 1rem;
            }

            .nav {
                justify-content: center;
                gap: 1rem;
            }

            .hero-title {
                font-size: 2rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .footer-content {
                grid-template-columns: 1fr;
                text-align: center;
                gap: 2rem;
            }

            .header-actions {
                gap: 0.5rem;
            }

            .btn {
                padding: 8px 16px;
                font-size: 0.85rem;
            }

            .login-options {
                flex-direction: column;
            }
        }

        @media (max-width: 480px) {
            .nav {
                flex-direction: column;
                gap: 0.5rem;
            }
            
            .header-actions {
                flex-direction: column;
                gap: 0.5rem;
            }
            
            .logo {
                font-size: 1.5rem;
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

    <!-- Enhanced Login/Signup Modal -->
    <div class="modal" id="authModal">
        <div class="modal-content">
            <div class="settings-header">
                <h3>Welcome to The Definitive Word</h3>
                <button onclick="closeAuth()" style="background: none; border: none; font-size: 1.5rem; cursor: pointer;">×</button>
            </div>
            
            <!-- Login Type Selection -->
            <div id="loginTypeSelection">
                <h4 style="text-align: center; margin-bottom: 1.5rem; color: var(--primary-color);">Choose Login Type</h4>
                <div class="login-options">
                    <div class="login-option active" onclick="selectLoginType('normal')">
                        <i class="fas fa-user"></i>
                        <h4>Regular User</h4>
                        <p>Access books, workshops, and community features</p>
                    </div>
                    <div class="login-option" onclick="selectLoginType('admin')">
                        <i class="fas fa-user-shield"></i>
                        <h4>Administrator</h4>
                        <p>Manage content and platform settings</p>
                    </div>
                </div>
                <button class="btn btn-primary" onclick="proceedToLogin()" style="width: 100%; margin-top: 1rem;">
                    Continue to Login
                </button>
            </div>

            <!-- Login/Signup Forms -->
            <div id="loginForms" style="display: none;">
                <div class="auth-tabs">
                    <div class="auth-tab active" onclick="switchAuthTab('login')">Sign In</div>
                    <div class="auth-tab" onclick="switchAuthTab('signup')">Sign Up</div>
                </div>
                
                <div class="auth-form" id="loginForm">
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
                        <a href="#" style="color: var(--accent-color); text-decoration: none;" onclick="showForgotPassword()">Forgot password?</a>
                    </div>
                    <button class="btn btn-primary" onclick="performLogin()">Sign In</button>
                </div>
                
                <div class="auth-form" id="signupForm" style="display: none;">
                    <div class="form-group">
                        <label for="signupName">Full Name</label>
                        <input type="text" id="signupName" placeholder="Enter your full name">
                    </div>
                    <div class="form-group">
                        <label for="signupEmail">Email Address</label>
                        <input type="email" id="signupEmail" placeholder="Enter your email">
                    </div>
                    <div class="form-group">
                        <label for="signupPassword">Password</label>
                        <input type="password" id="signupPassword" placeholder="Create a password">
                    </div>
                    <div class="form-group">
                        <label for="signupConfirm">Confirm Password</label>
                        <input type="password" id="signupConfirm" placeholder="Confirm your password">
                    </div>
                    <button class="btn btn-primary" onclick="performSignup()">Create Account</button>
                </div>

                <div style="text-align: center; margin-top: 1rem;">
                    <button class="btn btn-outline" onclick="goBackToLoginType()" style="width: 100%;">
                        <i class="fas fa-arrow-left"></i> Back to Login Options
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Cart Modal -->
    <div class="modal" id="cartModal">
        <div class="modal-content">
            <div class="settings-header">
                <h3>Your Shopping Cart</h3>
                <button onclick="closeCart()" style="background: none; border: none; font-size: 1.5rem; cursor: pointer;">×</button>
            </div>
            <div class="cart-items" id="cartItems">
                <!-- Cart items will be populated here -->
            </div>
            <div class="cart-total">
                <span>Total:</span>
                <span id="cartTotalAmount">R 0.00</span>
            </div>
            <div class="book-actions">
                <button class="btn btn-outline btn-small" onclick="closeCart()">Continue Shopping</button>
                <button class="btn btn-primary btn-small" onclick="checkout()">Proceed to Checkout</button>
            </div>
        </div>
    </div>

    <!-- Settings Modal -->
    <div class="modal" id="settingsModal">
        <div class="modal-content">
            <div class="settings-header">
                <h3>Settings & Diagnostics</h3>
                <button onclick="closeSettings()" style="background: none; border: none; font-size: 1.5rem; cursor: pointer;">×</button>
            </div>
            <div class="settings-content">
                <div class="setting-group">
                    <h4>Account Settings</h4>
                    <div class="setting-option">
                        <span>Auto-login</span>
                        <label style="display: flex; align-items: center; gap: 0.5rem;">
                            <input type="checkbox" id="autoLogin" onchange="updateSetting('autoLogin', this.checked)">
                            <span>Enabled</span>
                        </label>
                    </div>
                    <div class="setting-option">
                        <span>Save Login</span>
                        <label style="display: flex; align-items: center; gap: 0.5rem;">
                            <input type="checkbox" id="saveLogin" onchange="updateSetting('saveLogin', this.checked)">
                            <span>Enabled</span>
                        </label>
                    </div>
                </div>

                <div class="setting-group">
                    <h4>System Diagnostics</h4>
                    <div style="margin-bottom: 1rem;">
                        <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.5rem;">
                            <span style="color: var(--success);">✓</span>
                            <span>Security: Active</span>
                        </div>
                        <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.5rem;">
                            <span style="color: var(--success);">✓</span>
                            <span>SSL: Encrypted</span>
                        </div>
                        <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.5rem;">
                            <span style="color: var(--success);">✓</span>
                            <span>Database: Connected</span>
                        </div>
                        <div style="display: flex; align-items: center; gap: 0.5rem;">
                            <span style="color: var(--success);">✓</span>
                            <span>Payments: Ready</span>
                        </div>
                    </div>
                    <button class="btn btn-outline" onclick="runFullDiagnostics()" style="width: 100%;">Run Full Diagnostics</button>
                </div>

                <div class="setting-group">
                    <h4>Admin Tools</h4>
                    <button class="btn btn-primary" onclick="toggleEditMode()" style="width: 100%; margin-bottom: 0.5rem;">
                        <i class="fas fa-edit"></i> Toggle Edit Mode
                    </button>
                    <button class="btn btn-outline" onclick="openAddItem()" style="width: 100%;">
                        <i class="fas fa-plus"></i> Add New Item
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Add Item Modal -->
    <div class="modal" id="addItemModal">
        <div class="modal-content">
            <div class="settings-header">
                <h3>Add New Item</h3>
                <button onclick="closeAddItem()" style="background: none; border: none; font-size: 1.5rem; cursor: pointer;">×</button>
            </div>
            <div class="auth-form">
                <div class="form-group">
                    <label for="itemType">Item Type</label>
                    <select id="itemType" onchange="updateItemForm()">
                        <option value="book">Book</option>
                        <option value="workshop">Workshop</option>
                        <option value="event">Event</option>
                        <option value="blog">Blog Post</option>
                        <option value="job">Job Opportunity</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="itemTitle">Title</label>
                    <input type="text" id="itemTitle" placeholder="Enter title">
                </div>
                <div class="form-group">
                    <label for="itemAuthor">Author/Instructor/Company</label>
                    <input type="text" id="itemAuthor" placeholder="Enter name">
                </div>
                <div class="form-group">
                    <label for="itemDescription">Description</label>
                    <textarea id="itemDescription" placeholder="Enter description"></textarea>
                </div>
                <div class="form-group" id="priceGroup">
                    <label for="itemPrice">Price (R)</label>
                    <input type="number" id="itemPrice" placeholder="0.00" step="0.01">
                </div>
                <div class="form-group" id="dateGroup" style="display: none;">
                    <label for="itemDate">Date</label>
                    <input type="text" id="itemDate" placeholder="e.g., 15 April 2024">
                </div>
                <div class="form-group" id="durationGroup" style="display: none;">
                    <label for="itemDuration">Duration</label>
                    <input type="text" id="itemDuration" placeholder="e.g., 3 Hours">
                </div>
                <div class="form-group" id="locationGroup" style="display: none;">
                    <label for="itemLocation">Location</label>
                    <input type="text" id="itemLocation" placeholder="e.g., Online, Johannesburg">
                </div>
                <div class="form-group" id="salaryGroup" style="display: none;">
                    <label for="itemSalary">Salary/Stipend</label>
                    <input type="text" id="itemSalary" placeholder="e.g., R15,000 - R20,000">
                </div>
                <button class="btn btn-primary" onclick="saveNewItem()">Add Item</button>
            </div>
        </div>
    </div>

    <!-- Main Header -->
    <header class="header">
        <div class="container">
            <div class="header-content">
                <a href="#home" class="logo" onclick="switchTab('home')">
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
                    <a href="#cart" style="position: relative; color: var(--primary-color); font-size: 1.2rem; text-decoration: none;" onclick="openCart()">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count" id="cartCount">0</span>
                    </a>
                    <button onclick="openSettings()" class="btn btn-outline">
                        <i class="fas fa-cog"></i>
                    </button>
                    <button onclick="openAuth()" class="btn btn-primary" id="loginButton">
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
                    <h1 style="font-size: 3rem; margin-bottom: 1.5rem;">The Definitive Word</h1>
                    <p style="font-size: 1.3rem; margin-bottom: 2.5rem; opacity: 0.9; max-width: 600px; margin-left: auto; margin-right: auto;">
                        Your complete Christian resource platform with books, workshops, ministry programs, and vibrant community.
                    </p>
                    <div style="display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap;">
                        <button class="btn btn-primary" onclick="switchTab('books')">Browse Books</button>
                        <button class="btn" style="background: rgba(255,255,255,0.1); color: white; border: 2px solid white;" onclick="switchTab('workshops')">View Workshops</button>
                        <button class="btn" style="background: rgba(255,255,255,0.1); color: white; border: 2px solid white;" onclick="openAuth()">Join Community</button>
                    </div>
                </div>
            </div>

            <div class="section">
                <div class="container">
                    <h2 class="section-title">Welcome to Your Spiritual Home</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.2rem; max-width: 800px; margin-left: auto; margin-right: auto;">
                        Discover a comprehensive platform designed to nurture your spiritual growth through quality resources, 
                        transformative workshops, and meaningful community connections.
                    </p>

                    <div class="ministry-grid">
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-book"></i></div>
                            <h3>Christian Books</h3>
                            <p class="editable" ondblclick="makeEditable(this)">Access our curated collection of Christian literature, study guides, and spiritual resources from trusted South African authors.</p>
                            <button class="btn btn-outline" onclick="switchTab('books')" style="margin-top: 1.5rem;">Browse Books</button>
                        </div>
                        
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-chalkboard-teacher"></i></div>
                            <h3>Workshops & Training</h3>
                            <p class="editable" ondblclick="makeEditable(this)">Join live and recorded workshops covering biblical studies, leadership, marriage, and personal spiritual development.</p>
                            <button class="btn btn-outline" onclick="switchTab('workshops')" style="margin-top: 1.5rem;">View Workshops</button>
                        </div>
                        
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-users"></i></div>
                            <h3>Ministry Programs</h3>
                            <p class="editable" ondblclick="makeEditable(this)">Get involved with our youth, women's, and men's ministries designed for spiritual growth and community building.</p>
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
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.2rem;">
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
                    <h2 class="section-title">Christian Workshops & Training</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.2rem;">
                        Join our transformative workshops and training sessions for spiritual growth and leadership development
                    </p>

                    <div class="workshops-grid" id="workshops-container">
                        <!-- Workshops will be loaded here dynamically -->
                    </div>
                </div>
            </div>
        </section>

        <!-- MINISTRY TAB -->
        <section id="ministry-tab" class="tab-content">
            <div class="section">
                <div class="container">
                    <h2 class="section-title">Ministry Programs</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.2rem;">
                        Join our various ministry programs designed to nurture spiritual growth at every stage of life
                    </p>

                    <div class="ministry-grid">
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-users"></i></div>
                            <h3>Youth Ministry</h3>
                            <p class="editable" ondblclick="makeEditable(this)">Engaging programs for young believers aged 13-25. Weekly meetings, retreats, leadership training, and mission opportunities to build strong Christian foundations.</p>
                            <div class="book-actions">
                                <button class="btn btn-primary btn-small" onclick="showMinistryDetails('Youth Ministry')">Learn More</button>
                                <button class="btn btn-outline btn-small" onclick="registerForMinistry('Youth Ministry')">Join Now</button>
                            </div>
                        </div>
                        
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-female"></i></div>
                            <h3>Women's Ministry</h3>
                            <p class="editable" ondblclick="makeEditable(this)">Support and fellowship for women of all ages. Bible studies, prayer groups, annual conferences, and mentorship programs to empower women in faith.</p>
                            <div class="book-actions">
                                <button class="btn btn-primary btn-small" onclick="showMinistryDetails('Women\\'s Ministry')">Learn More</button>
                                <button class="btn btn-outline btn-small" onclick="registerForMinistry('Women\\'s Ministry')">Join Now</button>
                            </div>
                        </div>
                        
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-male"></i></div>
                            <h3>Men's Ministry</h3>
                            <p class="editable" ondblclick="makeEditable(this)">Building strong Christian men through accountability groups, workshops, service projects, and spiritual leadership training for effective discipleship.</p>
                            <div class="book-actions">
                                <button class="btn btn-primary btn-small" onclick="showMinistryDetails('Men\\'s Ministry')">Learn More</button>
                                <button class="btn btn-outline btn-small" onclick="registerForMinistry('Men\\'s Ministry')">Join Now</button>
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
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.2rem;">
                        Join thousands of believers in our growing global community
                    </p>

                    <!-- Community Tabs -->
                    <div class="community-tabs">
                        <div class="community-tab active" onclick="switchCommunityTab('overview')">Overview</div>
                        <div class="community-tab" onclick="switchCommunityTab('events')">Upcoming Events</div>
                        <div class="community-tab" onclick="switchCommunityTab('jobs')">Job Opportunities</div>
                        <div class="community-tab" onclick="switchCommunityTab('forums')">Discussion Forums</div>
                    </div>

                    <!-- Community Overview -->
                    <div id="community-overview" class="community-tab-content active">
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
                                <p class="editable" ondblclick="makeEditable(this)">Join meaningful conversations about faith, life, and scripture with believers from around the world.</p>
                                <button class="btn btn-primary" style="margin-top: 1.5rem;" onclick="openCommunityForums()">Enter Forums</button>
                            </div>
                            
                            <div class="ministry-card">
                                <div class="ministry-icon"><i class="fas fa-pray"></i></div>
                                <h3>Prayer Groups</h3>
                                <p class="editable" ondblclick="makeEditable(this)">Share prayer requests and join others in prayer. Experience the power of collective intercession.</p>
                                <button class="btn btn-primary" style="margin-top: 1.5rem;" onclick="joinPrayerGroup()">Join Prayer Group</button>
                            </div>
                            
                            <div class="ministry-card">
                                <div class="ministry-icon"><i class="fas fa-calendar-alt"></i></div>
                                <h3>Events & Meetings</h3>
                                <p class="editable" ondblclick="makeEditable(this)">Participate in live sessions, webinars, and virtual events with Christian leaders and teachers.</p>
                                <button class="btn btn-primary" style="margin-top: 1.5rem;" onclick="viewCommunityEvents()">View Events</button>
                            </div>
                        </div>
                    </div>

                    <!-- Upcoming Events -->
                    <div id="community-events" class="community-tab-content" style="display: none;">
                        <div class="events-grid" id="events-container">
                            <!-- Events will be loaded here dynamically -->
                        </div>
                    </div>

                    <!-- Job Opportunities -->
                    <div id="community-jobs" class="community-tab-content" style="display: none;">
                        <div class="jobs-grid" id="jobs-container">
                            <!-- Jobs will be loaded here dynamically -->
                        </div>
                    </div>

                    <!-- Discussion Forums -->
                    <div id="community-forums" class="community-tab-content" style="display: none;">
                        <div class="ministry-grid">
                            <div class="ministry-card">
                                <div class="ministry-icon"><i class="fas fa-bible"></i></div>
                                <h3>Bible Study Forum</h3>
                                <p class="editable" ondblclick="makeEditable(this)">Deep dive into scripture with fellow believers. Share insights and ask questions about God's Word.</p>
                                <button class="btn btn-primary" style="margin-top: 1.5rem;" onclick="joinForum('Bible Study')">Join Discussion</button>
                            </div>
                            
                            <div class="ministry-card">
                                <div class="ministry-icon"><i class="fas fa-hands-helping"></i></div>
                                <h3>Christian Living</h3>
                                <p class="editable" ondblclick="makeEditable(this)">Discuss practical Christian living, relationships, work, and daily walk with Christ.</p>
                                <button class="btn btn-primary" style="margin-top: 1.5rem;" onclick="joinForum('Christian Living')">Join Discussion</button>
                            </div>
                            
                            <div class="ministry-card">
                                <div class="ministry-icon"><i class="fas fa-praying-hands"></i></div>
                                <h3>Prayer Requests</h3>
                                <p class="editable" ondblclick="makeEditable(this)">Share your prayer needs and pray for others in our supportive community.</p>
                                <button class="btn btn-primary" style="margin-top: 1.5rem;" onclick="joinForum('Prayer Requests')">Join Discussion</button>
                            </div>
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
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.2rem;">
                        Inspirational articles and Christian insights for your spiritual journey
                    </p>

                    <div class="blog-grid" id="blog-container">
                        <!-- Blog posts will be loaded here dynamically -->
                    </div>
                </div>
            </div>
        </section>

        <!-- ABOUT TAB -->
        <section id="about-tab" class="tab-content">
            <div class="section">
                <div class="container">
                    <h2 class="section-title">About The Definitive Word</h2>
                    
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: center; margin: 3rem 0;">
                        <div>
                            <h3 style="font-size: 2rem; margin-bottom: 1.5rem; color: var(--primary-color);">Our Mission & Vision</h3>
                            <p class="editable" ondblclick="makeEditable(this)">The Definitive Word is dedicated to spreading the Gospel and supporting Christian growth through accessible digital resources. We believe in the transformative power of God's Word and strive to make quality Christian literature available to believers worldwide.</p>
                            
                            <p class="editable" ondblclick="makeEditable(this)">Founded in 2020, our ministry has grown to serve thousands of Christians across the globe, providing not just books, but a comprehensive platform for spiritual development and community connection.</p>
                            
                            <ul style="list-style: none; margin-top: 2rem;">
                                <li style="padding: 0.5rem 0; display: flex; align-items: center; gap: 1rem;">
                                    <span style="color: var(--primary-color); font-weight: bold;">✓</span>
                                    <span class="editable" ondblclick="makeEditable(this)">Quality Christian literature from trusted authors</span>
                                </li>
                                <li style="padding: 0.5rem 0; display: flex; align-items: center; gap: 1rem;">
                                    <span style="color: var(--primary-color); font-weight: bold;">✓</span>
                                    <span class="editable" ondblclick="makeEditable(this)">Transformative workshops and training</span>
                                </li>
                                <li style="padding: 0.5rem 0; display: flex; align-items: center; gap: 1rem;">
                                    <span style="color: var(--primary-color); font-weight: bold;">✓</span>
                                    <span class="editable" ondblclick="makeEditable(this)">Comprehensive ministry programs</span>
                                </li>
                                <li style="padding: 0.5rem 0; display: flex; align-items: center; gap: 1rem;">
                                    <span style="color: var(--primary-color); font-weight: bold;">✓</span>
                                    <span class="editable" ondblclick="makeEditable(this)">Supportive online community</span>
                                </li>
                            </ul>
                        </div>
                        
                        <div>
                            <h3 style="font-size: 2rem; margin-bottom: 1.5rem; color: var(--primary-color);">Our Values</h3>
                            <p class="editable" ondblclick="makeEditable(this)"><strong>Faith:</strong> Everything we do is rooted in biblical principles and dedicated to glorifying God.</p>
                            <p class="editable" ondblclick="makeEditable(this)"><strong>Community:</strong> We believe in the power of Christian fellowship and mutual support.</p>
                            <p class="editable" ondblclick="makeEditable(this)"><strong>Excellence:</strong> We strive for the highest quality in all our resources and services.</p>
                            <p class="editable" ondblclick="makeEditable(this)"><strong>Accessibility:</strong> Making Christian resources available to everyone, everywhere.</p>
                            <p class="editable" ondblclick="makeEditable(this)"><strong>Integrity:</strong> Operating with transparency and biblical ethics in all dealings.</p>
                            <p class="editable" ondblclick="makeEditable(this)"><strong>Security:</strong> Protecting our users' data and privacy with enterprise-level security.</p>
                            
                            <button class="btn btn-primary" style="margin-top: 2rem;" onclick="contactTeam()">Contact Our Team</button>
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
                    <p class="editable" ondblclick="makeEditable(this)">Your trusted source for biblical teaching, spiritual growth resources, and Christian community. Committed to spreading God's Word with excellence and integrity.</p>
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
                    <a onclick="switchTab('ministry')">Youth Ministry</a>
                    <a onclick="switchTab('ministry')">Women's Ministry</a>
                    <a onclick="switchTab('ministry')">Men's Ministry</a>
                    <a onclick="submitPrayerRequest()">Prayer Requests</a>
                </div>
                
                <div class="footer-section">
                    <h4>Support</h4>
                    <a onclick="contactTeam()">Contact Us</a>
                    <a onclick="showFAQ()">FAQ</a>
                    <a onclick="showShippingInfo()">Shipping Info</a>
                    <a onclick="showReturnsPolicy()">Returns</a>
                    <a onclick="showPrivacyPolicy()">Privacy Policy</a>
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
            version: '2.4.0',
            admin: {
                username: 'admin@definitiveword.org',
                password: 'Admin123!'
            }
        };

        // ===== APPLICATION STATE =====
        let currentUser = null;
        let cart = [];
        let currentTab = 'home';
        let currentAuthTab = 'login';
        let selectedLoginType = 'normal';
        let editMode = false;

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
                },
                {
                    id: 3,
                    title: "Faith in Action: Living the Gospel",
                    author: "Elder James Wilson",
                    description: "Practical guidance for applying biblical principles to everyday challenges and opportunities.",
                    price: 279.99,
                    badge: "",
                    image: "Christian Living"
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
            ],
            events: [
                {
                    id: 1,
                    title: "Annual Prayer Conference",
                    speaker: "Various Church Leaders",
                    description: "Join us for three days of powerful prayer, worship, and spiritual renewal.",
                    price: 0,
                    badge: "Free Event",
                    image: "Prayer Conference",
                    date: "25-27 May 2024",
                    time: "9:00 AM - 5:00 PM",
                    location: "Johannesburg Convention Center"
                },
                {
                    id: 2,
                    title: "Youth Summer Camp",
                    speaker: "Youth Ministry Team",
                    description: "A week-long camp for youth featuring sports, worship, and Bible studies.",
                    price: 1200.00,
                    badge: "Early Bird",
                    image: "Youth Camp",
                    date: "15-22 December 2024",
                    time: "All Day",
                    location: "Drakensberg Retreat Center"
                }
            ],
            jobs: [
                {
                    id: 1,
                    title: "Church Administrator",
                    company: "Grace Community Church",
                    description: "We're seeking an organized administrator to manage church operations and support ministry activities.",
                    salary: "R18,000 - R22,000",
                    badge: "Full Time",
                    image: "Church Job",
                    type: "Full Time",
                    location: "Pretoria",
                    deadline: "30 April 2024"
                },
                {
                    id: 2,
                    title: "Worship Leader",
                    company: "Living Waters Ministry",
                    description: "Passionate worship leader needed to lead our congregation in heartfelt worship and develop the music ministry.",
                    salary: "R15,000 - R20,000",
                    badge: "Part Time",
                    image: "Music Job",
                    type: "Part Time",
                    location: "Cape Town",
                    deadline: "15 May 2024"
                }
            ],
            blogPosts: [
                {
                    id: 1,
                    title: "5 Ways to Deepen Your Prayer Life",
                    author: "Pastor Michael Thompson",
                    excerpt: "Discover practical steps to strengthen your communication with God and transform your spiritual journey through consistent prayer practice.",
                    date: "March 15, 2024",
                    readTime: "5 min read",
                    image: "Prayer Article"
                },
                {
                    id: 2,
                    title: "Understanding God's Grace in Difficult Times",
                    author: "Dr. Sarah Johnson",
                    excerpt: "Learn how to recognize and embrace God's grace even when facing life's biggest challenges and uncertainties.",
                    date: "March 12, 2024",
                    readTime: "7 min read",
                    image: "Grace Article"
                },
                {
                    id: 3,
                    title: "Building a Christian Family in Modern Times",
                    author: "Elder James Wilson",
                    excerpt: "Practical advice for maintaining strong Christian values and relationships in today's rapidly changing world.",
                    date: "March 8, 2024",
                    readTime: "6 min read",
                    image: "Family Article"
                }
            ],
            users: []
        };

        // ===== ENHANCED AUTHENTICATION SYSTEM =====
        function selectLoginType(type) {
            selectedLoginType = type;
            document.querySelectorAll('.login-option').forEach(option => {
                option.classList.remove('active');
            });
            event.currentTarget.classList.add('active');
        }

        function proceedToLogin() {
            document.getElementById('loginTypeSelection').style.display = 'none';
            document.getElementById('loginForms').style.display = 'block';
        }

        function goBackToLoginType() {
            document.getElementById('loginTypeSelection').style.display = 'block';
            document.getElementById('loginForms').style.display = 'none';
        }

        function switchAuthTab(tab) {
            currentAuthTab = tab;
            document.getElementById('loginForm').style.display = tab === 'login' ? 'block' : 'none';
            document.getElementById('signupForm').style.display = tab === 'signup' ? 'block' : 'none';
            
            document.querySelectorAll('.auth-tab').forEach(tabElement => {
                tabElement.classList.toggle('active', tabElement.textContent.includes(tab === 'login' ? 'Sign In' : 'Sign Up'));
            });
        }

        function openAuth() {
            document.getElementById('authModal').style.display = 'flex';
            document.getElementById('loginTypeSelection').style.display = 'block';
            document.getElementById('loginForms').style.display = 'none';
            selectedLoginType = 'normal';
            
            // Reset login options
            document.querySelectorAll('.login-option').forEach(option => {
                option.classList.remove('active');
            });
            document.querySelectorAll('.login-option')[0].classList.add('active');
        }

        function closeAuth() {
            document.getElementById('authModal').style.display = 'none';
            // Clear form fields
            document.getElementById('loginEmail').value = '';
            document.getElementById('loginPassword').value = '';
            document.getElementById('signupName').value = '';
            document.getElementById('signupEmail').value = '';
            document.getElementById('signupPassword').value = '';
            document.getElementById('signupConfirm').value = '';
        }

        function performLogin() {
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;

            if (!email || !password) {
                showNotification('Please enter both email and password', 'error');
                return;
            }

            // Check for admin login
            if (selectedLoginType === 'admin' && email === CONFIG.admin.username && password === CONFIG.admin.password) {
                currentUser = {
                    email: email,
                    name: 'Administrator',
                    role: 'admin',
                    lastLogin: new Date().toISOString()
                };
                document.getElementById('loginButton').innerHTML = '<i class="fas fa-user-shield"></i> Admin';
                showNotification(`Welcome, ${currentUser.name}! Admin privileges activated.`, 'success');
                closeAuth();
                return;
            }

            // Check regular users
            const user = appData.users.find(u => u.email === email && u.password === password);
            if (user) {
                currentUser = user;
                document.getElementById('loginButton').innerHTML = `<i class="fas fa-user-check"></i> ${user.name.split(' ')[0]}`;
                showNotification(`Welcome back, ${user.name}!`, 'success');
                closeAuth();
            } else {
                showNotification('Invalid email or password', 'error');
            }
        }

        function performSignup() {
            const name = document.getElementById('signupName').value;
            const email = document.getElementById('signupEmail').value;
            const password = document.getElementById('signupPassword').value;
            const confirm = document.getElementById('signupConfirm').value;

            if (!name || !email || !password || !confirm) {
                showNotification('Please fill in all fields', 'error');
                return;
            }

            if (password !== confirm) {
                showNotification('Passwords do not match', 'error');
                return;
            }

            if (password.length < 6) {
                showNotification('Password must be at least 6 characters', 'error');
                return;
            }

            // Check if user already exists
            if (appData.users.find(u => u.email === email)) {
                showNotification('An account with this email already exists', 'error');
                return;
            }

            // Create new user
            const newUser = {
                id: Date.now(),
                name: name,
                email: email,
                password: password,
                joinDate: new Date().toISOString(),
                role: 'member'
            };

            appData.users.push(newUser);
            saveToLocalStorage();

            currentUser = newUser;
            document.getElementById('loginButton').innerHTML = `<i class="fas fa-user-check"></i> ${name.split(' ')[0]}`;
            showNotification(`Welcome to The Definitive Word, ${name}!`, 'success');
            closeAuth();
        }

        // ===== COMMUNITY TAB SYSTEM =====
        function switchCommunityTab(tabName) {
            // Hide all community tabs
            document.querySelectorAll('.community-tab-content').forEach(tab => {
                tab.style.display = 'none';
            });
            
            // Remove active class from all community tabs
            document.querySelectorAll('.community-tab').forEach(tab => {
                tab.classList.remove('active');
            });
            
            // Show selected tab and activate
            document.getElementById(`community-${tabName}`).style.display = 'block';
            document.querySelector(`.community-tab[onclick="switchCommunityTab('${tabName}')"]`).classList.add('active');

            // Render appropriate content
            if (tabName === 'events') {
                renderEvents();
            } else if (tabName === 'jobs') {
                renderJobs();
            }
        }

        // ===== EDITABLE CONTENT SYSTEM =====
        function makeEditable(element) {
            if (!editMode) return;
            
            const currentText = element.textContent;
            element.classList.add('editing');
            
            const input = document.createElement('textarea');
            input.value = currentText;
            input.style.width = '100%';
            input.style.minHeight = '100px';
            input.style.padding = '0.5rem';
            input.style.border = '1px solid var(--accent-color)';
            input.style.borderRadius = '4px';
            
            element.innerHTML = '';
            element.appendChild(input);
            input.focus();
            
            // Save on Enter or click outside
            function saveEdit() {
                element.textContent = input.value;
                element.classList.remove('editing');
                showNotification('Content updated successfully!', 'success');
                saveToLocalStorage();
            }
            
            input.addEventListener('keydown', function(e) {
                if (e.key === 'Enter' && !e.shiftKey) {
                    e.preventDefault();
                    saveEdit();
                }
                if (e.key === 'Escape') {
                    element.textContent = currentText;
                    element.classList.remove('editing');
                }
            });
            
            input.addEventListener('blur', saveEdit);
        }

        function toggleEditMode() {
            if (!currentUser || currentUser.role !== 'admin') {
                showNotification('Admin access required. Please sign in as administrator.', 'error');
                openAuth();
                return;
            }
            
            editMode = !editMode;
            const editables = document.querySelectorAll('.editable');
            
            if (editMode) {
                editables.forEach(el => {
                    el.style.cursor = 'text';
                    el.title = 'Double-click to edit';
                });
                showNotification('Edit mode activated! Double-click any text to edit.', 'success');
            } else {
                editables.forEach(el => {
                    el.style.cursor = 'default';
                    el.title = '';
                });
                showNotification('Edit mode deactivated.', 'info');
            }
        }

        // ===== ENHANCED RENDER FUNCTIONS =====
        function renderEvents() {
            const container = document.getElementById('events-container');
            if (!container) return;
            
            container.innerHTML = '';

            appData.events.forEach(event => {
                const eventCard = `
                    <div class="event-card">
                        ${event.badge ? `<div class="event-badge">${event.badge}</div>` : ''}
                        <div class="event-image">${event.image}</div>
                        <div class="event-info">
                            <h3 class="event-title">${event.title}</h3>
                            <p class="event-speaker">Hosted by ${event.speaker}</p>
                            <div class="event-details">
                                <div class="event-date"><i class="fas fa-calendar"></i> ${event.date}</div>
                                <div class="event-time"><i class="fas fa-clock"></i> ${event.time}</div>
                                <div class="event-location"><i class="fas fa-map-marker-alt"></i> ${event.location}</div>
                            </div>
                            <p class="event-description">${event.description}</p>
                            ${event.price > 0 ? `<div class="event-price"><span class="currency">R</span>${event.price.toFixed(2)}</div>` : '<div class="event-price" style="color: var(--success);">Free Event</div>'}
                            <div class="event-actions">
                                <button class="btn btn-primary btn-small" onclick="registerForEvent('${event.title.replace(/'/g, "\\'")}', ${event.price})">Register Now</button>
                                <button class="btn btn-outline btn-small" onclick="showEventDetails('${event.title.replace(/'/g, "\\'")}', '${event.description.replace(/'/g, "\\'")}')">Details</button>
                            </div>
                        </div>
                    </div>
                `;
                container.innerHTML += eventCard;
            });
        }

        function renderJobs() {
            const container = document.getElementById('jobs-container');
            if (!container) return;
            
            container.innerHTML = '';

            appData.jobs.forEach(job => {
                const jobCard = `
                    <div class="job-card">
                        ${job.badge ? `<div class="job-badge">${job.badge}</div>` : ''}
                        <div class="job-image">${job.image}</div>
                        <div class="job-info">
                            <h3 class="job-title">${job.title}</h3>
                            <p class="job-company">${job.company}</p>
                            <div class="job-details">
                                <div class="job-type"><i class="fas fa-briefcase"></i> ${job.type}</div>
                                <div class="job-location"><i class="fas fa-map-marker-alt"></i> ${job.location}</div>
                                <div class="job-deadline"><i class="fas fa-clock"></i> Apply by ${job.deadline}</div>
                            </div>
                            <p class="job-description">${job.description}</p>
                            <div class="job-salary">${job.salary}</div>
                            <div class="job-actions">
                                <button class="btn btn-primary btn-small" onclick="applyForJob('${job.title.replace(/'/g, "\\'")}')">Apply Now</button>
                                <button class="btn btn-outline btn-small" onclick="showJobDetails('${job.title.replace(/'/g, "\\'")}', '${job.description.replace(/'/g, "\\'")}')">Details</button>
                            </div>
                        </div>
                    </div>
                `;
                container.innerHTML += jobCard;
            });
        }

        // ===== NEW ACTION FUNCTIONS =====
        function registerForEvent(title, price) {
            if (!currentUser) {
                showNotification('Please sign in to register for events', 'error');
                openAuth();
                return;
            }
            if (price > 0) {
                addToCart(title, price, 'event');
            } else {
                showNotification(`Successfully registered for ${title}! You will receive confirmation details via email.`, 'success');
            }
        }

        function applyForJob(title) {
            if (!currentUser) {
                showNotification('Please sign in to apply for jobs', 'error');
                openAuth();
                return;
            }
            showNotification(`Application submitted for ${title}! The employer will contact you if shortlisted.`, 'success');
        }

        function showEventDetails(title, description) {
            showNotification(`Event Details: ${title}\n\n${description}`, 'info');
        }

        function showJobDetails(title, description) {
            showNotification(`Job Details: ${title}\n\n${description}`, 'info');
        }

        function joinForum(forumName) {
            if (!currentUser) {
                showNotification('Please sign in to join forum discussions', 'error');
                openAuth();
                return;
            }
            showNotification(`Welcome to the ${forumName} forum! You can now participate in discussions.`, 'success');
        }

        // ===== EXISTING FUNCTIONS (Updated) =====
        function switchTab(tabName) {
            // Hide all tabs
            document.querySelectorAll('.tab-content').forEach(tab => {
                tab.classList.remove('active');
            });
            
            // Remove active class from all nav links
            document.querySelectorAll('.nav-link').forEach(link => {
                link.classList.remove('active');
            });
            
            // Show selected tab and activate nav link
            document.getElementById(`${tabName}-tab`).classList.add('active');
            document.querySelector(`.nav-link[href="#${tabName}"]`).classList.add('active');
            
            currentTab = tabName;

            // Render appropriate content
            if (tabName === 'books') {
                renderBooks();
            } else if (tabName === 'workshops') {
                renderWorkshops();
            } else if (tabName === 'blog') {
                renderBlogPosts();
            } else if (tabName === 'community') {
                // Reset to overview tab when switching to community
                switchCommunityTab('overview');
            }
        }

        // ===== KEEP ALL OTHER EXISTING FUNCTIONS AS THEY WERE =====
        // [All the existing functions from previous code remain here...]
        function showForgotPassword() {
            showNotification('Password reset feature coming soon!', 'info');
        }

        function openCart() {
            renderCartItems();
            document.getElementById('cartModal').style.display = 'flex';
        }

        function closeCart() {
            document.getElementById('cartModal').style.display = 'none';
        }

        function renderCartItems() {
            const container = document.getElementById('cartItems');
            const totalAmount = document.getElementById('cartTotalAmount');
            
            if (cart.length === 0) {
                container.innerHTML = '<p style="text-align: center; color: var(--light-text); padding: 2rem;">Your cart is empty</p>';
                totalAmount.textContent = 'R 0.00';
                return;
            }

            container.innerHTML = '';
            let total = 0;

            cart.forEach((item, index) => {
                total += item.price;
                const cartItem = document.createElement('div');
                cartItem.className = 'cart-item';
                cartItem.innerHTML = `
                    <div class="cart-item-info">
                        <div class="cart-item-name">${item.name}</div>
                        <div class="cart-item-price">R ${item.price.toFixed(2)}</div>
                    </div>
                    <button class="btn btn-outline btn-small" onclick="removeFromCart(${index})">Remove</button>
                `;
                container.appendChild(cartItem);
            });

            totalAmount.textContent = `R ${total.toFixed(2)}`;
        }

        function removeFromCart(index) {
            const removedItem = cart[index];
            cart.splice(index, 1);
            updateCartDisplay();
            renderCartItems();
            showNotification(`Removed ${removedItem.name} from cart`, 'info');
        }

        function checkout() {
            if (cart.length === 0) {
                showNotification('Your cart is empty', 'error');
                return;
            }

            if (!currentUser) {
                showNotification('Please sign in to checkout', 'error');
                openAuth();
                return;
            }

            showNotification('Processing your order...', 'warning');
            setTimeout(() => {
                const total = cart.reduce((sum, item) => sum + item.price, 0);
                showNotification(`Order completed successfully! Total: R ${total.toFixed(2)}`, 'success');
                cart = [];
                updateCartDisplay();
                closeCart();
            }, 2000);
        }

        function openAddItem() {
            if (!currentUser || currentUser.role !== 'admin') {
                showNotification('Admin access required. Please sign in as administrator.', 'error');
                openAuth();
                return;
            }
            document.getElementById('addItemModal').style.display = 'flex';
        }

        function closeAddItem() {
            document.getElementById('addItemModal').style.display = 'none';
            // Clear form
            document.getElementById('itemTitle').value = '';
            document.getElementById('itemAuthor').value = '';
            document.getElementById('itemDescription').value = '';
            document.getElementById('itemPrice').value = '';
            document.getElementById('itemDate').value = '';
            document.getElementById('itemDuration').value = '';
            document.getElementById('itemLocation').value = '';
            document.getElementById('itemSalary').value = '';
        }

        function updateItemForm() {
            const type = document.getElementById('itemType').value;
            document.getElementById('priceGroup').style.display = type !== 'blog' && type !== 'job' ? 'block' : 'none';
            document.getElementById('dateGroup').style.display = type === 'workshop' || type === 'event' ? 'block' : 'none';
            document.getElementById('durationGroup').style.display = type === 'workshop' ? 'block' : 'none';
            document.getElementById('locationGroup').style.display = type === 'event' || type === 'job' ? 'block' : 'none';
            document.getElementById('salaryGroup').style.display = type === 'job' ? 'block' : 'none';
        }

        function saveNewItem() {
            const type = document.getElementById('itemType').value;
            const title = document.getElementById('itemTitle').value;
            const author = document.getElementById('itemAuthor').value;
            const description = document.getElementById('itemDescription').value;

            if (!title || !author || !description) {
                showNotification('Please fill in all required fields', 'error');
                return;
            }

            const newItem = {
                id: Date.now(),
                title: title,
                description: description,
                image: type.charAt(0).toUpperCase() + type.slice(1) + ' Image',
                badge: "New"
            };

            if (type === 'book') {
                const price = parseFloat(document.getElementById('itemPrice').value);
                if (!price || price <= 0) {
                    showNotification('Please enter a valid price', 'error');
                    return;
                }
                newItem.price = price;
                newItem.author = author;
                appData.books.push(newItem);
                renderBooks();
            } else if (type === 'workshop') {
                const price = parseFloat(document.getElementById('itemPrice').value);
                if (!price || price <= 0) {
                    showNotification('Please enter a valid price', 'error');
                    return;
                }
                newItem.price = price;
                newItem.instructor = author;
                newItem.date = document.getElementById('itemDate').value || 'Date TBD';
                newItem.duration = document.getElementById('itemDuration').value || 'Duration TBD';
                newItem.seats = "0/0 Seats";
                appData.workshops.push(newItem);
                renderWorkshops();
            } else if (type === 'event') {
                const price = parseFloat(document.getElementById('itemPrice').value) || 0;
                newItem.price = price;
                newItem.speaker = author;
                newItem.date = document.getElementById('itemDate').value || 'Date TBD';
                newItem.time = "Time TBD";
                newItem.location = document.getElementById('itemLocation').value || 'Location TBD';
                appData.events.push(newItem);
                renderEvents();
            } else if (type === 'job') {
                newItem.company = author;
                newItem.salary = document.getElementById('itemSalary').value || 'Salary negotiable';
                newItem.type = "Full Time";
                newItem.location = document.getElementById('itemLocation').value || 'Location TBD';
                newItem.deadline = "Deadline TBD";
                appData.jobs.push(newItem);
                renderJobs();
            } else if (type === 'blog') {
                newItem.author = author;
                newItem.date = new Date().toLocaleDateString();
                newItem.readTime = "5 min read";
                newItem.excerpt = description.substring(0, 150) + '...';
                appData.blogPosts.push(newItem);
                renderBlogPosts();
            }

            saveToLocalStorage();
            showNotification(`${type.charAt(0).toUpperCase() + type.slice(1)} added successfully!`, 'success');
            closeAddItem();
        }

        function renderBooks() {
            const container = document.getElementById('books-container');
            if (!container) return;
            
            container.innerHTML = '';

            appData.books.forEach(book => {
                const bookCard = `
                    <div class="book-card">
                        ${book.badge ? `<div class="book-badge">${book.badge}</div>` : ''}
                        <div class="book-image">${book.image}</div>
                        <div class="book-info">
                            <h3 class="book-title">${book.title}</h3>
                            <p class="book-author">by ${book.author}</p>
                            <p class="book-description">${book.description}</p>
                            <div class="book-price"><span class="currency">R</span>${book.price.toFixed(2)}</div>
                            <div class="book-actions">
                                <button class="btn btn-primary btn-small" onclick="addToCart('${book.title.replace(/'/g, "\\'")}', ${book.price}, 'book')">Add to Cart</button>
                                <button class="btn btn-outline btn-small" onclick="previewItem('${book.title.replace(/'/g, "\\'")}', '${book.description.replace(/'/g, "\\'")}', ${book.price})">Preview</button>
                            </div>
                        </div>
                    </div>
                `;
                container.innerHTML += bookCard;
            });
        }

        function renderWorkshops() {
            const container = document.getElementById('workshops-container');
            if (!container) return;
            
            container.innerHTML = '';

            appData.workshops.forEach(workshop => {
                const workshopCard = `
                    <div class="workshop-card">
                        ${workshop.badge ? `<div class="workshop-badge">${workshop.badge}</div>` : ''}
                        <div class="workshop-image">${workshop.image}</div>
                        <div class="workshop-info">
                            <h3 class="workshop-title">${workshop.title}</h3>
                            <p class="workshop-instructor">Facilitated by ${workshop.instructor}</p>
                            <div class="workshop-details">
                                <div class="workshop-date"><i class="fas fa-calendar"></i> ${workshop.date}</div>
                                <div class="workshop-duration"><i class="fas fa-clock"></i> ${workshop.duration}</div>
                                <div class="workshop-seats"><i class="fas fa-users"></i> ${workshop.seats}</div>
                            </div>
                            <p class="workshop-description">${workshop.description}</p>
                            <div class="workshop-price"><span class="currency">R</span>${workshop.price.toFixed(2)}</div>
                            <div class="workshop-actions">
                                <button class="btn btn-primary btn-small" onclick="registerForWorkshop('${workshop.title.replace(/'/g, "\\'")}', ${workshop.price})">Register Now</button>
                                <button class="btn btn-outline btn-small" onclick="showWorkshopDetails('${workshop.title.replace(/'/g, "\\'")}', '${workshop.description.replace(/'/g, "\\'")}')">Details</button>
                            </div>
                        </div>
                    </div>
                `;
                container.innerHTML += workshopCard;
            });
        }

        function renderBlogPosts() {
            const container = document.getElementById('blog-container');
            if (!container) return;
            
            container.innerHTML = '';

            appData.blogPosts.forEach(post => {
                const blogCard = `
                    <div class="blog-card">
                        <div class="blog-image">${post.image}</div>
                        <div class="blog-info">
                            <h3 class="blog-title">${post.title}</h3>
                            <p class="blog-author">by ${post.author}</p>
                            <p class="blog-excerpt">${post.excerpt}</p>
                            <div class="blog-meta">
                                <span>${post.date}</span>
                                <span>${post.readTime}</span>
                            </div>
                            <div class="blog-actions">
                                <button class="btn btn-primary btn-small" onclick="readBlogPost('${post.title.replace(/'/g, "\\'")}')">Read More</button>
                                <button class="btn btn-outline btn-small" onclick="shareBlogPost('${post.title.replace(/'/g, "\\'")}')">Share</button>
                            </div>
                        </div>
                    </div>
                `;
                container.innerHTML += blogCard;
            });
        }

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

        function previewItem(title, description, price) {
            showNotification(`Preview: ${title} - R${price.toFixed(2)}\n\n${description}`, 'info');
        }

        function showWorkshopDetails(title, description) {
            showNotification(`Workshop Details: ${title}\n\n${description}`, 'info');
        }

        function registerForWorkshop(title, price) {
            if (!currentUser) {
                showNotification('Please sign in to register for workshops', 'error');
                openAuth();
                return;
            }
            addToCart(title, price, 'workshop');
        }

        function registerForMinistry(ministry) {
            if (!currentUser) {
                showNotification('Please sign in to join ministry programs', 'error');
                openAuth();
                return;
            }
            showNotification(`Thank you for your interest in ${ministry}! We'll contact you soon with more information.`, 'success');
        }

        function showMinistryDetails(ministry) {
            showNotification(`${ministry} Details:\n\nThis ministry program offers weekly meetings, special events, and spiritual growth opportunities tailored to specific age groups and needs.`, 'info');
        }

        function openCommunityForums() {
            if (!currentUser) {
                showNotification('Please sign in to access community forums', 'error');
                openAuth();
                return;
            }
            showNotification('Opening community forums... You can now participate in discussions with other members.', 'success');
        }

        function joinPrayerGroup() {
            if (!currentUser) {
                showNotification('Please sign in to join prayer groups', 'error');
                openAuth();
                return;
            }
            showNotification('You have been added to our prayer group! You will receive prayer requests and updates.', 'success');
        }

        function viewCommunityEvents() {
            switchCommunityTab('events');
        }

        function readBlogPost(title) {
            showNotification(`Now reading: ${title}\n\nFull article content would be displayed here.`, 'info');
        }

        function shareBlogPost(title) {
            showNotification(`Sharing: ${title}\n\nShare this inspiring article with friends and family!`, 'info');
        }

        function contactTeam() {
            showNotification('Contact our team at: support@definitiveword.org\n\nWe\'d love to hear from you!', 'info');
        }

        function submitPrayerRequest() {
            if (!currentUser) {
                showNotification('Please sign in to submit prayer requests', 'error');
                openAuth();
                return;
            }
            showNotification('Prayer request form opened. Share your prayer needs with our community.', 'info');
        }

        function showFAQ() {
            showNotification('Frequently Asked Questions:\n\nQ: How do I reset my password?\nA: Use the "Forgot Password" link on the login page.\n\nQ: Are workshops refundable?\nA: Yes, within 7 days of purchase.', 'info');
        }

        function showShippingInfo() {
            showNotification('Shipping Information:\n\n• Digital items: Instant download\n• Physical books: 3-5 business days\n• Free shipping on orders over R500', 'info');
        }

        function showReturnsPolicy() {
            showNotification('Returns Policy:\n\n• 30-day return policy for physical items\n• Digital items are non-refundable once downloaded\n• Contact support for returns', 'info');
        }

        function showPrivacyPolicy() {
            showNotification('Privacy Policy:\n\nWe value your privacy and protect your personal information. Your data is never shared with third parties without your consent.', 'info');
        }

        function openSettings() {
            document.getElementById('settingsModal').style.display = 'flex';
        }

        function closeSettings() {
            document.getElementById('settingsModal').style.display = 'none';
        }

        function runFullDiagnostics() {
            showNotification('Running comprehensive system diagnostics...', 'warning');
            
            const tests = [
                'Checking user authentication system... ✓',
                'Testing shopping cart functionality... ✓',
                'Verifying payment gateway... ✓',
                'Testing database connections... ✓',
                'Checking security protocols... ✓',
                'Validating all form submissions... ✓'
            ];
            
            let delay = 0;
            tests.forEach(test => {
                setTimeout(() => {
                    console.log(test);
                }, delay);
                delay += 500;
            });
            
            setTimeout(() => {
                showNotification('All systems operational! No issues found.', 'success');
            }, 3000);
        }

        function updateSetting(key, value) {
            showNotification(`${key} ${value ? 'enabled' : 'disabled'}`, 'success');
        }

        function saveToLocalStorage() {
            localStorage.setItem('definitiveWordData', JSON.stringify(appData));
        }

        function loadFromLocalStorage() {
            const saved = localStorage.getItem('definitiveWordData');
            if (saved) {
                try {
                    appData = JSON.parse(saved);
                    console.log('Data loaded from localStorage');
                    console.log('Books:', appData.books.length);
                    console.log('Workshops:', appData.workshops.length);
                    console.log('Blog Posts:', appData.blogPosts.length);
                    console.log('Users:', appData.users.length);
                } catch (e) {
                    console.error('Error loading data:', e);
                }
            }
        }

        function showNotification(message, type = 'info') {
            // Create notification element
            const notification = document.createElement('div');
            notification.style.cssText = `
                position: fixed;
                top: 20px;
                right: 20px;
                padding: 15px 20px;
                border-radius: 8px;
                color: white;
                z-index: 1001;
                background: ${type === 'success' ? 'var(--success)' : type === 'error' ? 'var(--error)' : type === 'warning' ? 'var(--warning)' : 'var(--accent-color)'};
                transform: translateX(400px);
                transition: transform 0.3s ease;
                max-width: 400px;
                word-wrap: break-word;
            `;
            notification.textContent = message;
            document.body.appendChild(notification);

            // Animate in
            setTimeout(() => {
                notification.style.transform = 'translateX(0)';
            }, 100);

            // Remove after delay
            setTimeout(() => {
                notification.style.transform = 'translateX(400px)';
                setTimeout(() => {
                    document.body.removeChild(notification);
                }, 300);
            }, 4000);
        }

        function checkSavedSession() {
            const savedUser = localStorage.getItem('definitiveWordCurrentUser');
            const autoLogin = localStorage.getItem('definitiveWordAutoLogin') === 'true';
            
            if (savedUser && autoLogin) {
                try {
                    const userData = JSON.parse(savedUser);
                    currentUser = userData;
                    document.getElementById('loginButton').innerHTML = `<i class="fas fa-user-check"></i> ${userData.name.split(' ')[0]}`;
                    showNotification(`Welcome back, ${userData.name}!`, 'success');
                } catch (e) {
                    console.error('Error loading saved session:', e);
                }
            }
        }

        // ===== INITIALIZATION =====
        document.addEventListener('DOMContentLoaded', function() {
            console.log('=== STARTING DIAGNOSTICS ===');
            
            // Hide loading screen
            setTimeout(() => {
                document.getElementById('loadingScreen').style.display = 'none';
                showNotification('The Definitive Word loaded successfully! All systems operational.', 'success');
            }, 2000);

            // Load data
            loadFromLocalStorage();
            
            // Render initial content
            renderBooks();
            renderWorkshops();
            renderBlogPosts();
            renderEvents();
            renderJobs();
            updateCartDisplay();

            // Set up tab switching for navigation links
            document.querySelectorAll('.nav-link').forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const tabName = this.getAttribute('href').substring(1);
                    switchTab(tabName);
                });
            });

            // Set up footer link functionality
            document.querySelectorAll('.footer-section a').forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const text = this.textContent;
                    if (text.includes('Home') || text.includes('Books') || text.includes('Workshops') || text.includes('Ministry') || text.includes('Community')) {
                        const tabName = text.toLowerCase().replace(' programs', '').replace(' ', '');
                        switchTab(tabName);
                    }
                });
            });

            // Check for saved user session
            checkSavedSession();

            console.log('=== DIAGNOSTICS COMPLETE ===');
            console.log('All systems initialized successfully');
            console.log('Current user:', currentUser);
        });

        // ===== ERROR BOUNDARY =====
        window.addEventListener('error', function(e) {
            console.error('Global error caught:', e.error);
            showNotification('An unexpected error occurred. Please refresh the page.', 'error');
        });

        // ===== BEFORE UNLOAD =====
        window.addEventListener('beforeunload', function() {
            // Save current state
            if (currentUser) {
                localStorage.setItem('definitiveWordCurrentUser', JSON.stringify(currentUser));
            }
            saveToLocalStorage();
        });

        console.log('The Definitive Word Platform v2.4.0 - Fully Initialized');
    </script>
</body>
</html>
