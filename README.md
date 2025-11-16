<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Complete Christian Platform</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        /* === PROFESSIONAL COLOR SCHEME: White, Gold, Blue === */
        :root {
            --primary-blue: #1e3a8a;
            --secondary-blue: #2563eb;
            --light-blue: #dbeafe;
            --gold: #d4af37;
            --light-gold: #fef3c7;
            --white: #ffffff;
            --light-gray: #f8fafc;
            --medium-gray: #e2e8f0;
            --dark-gray: #475569;
            --text-dark: #1e293b;
            --success: #10b981;
            --error: #ef4444;
            --warning: #f59e0b;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: var(--text-dark);
            line-height: 1.6;
            background: var(--white);
            overflow-x: hidden;
        }

        /* Loading Screen */
        #loadingScreen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, var(--primary-blue) 0%, var(--secondary-blue) 100%);
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
            border-top: 4px solid var(--gold);
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            margin-bottom: 20px;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Diagnostic Panel */
        #diagnosticPanel {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: var(--white);
            border: 2px solid var(--gold);
            border-radius: 8px;
            padding: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            z-index: 1001;
            max-width: 300px;
            font-size: 0.85rem;
        }

        .diagnostic-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
            padding-bottom: 8px;
            border-bottom: 1px solid var(--medium-gray);
        }

        .diagnostic-item {
            display: flex;
            align-items: center;
            gap: 8px;
            margin: 5px 0;
            padding: 3px 0;
        }

        .status-indicator {
            width: 10px;
            height: 10px;
            border-radius: 50%;
        }

        .status-ok {
            background: var(--success);
        }

        .status-warning {
            background: var(--warning);
        }

        .status-error {
            background: var(--error);
        }

        /* Main Layout */
        .container { 
            max-width: 1200px; 
            margin: 0 auto; 
            padding: 0 20px; 
        }
        
        .header { 
            background: var(--white); 
            box-shadow: 0 2px 10px rgba(0,0,0,0.08); 
            position: sticky; 
            top: 0; 
            z-index: 1000; 
            border-bottom: 3px solid var(--gold); 
        }
        
        .header-content { 
            display: flex; 
            align-items: center; 
            justify-content: space-between; 
            padding: 1rem 0; 
        }
        
        .logo { 
            font-size: 1.8rem; 
            font-weight: 700; 
            color: var(--primary-blue); 
            text-decoration: none; 
            font-family: 'Georgia', serif; 
            white-space: nowrap;
        }
        
        .logo span { 
            color: var(--gold); 
            font-style: italic; 
        }
        
        .nav { 
            display: flex; 
            gap: 1.5rem; 
            align-items: center; 
            flex-wrap: wrap;
        }
        
        .nav-link { 
            color: var(--text-dark); 
            text-decoration: none; 
            font-weight: 500; 
            font-size: 1rem; 
            transition: all 0.3s ease; 
            position: relative; 
            cursor: pointer;
            white-space: nowrap;
            padding: 0.5rem 0;
        }
        
        .nav-link.active {
            color: var(--secondary-blue);
        }
        
        .nav-link.active:after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: var(--gold);
        }
        
        .nav-link:hover { 
            color: var(--secondary-blue); 
        }
        
        .btn { 
            padding: 10px 20px; 
            border-radius: 6px; 
            text-decoration: none; 
            font-weight: 600; 
            transition: all 0.3s ease; 
            border: none; 
            cursor: pointer; 
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 0.9rem; 
            white-space: nowrap;
        }
        
        .btn-primary { 
            background: linear-gradient(135deg, var(--primary-blue), var(--secondary-blue)); 
            color: var(--white); 
        }
        
        .btn-primary:hover { 
            transform: translateY(-2px); 
            box-shadow: 0 6px 20px rgba(37, 99, 235, 0.4); 
        }
        
        .btn-outline { 
            border: 2px solid var(--primary-blue); 
            color: var(--primary-blue); 
            background: transparent; 
        }
        
        .btn-outline:hover { 
            background: var(--primary-blue); 
            color: var(--white); 
        }

        .btn-gold {
            background: var(--gold);
            color: var(--white);
        }

        .btn-gold:hover {
            background: #b8941f;
            transform: translateY(-2px);
        }

        .btn-refresh {
            background: var(--light-gray);
            color: var(--primary-blue);
            border: 1px solid var(--medium-gray);
        }

        .btn-refresh:hover {
            background: var(--medium-gray);
        }

        /* Header Actions */
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
            background: linear-gradient(135deg, var(--primary-blue) 0%, var(--secondary-blue) 100%);
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><path d="M0,0 L100,0 L100,100 Z" fill="rgba(255,255,255,0.1)"/></svg>');
            background-size: cover;
        }

        .section {
            padding: 80px 0;
        }

        .section-light {
            background: var(--light-gray);
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 1rem;
            color: var(--primary-blue);
            font-family: 'Georgia', serif;
            position: relative;
        }

        .section-title:after {
            content: '';
            display: block;
            width: 80px;
            height: 3px;
            background: var(--gold);
            margin: 1rem auto;
        }

        .section-subtitle {
            text-align: center;
            color: var(--dark-gray);
            margin-bottom: 3rem;
            font-size: 1.2rem;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        /* Card Styles */
        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .card {
            background: var(--white);
            border-radius: 12px;
            overflow: hidden;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            position: relative;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.15);
        }

        .card-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background: var(--gold);
            color: var(--white);
            padding: 5px 12px;
            border-radius: 4px;
            font-size: 0.8rem;
            font-weight: 600;
            z-index: 2;
        }

        .card-image {
            height: 200px;
            background: linear-gradient(135deg, var(--primary-blue), var(--secondary-blue));
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-weight: 600;
            font-size: 1.1rem;
        }

        .card-content {
            padding: 1.5rem;
        }

        .card-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--primary-blue);
            line-height: 1.4;
        }

        .card-meta {
            color: var(--dark-gray);
            margin-bottom: 1rem;
            font-size: 0.9rem;
            font-style: italic;
        }

        .card-description {
            color: var(--dark-gray);
            margin-bottom: 1.5rem;
            font-size: 0.9rem;
            line-height: 1.6;
        }

        .card-price {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--primary-blue);
            margin-bottom: 1.5rem;
        }

        .card-actions {
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
            border-radius: 12px;
            padding: 2rem;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            transition: all 0.3s ease;
            border: 1px solid var(--medium-gray);
        }

        .ministry-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.15);
        }

        .ministry-icon {
            font-size: 3rem;
            margin-bottom: 1.5rem;
            color: var(--primary-blue);
            background: var(--light-gold);
            width: 80px;
            height: 80px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            margin-left: auto;
            margin-right: auto;
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
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary-blue);
            margin-bottom: 0.5rem;
        }

        .stat-label {
            color: var(--dark-gray);
            font-size: 1rem;
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
            padding: 1rem;
        }

        .modal-content {
            background: white;
            padding: 2rem;
            border-radius: 12px;
            max-width: 500px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            border: 2px solid var(--gold);
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            position: relative;
        }

        .modal-large {
            max-width: 800px;
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
            padding-bottom: 1rem;
            border-bottom: 2px solid var(--medium-gray);
        }

        .modal-header h3 {
            color: var(--primary-blue);
            margin: 0;
            font-size: 1.5rem;
        }

        .close-modal {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--dark-gray);
            transition: color 0.3s ease;
        }

        .close-modal:hover {
            color: var(--error);
        }

        /* Login Options */
        .login-options {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
            margin: 1.5rem 0;
        }

        .login-option {
            padding: 1.5rem;
            border: 2px solid var(--medium-gray);
            border-radius: 8px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            background: var(--white);
        }

        .login-option:hover {
            border-color: var(--secondary-blue);
            transform: translateY(-2px);
        }

        .login-option.active {
            border-color: var(--secondary-blue);
            background: var(--light-blue);
        }

        .login-option i {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            color: var(--primary-blue);
        }

        .login-option h4 {
            margin-bottom: 0.5rem;
            color: var(--primary-blue);
        }

        .login-option p {
            color: var(--dark-gray);
            font-size: 0.9rem;
            line-height: 1.4;
        }

        /* Form Styles */
        .form-group {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .form-group label {
            font-weight: 600;
            color: var(--text-dark);
            font-size: 0.9rem;
        }

        .form-group input, .form-group textarea, .form-group select {
            padding: 12px;
            border: 1px solid var(--medium-gray);
            border-radius: 6px;
            font-size: 1rem;
            font-family: inherit;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus, .form-group textarea:focus, .form-group select:focus {
            outline: none;
            border-color: var(--secondary-blue);
            box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
        }

        .form-actions {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 1.5rem 0;
        }

        .form-footer {
            text-align: center;
            margin-top: 1.5rem;
            padding-top: 1rem;
            border-top: 1px solid var(--medium-gray);
        }

        .auth-tabs {
            display: flex;
            margin-bottom: 1.5rem;
            border-bottom: 2px solid var(--medium-gray);
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
            border-bottom-color: var(--secondary-blue);
            color: var(--secondary-blue);
            font-weight: 600;
        }

        .auth-tab:hover {
            background: #f8fafc;
        }

        /* Progress Steps */
        .progress-steps {
            display: flex;
            justify-content: space-between;
            margin-bottom: 2rem;
            position: relative;
        }

        .progress-steps::before {
            content: '';
            position: absolute;
            top: 15px;
            left: 0;
            right: 0;
            height: 2px;
            background: var(--medium-gray);
            z-index: 1;
        }

        .progress-step {
            display: flex;
            flex-direction: column;
            align-items: center;
            position: relative;
            z-index: 2;
        }

        .step-icon {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            background: var(--medium-gray);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 0.5rem;
            font-size: 0.8rem;
        }

        .step-icon.active {
            background: var(--secondary-blue);
        }

        .step-icon.completed {
            background: var(--success);
        }

        .step-label {
            font-size: 0.8rem;
            color: var(--dark-gray);
            text-align: center;
        }

        .step-label.active {
            color: var(--secondary-blue);
            font-weight: 600;
        }

        /* Cart */
        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: var(--gold);
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

        /* Footer */
        .footer {
            background: var(--primary-blue);
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
            color: var(--gold);
        }

        .footer-bottom {
            border-top: 1px solid #4a5568;
            padding-top: 2rem;
            text-align: center;
            color: #cbd5e0;
        }

        /* Notification System */
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
            max-width: 400px;
            word-wrap: break-word;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .notification.success {
            background: var(--success);
        }

        .notification.error {
            background: var(--error);
        }

        .notification.warning {
            background: var(--warning);
        }

        .notification.info {
            background: var(--secondary-blue);
        }

        /* Responsive */
        @media (max-width: 1024px) {
            .nav {
                gap: 1rem;
            }
            
            .footer-content {
                grid-template-columns: 1fr 1fr;
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
                grid-template-columns: 1fr;
            }

            #diagnosticPanel {
                bottom: 10px;
                right: 10px;
                left: 10px;
                max-width: none;
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
            
            .card-actions {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Loading Screen -->
    <div id="loadingScreen">
        <div class="spinner"></div>
        <h3>Initializing The Definitive Word</h3>
        <p>Loading all features...</p>
    </div>

    <!-- Diagnostic Panel -->
    <div id="diagnosticPanel">
        <div class="diagnostic-header">
            <h4>System Diagnostics</h4>
            <button class="btn btn-refresh btn-small" onclick="runDiagnostics()">
                <i class="fas fa-sync-alt"></i> Refresh
            </button>
        </div>
        <div id="diagnosticResults">
            <!-- Diagnostic results will be populated here -->
        </div>
    </div>

    <!-- Enhanced Login/Signup Modal -->
    <div class="modal" id="authModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Welcome to The Definitive Word</h3>
                <button class="close-modal" onclick="closeModal('authModal')">×</button>
            </div>
            
            <!-- Step 1: Login Type Selection -->
            <div id="loginTypeStep" class="auth-step active">
                <div class="progress-steps">
                    <div class="progress-step">
                        <div class="step-icon active">1</div>
                        <div class="step-label active">Select Account Type</div>
                    </div>
                    <div class="progress-step">
                        <div class="step-icon">2</div>
                        <div class="step-label">Login/Signup</div>
                    </div>
                    <div class="progress-step">
                        <div class="step-icon">3</div>
                        <div class="step-label">Complete Profile</div>
                    </div>
                </div>
                
                <h4 style="text-align: center; margin-bottom: 1.5rem; color: var(--primary-blue);">Choose Your Account Type</h4>
                <p style="text-align: center; margin-bottom: 1.5rem; color: var(--dark-gray);">
                    Select the type of account that best fits your needs. You can always change this later.
                </p>
                
                <div class="login-options">
                    <div class="login-option active" onclick="selectLoginType('regular')">
                        <i class="fas fa-user"></i>
                        <h4>Regular Member</h4>
                        <p>Access books, workshops, community features, and spiritual resources. Perfect for individual spiritual growth.</p>
                    </div>
                    <div class="login-option" onclick="selectLoginType('admin')">
                        <i class="fas fa-user-shield"></i>
                        <h4>Administrator</h4>
                        <p>Manage platform content, users, and settings. Full access to all administrative tools and features.</p>
                    </div>
                </div>
                
                <div class="form-actions">
                    <button class="btn btn-outline" onclick="closeModal('authModal')">
                        <i class="fas fa-times"></i> Cancel
                    </button>
                    <button class="btn btn-primary" onclick="proceedToLoginForm()">
                        Continue <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Step 2: Login/Signup Forms -->
            <div id="loginFormStep" class="auth-step">
                <div class="progress-steps">
                    <div class="progress-step">
                        <div class="step-icon completed">✓</div>
                        <div class="step-label">Select Account Type</div>
                    </div>
                    <div class="progress-step">
                        <div class="step-icon active">2</div>
                        <div class="step-label active">Login/Signup</div>
                    </div>
                    <div class="progress-step">
                        <div class="step-icon">3</div>
                        <div class="step-label">Complete Profile</div>
                    </div>
                </div>
                
                <div class="auth-tabs">
                    <div class="auth-tab active" onclick="switchAuthTab('login')">Sign In</div>
                    <div class="auth-tab" onclick="switchAuthTab('signup')">Create Account</div>
                </div>
                
                <div class="auth-form" id="loginForm">
                    <div class="form-group">
                        <label for="loginEmail">Email Address</label>
                        <input type="email" id="loginEmail" placeholder="Enter your email address">
                    </div>
                    <div class="form-group">
                        <label for="loginPassword">Password</label>
                        <input type="password" id="loginPassword" placeholder="Enter your password">
                    </div>
                    <div class="form-actions">
                        <label style="display: flex; align-items: center; gap: 0.5rem;">
                            <input type="checkbox" id="rememberLogin">
                            <span>Remember me</span>
                        </label>
                        <a href="#" style="color: var(--secondary-blue); text-decoration: none;" onclick="showForgotPassword()">Forgot password?</a>
                    </div>
                    <button class="btn btn-primary" onclick="performLogin()" style="width: 100%;">
                        <i class="fas fa-sign-in-alt"></i> Sign In
                    </button>
                </div>
                
                <div class="auth-form" id="signupForm" style="display: none;">
                    <div class="form-group">
                        <label for="signupName">Full Name</label>
                        <input type="text" id="signupName" placeholder="Enter your full name">
                    </div>
                    <div class="form-group">
                        <label for="signupEmail">Email Address</label>
                        <input type="email" id="signupEmail" placeholder="Enter your email address">
                    </div>
                    <div class="form-group">
                        <label for="signupPassword">Password</label>
                        <input type="password" id="signupPassword" placeholder="Create a secure password">
                        <small style="color: var(--dark-gray);">Must be at least 8 characters with letters and numbers</small>
                    </div>
                    <div class="form-group">
                        <label for="signupConfirm">Confirm Password</label>
                        <input type="password" id="signupConfirm" placeholder="Confirm your password">
                    </div>
                    <div class="form-group">
                        <label style="display: flex; align-items: flex-start; gap: 0.5rem;">
                            <input type="checkbox" id="acceptTerms">
                            <span>I agree to the <a href="#" style="color: var(--secondary-blue);">Terms of Service</a> and <a href="#" style="color: var(--secondary-blue);">Privacy Policy</a></span>
                        </label>
                    </div>
                    <button class="btn btn-primary" onclick="performSignup()" style="width: 100%;">
                        <i class="fas fa-user-plus"></i> Create Account
                    </button>
                </div>
                
                <div class="form-footer">
                    <button class="btn btn-outline" onclick="goBackToLoginType()" style="width: 100%;">
                        <i class="fas fa-arrow-left"></i> Back to Account Type
                    </button>
                </div>
            </div>
            
            <!-- Step 3: Profile Completion -->
            <div id="profileStep" class="auth-step">
                <div class="progress-steps">
                    <div class="progress-step">
                        <div class="step-icon completed">✓</div>
                        <div class="step-label">Select Account Type</div>
                    </div>
                    <div class="progress-step">
                        <div class="step-icon completed">✓</div>
                        <div class="step-label">Login/Signup</div>
                    </div>
                    <div class="progress-step">
                        <div class="step-icon active">3</div>
                        <div class="step-label active">Complete Profile</div>
                    </div>
                </div>
                
                <h4 style="text-align: center; margin-bottom: 1.5rem; color: var(--primary-blue);">Complete Your Profile</h4>
                <p style="text-align: center; margin-bottom: 1.5rem; color: var(--dark-gray);">
                    Help us personalize your experience by completing your profile (optional).
                </p>
                
                <div class="form-group">
                    <label for="profileLocation">Location</label>
                    <input type="text" id="profileLocation" placeholder="City, Country">
                </div>
                
                <div class="form-group">
                    <label for="profileChurch">Church/Denomination (Optional)</label>
                    <input type="text" id="profileChurch" placeholder="Your church or denomination">
                </div>
                
                <div class="form-group">
                    <label for="profileInterests">Spiritual Interests</label>
                    <select id="profileInterests" multiple style="height: 100px;">
                        <option value="bible">Bible Study</option>
                        <option value="prayer">Prayer</option>
                        <option value="worship">Worship</option>
                        <option value="evangelism">Evangelism</option>
                        <option value="discipleship">Discipleship</option>
                        <option value="family">Family Ministry</option>
                        <option value="youth">Youth Ministry</option>
                        <option value="missions">Missions</option>
                    </select>
                    <small style="color: var(--dark-gray);">Hold Ctrl/Cmd to select multiple interests</small>
                </div>
                
                <div class="form-actions">
                    <button class="btn btn-outline" onclick="skipProfileCompletion()">
                        Skip for Now
                    </button>
                    <button class="btn btn-primary" onclick="completeProfile()">
                        Complete Profile <i class="fas fa-check"></i>
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Forgot Password Modal -->
    <div class="modal" id="forgotPasswordModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Reset Your Password</h3>
                <button class="close-modal" onclick="closeModal('forgotPasswordModal')">×</button>
            </div>
            
            <p style="margin-bottom: 1.5rem; color: var(--dark-gray);">
                Enter your email address and we'll send you a link to reset your password.
            </p>
            
            <div class="form-group">
                <label for="resetEmail">Email Address</label>
                <input type="email" id="resetEmail" placeholder="Enter your email address">
            </div>
            
            <button class="btn btn-primary" onclick="sendPasswordReset()" style="width: 100%; margin-bottom: 1rem;">
                <i class="fas fa-paper-plane"></i> Send Reset Link
            </button>
            
            <div class="form-footer">
                <p>Remember your password? <a href="#" style="color: var(--secondary-blue);" onclick="showLoginForm()">Sign in here</a></p>
            </div>
        </div>
    </div>

    <!-- Cart Modal -->
    <div class="modal" id="cartModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Your Shopping Cart</h3>
                <button class="close-modal" onclick="closeModal('cartModal')">×</button>
            </div>
            
            <div class="cart-items" id="cartItems">
                <div style="text-align: center; padding: 2rem; color: var(--dark-gray);">
                    <i class="fas fa-shopping-cart" style="font-size: 3rem; margin-bottom: 1rem; opacity: 0.5;"></i>
                    <h4>Your cart is empty</h4>
                    <p>Browse our store to add items to your cart</p>
                    <button class="btn btn-primary" onclick="closeModal('cartModal'); switchTab('books');" style="margin-top: 1rem;">
                        <i class="fas fa-book"></i> Browse Books
                    </button>
                </div>
            </div>
            
            <div class="cart-total" style="display: none;">
                <div style="display: flex; justify-content: space-between; font-size: 1.2rem; font-weight: 700; margin: 1rem 0; padding-top: 1rem; border-top: 2px solid var(--medium-gray);">
                    <span>Total:</span>
                    <span id="cartTotalAmount">R 0.00</span>
                </div>
                
                <div class="card-actions">
                    <button class="btn btn-outline btn-small" onclick="closeModal('cartModal')">Continue Shopping</button>
                    <button class="btn btn-primary btn-small" onclick="checkout()">Proceed to Checkout</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Settings Modal -->
    <div class="modal" id="settingsModal">
        <div class="modal-content modal-large">
            <div class="modal-header">
                <h3>Account Settings & Preferences</h3>
                <button class="close-modal" onclick="closeModal('settingsModal')">×</button>
            </div>
            
            <div class="auth-tabs">
                <div class="auth-tab active" onclick="switchSettingsTab('account')">Account</div>
                <div class="auth-tab" onclick="switchSettingsTab('notifications')">Notifications</div>
                <div class="auth-tab" onclick="switchSettingsTab('privacy')">Privacy</div>
                <div class="auth-tab" onclick="switchSettingsTab('billing')">Billing</div>
            </div>
            
            <div id="accountSettings" class="settings-tab">
                <h4 style="margin: 1.5rem 0 1rem 0; color: var(--primary-blue);">Profile Information</h4>
                
                <div class="form-group">
                    <label for="settingsName">Full Name</label>
                    <input type="text" id="settingsName" placeholder="Your full name">
                </div>
                
                <div class="form-group">
                    <label for="settingsEmail">Email Address</label>
                    <input type="email" id="settingsEmail" placeholder="Your email address">
                </div>
                
                <div class="form-group">
                    <label for="settingsLocation">Location</label>
                    <input type="text" id="settingsLocation" placeholder="Your location">
                </div>
                
                <h4 style="margin: 1.5rem 0 1rem 0; color: var(--primary-blue);">Account Security</h4>
                
                <div class="form-group">
                    <label for="currentPassword">Current Password</label>
                    <input type="password" id="currentPassword" placeholder="Your current password">
                </div>
                
                <div class="form-group">
                    <label for="newPassword">New Password</label>
                    <input type="password" id="newPassword" placeholder="New password">
                </div>
                
                <div class="form-group">
                    <label for="confirmNewPassword">Confirm New Password</label>
                    <input type="password" id="confirmNewPassword" placeholder="Confirm new password">
                </div>
                
                <button class="btn btn-primary" onclick="saveAccountSettings()" style="width: 100%;">
                    <i class="fas fa-save"></i> Save Changes
                </button>
            </div>
            
            <div id="notificationSettings" class="settings-tab" style="display: none;">
                <h4 style="margin: 1.5rem 0 1rem 0; color: var(--primary-blue);">Notification Preferences</h4>
                
                <div style="display: flex; justify-content: space-between; align-items: center; padding: 1rem 0; border-bottom: 1px solid var(--medium-gray);">
                    <div>
                        <div style="font-weight: 600;">Email Notifications</div>
                        <div style="font-size: 0.9rem; color: var(--dark-gray);">Receive updates about new content and features</div>
                    </div>
                    <label class="switch">
                        <input type="checkbox" checked>
                        <span class="slider"></span>
                    </label>
                </div>
                
                <div style="display: flex; justify-content: space-between; align-items: center; padding: 1rem 0; border-bottom: 1px solid var(--medium-gray);">
                    <div>
                        <div style="font-weight: 600;">Community Updates</div>
                        <div style="font-size: 0.9rem; color: var(--dark-gray);">Get notified about community events and discussions</div>
                    </div>
                    <label class="switch">
                        <input type="checkbox" checked>
                        <span class="slider"></span>
                    </label>
                </div>
                
                <div style="display: flex; justify-content: space-between; align-items: center; padding: 1rem 0; border-bottom: 1px solid var(--medium-gray);">
                    <div>
                        <div style="font-weight: 600;">Promotional Offers</div>
                        <div style="font-size: 0.9rem; color: var(--dark-gray);">Receive information about special offers and discounts</div>
                    </div>
                    <label class="switch">
                        <input type="checkbox">
                        <span class="slider"></span>
                    </label>
                </div>
                
                <button class="btn btn-primary" onclick="saveNotificationSettings()" style="width: 100%; margin-top: 1.5rem;">
                    <i class="fas fa-save"></i> Save Preferences
                </button>
            </div>
            
            <div id="privacySettings" class="settings-tab" style="display: none;">
                <h4 style="margin: 1.5rem 0 1rem 0; color: var(--primary-blue);">Privacy Settings</h4>
                
                <div style="margin-bottom: 1.5rem;">
                    <div style="font-weight: 600; margin-bottom: 0.5rem;">Profile Visibility</div>
                    <select style="width: 100%; padding: 10px; border-radius: 6px; border: 1px solid var(--medium-gray);">
                        <option>Public - Anyone can see my profile</option>
                        <option>Community Members Only</option>
                        <option selected>Private - Only I can see my profile</option>
                    </select>
                </div>
                
                <div style="display: flex; justify-content: space-between; align-items: center; padding: 1rem 0; border-bottom: 1px solid var(--medium-gray);">
                    <div>
                        <div style="font-weight: 600;">Data Collection</div>
                        <div style="font-size: 0.9rem; color: var(--dark-gray);">Allow us to collect anonymous usage data to improve our services</div>
                    </div>
                    <label class="switch">
                        <input type="checkbox" checked>
                        <span class="slider"></span>
                    </label>
                </div>
                
                <div style="display: flex; justify-content: space-between; align-items: center; padding: 1rem 0; border-bottom: 1px solid var(--medium-gray);">
                    <div>
                        <div style="font-weight: 600;">Personalized Content</div>
                        <div style="font-size: 0.9rem; color: var(--dark-gray);">Show personalized recommendations based on my activity</div>
                    </div>
                    <label class="switch">
                        <input type="checkbox" checked>
                        <span class="slider"></span>
                    </label>
                </div>
                
                <button class="btn btn-primary" onclick="savePrivacySettings()" style="width: 100%; margin-top: 1.5rem;">
                    <i class="fas fa-save"></i> Save Privacy Settings
                </button>
            </div>
            
            <div id="billingSettings" class="settings-tab" style="display: none;">
                <h4 style="margin: 1.5rem 0 1rem 0; color: var(--primary-blue);">Billing Information</h4>
                
                <div style="background: var(--light-gray); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1rem;">
                        <div style="font-weight: 600;">Current Plan</div>
                        <div style="background: var(--gold); color: white; padding: 0.3rem 0.8rem; border-radius: 4px; font-size: 0.8rem;">Free Tier</div>
                    </div>
                    <p style="color: var(--dark-gray); margin-bottom: 1rem;">Upgrade to our premium plan for access to exclusive content and features.</p>
                    <button class="btn btn-gold" style="width: 100%;">
                        <i class="fas fa-crown"></i> Upgrade to Premium
                    </button>
                </div>
                
                <h4 style="margin: 1.5rem 0 1rem 0; color: var(--primary-blue);">Payment Methods</h4>
                
                <div style="text-align: center; padding: 2rem; color: var(--dark-gray);">
                    <i class="fas fa-credit-card" style="font-size: 3rem; margin-bottom: 1rem; opacity: 0.5;"></i>
                    <h4>No payment methods</h4>
                    <p>Add a payment method to make purchases easier</p>
                    <button class="btn btn-outline" style="margin-top: 1rem;">
                        <i class="fas fa-plus"></i> Add Payment Method
                    </button>
                </div>
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
                    <button class="btn btn-refresh" onclick="refreshApplication()" title="Refresh Application">
                        <i class="fas fa-sync-alt"></i>
                    </button>
                    <a href="#cart" style="position: relative; color: var(--primary-blue); font-size: 1.2rem; text-decoration: none;" onclick="openModal('cartModal')">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count" id="cartCount">0</span>
                    </a>
                    <button onclick="openModal('settingsModal')" class="btn btn-outline">
                        <i class="fas fa-cog"></i>
                    </button>
                    <button onclick="openModal('authModal')" class="btn btn-primary" id="loginButton">
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
                        <button class="btn btn-primary" onclick="switchTab('books')">
                            <i class="fas fa-book"></i> Browse Books
                        </button>
                        <button class="btn" style="background: rgba(255,255,255,0.1); color: white; border: 2px solid white;" onclick="switchTab('workshops')">
                            <i class="fas fa-chalkboard-teacher"></i> View Workshops
                        </button>
                        <button class="btn" style="background: rgba(255,255,255,0.1); color: white; border: 2px solid white;" onclick="openModal('authModal')">
                            <i class="fas fa-users"></i> Join Community
                        </button>
                    </div>
                </div>
            </div>

            <div class="section section-light">
                <div class="container">
                    <h2 class="section-title">Welcome to Your Spiritual Home</h2>
                    <p class="section-subtitle">
                        Discover a comprehensive platform designed to nurture your spiritual growth through quality resources, 
                        transformative workshops, and meaningful community connections.
                    </p>

                    <div class="ministry-grid">
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-book"></i></div>
                            <h3>Christian Books</h3>
                            <p>Access our curated collection of Christian literature, study guides, and spiritual resources from trusted authors.</p>
                            <button class="btn btn-outline" onclick="switchTab('books')" style="margin-top: 1.5rem;">
                                <i class="fas fa-book-open"></i> Browse Books
                            </button>
                        </div>
                        
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-chalkboard-teacher"></i></div>
                            <h3>Workshops & Training</h3>
                            <p>Join live and recorded workshops covering biblical studies, leadership, marriage, and personal spiritual development.</p>
                            <button class="btn btn-outline" onclick="switchTab('workshops')" style="margin-top: 1.5rem;">
                                <i class="fas fa-video"></i> View Workshops
                            </button>
                        </div>
                        
                        <div class="ministry-card">
                            <div class="ministry-icon"><i class="fas fa-users"></i></div>
                            <h3>Ministry Programs</h3>
                            <p>Get involved with our youth, women's, and men's ministries designed for spiritual growth and community building.</p>
                            <button class="btn btn-outline" onclick="switchTab('ministry')" style="margin-top: 1.5rem;">
                                <i class="fas fa-hands-helping"></i> Explore Ministries
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <div class="section">
                <div class="container">
                    <h2 class="section-title">Featured Resources</h2>
                    <p class="section-subtitle">
                        Explore our most popular books, workshops, and resources to deepen your faith journey
                    </p>

                    <div class="cards-grid">
                        <div class="card">
                            <div class="card-badge">Bestseller</div>
                            <div class="card-image">Daily Devotional</div>
                            <div class="card-content">
                                <h3 class="card-title">Morning Reflections: 365 Days with God</h3>
                                <p class="card-meta">by Dr. Michael Thompson</p>
                                <p class="card-description">Start each day with profound biblical insights and practical applications for modern Christian living.</p>
                                <div class="card-price">R 349.99</div>
                                <div class="card-actions">
                                    <button class="btn btn-primary btn-small" onclick="addToCart('Morning Reflections: 365 Days with God', 349.99, 'book')">
                                        <i class="fas fa-cart-plus"></i> Add to Cart
                                    </button>
                                    <button class="btn btn-outline btn-small" onclick="previewItem('Morning Reflections: 365 Days with God', 'Start each day with profound biblical insights and practical applications for modern Christian living.', 349.99)">
                                        <i class="fas fa-eye"></i> Preview
                                    </button>
                                </div>
                            </div>
                        </div>

                        <div class="card">
                            <div class="card-badge">Live Online</div>
                            <div class="card-image">Biblical Leadership</div>
                            <div class="card-content">
                                <h3 class="card-title">Biblical Leadership Principles</h3>
                                <p class="card-meta">Facilitated by Dr. Sarah Johnson</p>
                                <p class="card-description">Learn timeless leadership principles from Scripture and apply them to modern ministry challenges.</p>
                                <div class="card-price">R 499.99</div>
                                <div class="card-actions">
                                    <button class="btn btn-primary btn-small" onclick="registerForWorkshop('Biblical Leadership Principles', 499.99)">
                                        <i class="fas fa-user-plus"></i> Register Now
                                    </button>
                                    <button class="btn btn-outline btn-small" onclick="showWorkshopDetails('Biblical Leadership Principles', 'Learn timeless leadership principles from Scripture and apply them to modern ministry challenges.')">
                                        <i class="fas fa-info-circle"></i> Details
                                    </button>
                                </div>
                            </div>
                        </div>

                        <div class="card">
                            <div class="card-badge">Free Resource</div>
                            <div class="card-image">Prayer Guide</div>
                            <div class="card-content">
                                <h3 class="card-title">30-Day Prayer Challenge</h3>
                                <p class="card-meta">by The Definitive Word Team</p>
                                <p class="card-description">Transform your prayer life with this guided 30-day challenge designed to deepen your connection with God.</p>
                                <div class="card-price">Free</div>
                                <div class="card-actions">
                                    <button class="btn btn-primary btn-small" onclick="downloadResource('30-Day Prayer Challenge')">
                                        <i class="fas fa-download"></i> Download
                                    </button>
                                    <button class="btn btn-outline btn-small" onclick="previewItem('30-Day Prayer Challenge', 'Transform your prayer life with this guided 30-day challenge designed to deepen your connection with God.', 0)">
                                        <i class="fas fa-eye"></i> Preview
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Additional tabs would continue here with similar structure -->
        
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

    <!-- JavaScript -->
    <script>
        // ===== APPLICATION STATE =====
        let currentUser = null;
        let cart = [];
        let currentTab = 'home';
        let currentAuthTab = 'login';
        let selectedLoginType = 'regular';
        let currentAuthStep = 'loginType';
        let diagnostics = {
            appState: 'loading',
            authentication: 'unknown',
            cartSystem: 'unknown',
            uiComponents: 'unknown',
            dataStorage: 'unknown',
            modals: 'unknown'
        };

        // ===== DIAGNOSTIC SYSTEM =====
        function runDiagnostics() {
            console.log('=== RUNNING FULL DIAGNOSTICS ===');
            
            // Test Application State
            try {
                diagnostics.appState = currentUser ? 'authenticated' : 'anonymous';
                console.log('✓ Application state: ' + diagnostics.appState);
            } catch (e) {
                diagnostics.appState = 'error';
                console.error('✗ Application state error: ' + e.message);
            }

            // Test Authentication System
            try {
                const authModal = document.getElementById('authModal');
                diagnostics.authentication = authModal ? 'ready' : 'missing';
                console.log('✓ Authentication system: ' + diagnostics.authentication);
            } catch (e) {
                diagnostics.authentication = 'error';
                console.error('✗ Authentication system error: ' + e.message);
            }

            // Test Cart System
            try {
                const cartCount = document.getElementById('cartCount');
                diagnostics.cartSystem = cartCount ? 'ready' : 'missing';
                console.log('✓ Cart system: ' + diagnostics.cartSystem);
            } catch (e) {
                diagnostics.cartSystem = 'error';
                console.error('✗ Cart system error: ' + e.message);
            }

            // Test UI Components
            try {
                const mainContent = document.getElementById('mainContent');
                diagnostics.uiComponents = mainContent ? 'ready' : 'missing';
                console.log('✓ UI components: ' + diagnostics.uiComponents);
            } catch (e) {
                diagnostics.uiComponents = 'error';
                console.error('✗ UI components error: ' + e.message);
            }

            // Test Data Storage
            try {
                localStorage.setItem('test', 'test');
                localStorage.removeItem('test');
                diagnostics.dataStorage = 'working';
                console.log('✓ Data storage: ' + diagnostics.dataStorage);
            } catch (e) {
                diagnostics.dataStorage = 'error';
                console.error('✗ Data storage error: ' + e.message);
            }

            // Test Modals
            try {
                const modals = document.querySelectorAll('.modal');
                diagnostics.modals = modals.length > 0 ? 'ready' : 'missing';
                console.log('✓ Modals: ' + diagnostics.modals + ' (' + modals.length + ' found)');
            } catch (e) {
                diagnostics.modals = 'error';
                console.error('✗ Modals error: ' + e.message);
            }

            updateDiagnosticDisplay();
            showNotification('Diagnostics completed successfully!', 'success');
        }

        function updateDiagnosticDisplay() {
            const diagnosticResults = document.getElementById('diagnosticResults');
            diagnosticResults.innerHTML = '';

            for (const [system, status] of Object.entries(diagnostics)) {
                const item = document.createElement('div');
                item.className = 'diagnostic-item';
                
                const statusClass = status === 'ready' || status === 'working' || status === 'authenticated' ? 
                    'status-ok' : status === 'unknown' ? 'status-warning' : 'status-error';
                
                item.innerHTML = `
                    <div class="status-indicator ${statusClass}"></div>
                    <div>${system}: ${status}</div>
                `;
                
                diagnosticResults.appendChild(item);
            }
        }

        // ===== REFRESH FUNCTION =====
        function refreshApplication() {
            showNotification('Refreshing application...', 'warning');
            
            // Reset application state
            currentUser = null;
            cart = [];
            currentTab = 'home';
            currentAuthTab = 'login';
            selectedLoginType = 'regular';
            currentAuthStep = 'loginType';
            
            // Reset UI elements
            document.getElementById('loginButton').innerHTML = '<i class="fas fa-user"></i> Sign In';
            document.getElementById('cartCount').textContent = '0';
            
            // Close all modals
            document.querySelectorAll('.modal').forEach(modal => {
                modal.style.display = 'none';
            });
            
            // Reset auth modal to first step
            document.getElementById('loginTypeStep').classList.add('active');
            document.getElementById('loginFormStep').classList.remove('active');
            document.getElementById('profileStep').classList.remove('active');
            
            // Clear form fields
            document.getElementById('loginEmail').value = '';
            document.getElementById('loginPassword').value = '';
            document.getElementById('signupName').value = '';
            document.getElementById('signupEmail').value = '';
            document.getElementById('signupPassword').value = '';
            document.getElementById('signupConfirm').value = '';
            
            // Reset login options
            document.querySelectorAll('.login-option').forEach(option => {
                option.classList.remove('active');
            });
            document.querySelectorAll('.login-option')[0].classList.add('active');
            
            // Reset tabs
            switchTab('home');
            
            // Run diagnostics
            setTimeout(() => {
                runDiagnostics();
                showNotification('Application refreshed successfully!', 'success');
            }, 500);
        }

        // ===== MODAL MANAGEMENT =====
        function openModal(modalId) {
            try {
                document.getElementById(modalId).style.display = 'flex';
            } catch (e) {
                console.error('Error opening modal: ' + e.message);
                showNotification('Error opening dialog. Please try again.', 'error');
            }
        }

        function closeModal(modalId) {
            try {
                document.getElementById(modalId).style.display = 'none';
            } catch (e) {
                console.error('Error closing modal: ' + e.message);
            }
        }

        // Close modals when clicking outside
        window.onclick = function(event) {
            const modals = document.getElementsByClassName('modal');
            for (let i = 0; i < modals.length; i++) {
                if (event.target == modals[i]) {
                    modals[i].style.display = 'none';
                }
            }
        }

        // ===== AUTHENTICATION SYSTEM =====
        function selectLoginType(type) {
            try {
                selectedLoginType = type;
                document.querySelectorAll('.login-option').forEach(option => {
                    option.classList.remove('active');
                });
                event.currentTarget.classList.add('active');
            } catch (e) {
                console.error('Error selecting login type: ' + e.message);
                showNotification('Error selecting account type. Please try again.', 'error');
            }
        }

        function proceedToLoginForm() {
            try {
                document.getElementById('loginTypeStep').classList.remove('active');
                document.getElementById('loginFormStep').classList.add('active');
                currentAuthStep = 'loginForm';
            } catch (e) {
                console.error('Error proceeding to login form: ' + e.message);
                showNotification('Error navigating to login form. Please try again.', 'error');
            }
        }

        function goBackToLoginType() {
            try {
                document.getElementById('loginFormStep').classList.remove('active');
                document.getElementById('loginTypeStep').classList.add('active');
                currentAuthStep = 'loginType';
            } catch (e) {
                console.error('Error going back to login type: ' + e.message);
                showNotification('Error navigating back. Please try again.', 'error');
            }
        }

        function switchAuthTab(tab) {
            try {
                currentAuthTab = tab;
                document.getElementById('loginForm').style.display = tab === 'login' ? 'block' : 'none';
                document.getElementById('signupForm').style.display = tab === 'signup' ? 'block' : 'none';
                
                document.querySelectorAll('.auth-tab').forEach(tabElement => {
                    tabElement.classList.toggle('active', tabElement.textContent.includes(tab === 'login' ? 'Sign In' : 'Create Account'));
                });
            } catch (e) {
                console.error('Error switching auth tab: ' + e.message);
                showNotification('Error switching tabs. Please try again.', 'error');
            }
        }

        function performLogin() {
            try {
                const email = document.getElementById('loginEmail').value;
                const password = document.getElementById('loginPassword').value;

                if (!email || !password) {
                    showNotification('Please enter both email and password', 'error');
                    return;
                }

                // Check for admin login
                if (selectedLoginType === 'admin' && email === 'admin@definitiveword.org' && password === 'Admin123!') {
                    currentUser = {
                        email: email,
                        name: 'Administrator',
                        role: 'admin',
                        lastLogin: new Date().toISOString()
                    };
                    document.getElementById('loginButton').innerHTML = '<i class="fas fa-user-shield"></i> Admin';
                    showNotification(`Welcome, ${currentUser.name}! Admin privileges activated.`, 'success');
                    closeModal('authModal');
                    
                    // Show profile completion for new admin
                    showProfileCompletion();
                    return;
                }

                // For demo purposes - accept any login
                currentUser = {
                    email: email,
                    name: email.split('@')[0],
                    role: selectedLoginType,
                    lastLogin: new Date().toISOString()
                };
                
                document.getElementById('loginButton').innerHTML = `<i class="fas fa-user-check"></i> ${currentUser.name}`;
                showNotification(`Welcome back, ${currentUser.name}!`, 'success');
                closeModal('authModal');
                
                // Show profile completion for new users
                if (currentAuthTab === 'signup') {
                    showProfileCompletion();
                }
            } catch (e) {
                console.error('Error during login: ' + e.message);
                showNotification('Error during login. Please try again.', 'error');
            }
        }

        function performSignup() {
            try {
                const name = document.getElementById('signupName').value;
                const email = document.getElementById('signupEmail').value;
                const password = document.getElementById('signupPassword').value;
                const confirm = document.getElementById('signupConfirm').value;
                const acceptTerms = document.getElementById('acceptTerms').checked;

                if (!name || !email || !password || !confirm) {
                    showNotification('Please fill in all fields', 'error');
                    return;
                }

                if (password !== confirm) {
                    showNotification('Passwords do not match', 'error');
                    return;
                }

                if (password.length < 8) {
                    showNotification('Password must be at least 8 characters', 'error');
                    return;
                }

                if (!acceptTerms) {
                    showNotification('Please accept the Terms of Service and Privacy Policy', 'error');
                    return;
                }

                // Create new user
                currentUser = {
                    name: name,
                    email: email,
                    role: selectedLoginType,
                    joinDate: new Date().toISOString()
                };

                document.getElementById('loginButton').innerHTML = `<i class="fas fa-user-check"></i> ${name.split(' ')[0]}`;
                showNotification(`Welcome to The Definitive Word, ${name}!`, 'success');
                
                // Move to profile completion
                showProfileCompletion();
            } catch (e) {
                console.error('Error during signup: ' + e.message);
                showNotification('Error during registration. Please try again.', 'error');
            }
        }

        function showProfileCompletion() {
            try {
                document.getElementById('loginFormStep').classList.remove('active');
                document.getElementById('profileStep').classList.add('active');
                currentAuthStep = 'profile';
            } catch (e) {
                console.error('Error showing profile completion: ' + e.message);
                showNotification('Error navigating to profile setup. Please try again.', 'error');
            }
        }

        function skipProfileCompletion() {
            closeModal('authModal');
            showNotification('Profile setup skipped. You can complete it later in your account settings.', 'info');
        }

        function completeProfile() {
            try {
                const location = document.getElementById('profileLocation').value;
                const church = document.getElementById('profileChurch').value;
                
                if (currentUser) {
                    currentUser.location = location;
                    currentUser.church = church;
                }
                
                closeModal('authModal');
                showNotification('Profile completed successfully!', 'success');
            } catch (e) {
                console.error('Error completing profile: ' + e.message);
                showNotification('Error saving profile. Please try again.', 'error');
            }
        }

        function showForgotPassword() {
            try {
                closeModal('authModal');
                openModal('forgotPasswordModal');
            } catch (e) {
                console.error('Error showing forgot password: ' + e.message);
                showNotification('Error opening password reset. Please try again.', 'error');
            }
        }

        function showLoginForm() {
            try {
                closeModal('forgotPasswordModal');
                openModal('authModal');
            } catch (e) {
                console.error('Error showing login form: ' + e.message);
                showNotification('Error navigating to login. Please try again.', 'error');
            }
        }

        function sendPasswordReset() {
            try {
                const email = document.getElementById('resetEmail').value;
                
                if (!email) {
                    showNotification('Please enter your email address', 'error');
                    return;
                }
                
                closeModal('forgotPasswordModal');
                showNotification(`Password reset link sent to ${email}. Please check your inbox.`, 'success');
            } catch (e) {
                console.error('Error sending password reset: ' + e.message);
                showNotification('Error sending reset link. Please try again.', 'error');
            }
        }

        // ===== SETTINGS MANAGEMENT =====
        function switchSettingsTab(tab) {
            try {
                document.querySelectorAll('.settings-tab').forEach(tabElement => {
                    tabElement.style.display = 'none';
                });
                
                document.querySelectorAll('.auth-tab').forEach(tabElement => {
                    tabElement.classList.remove('active');
                });
                
                document.getElementById(`${tab}Settings`).style.display = 'block';
                document.querySelector(`.auth-tab[onclick="switchSettingsTab('${tab}')"]`).classList.add('active');
            } catch (e) {
                console.error('Error switching settings tab: ' + e.message);
                showNotification('Error switching settings tab. Please try again.', 'error');
            }
        }

        function saveAccountSettings() {
            showNotification('Account settings saved successfully!', 'success');
        }

        function saveNotificationSettings() {
            showNotification('Notification preferences updated!', 'success');
        }

        function savePrivacySettings() {
            showNotification('Privacy settings saved!', 'success');
        }

        // ===== TAB MANAGEMENT =====
        function switchTab(tabName) {
            try {
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
            } catch (e) {
                console.error('Error switching tab: ' + e.message);
                showNotification('Error navigating to page. Please try again.', 'error');
            }
        }

        // ===== CART MANAGEMENT =====
        function addToCart(itemName, price, type) {
            try {
                if (!currentUser) {
                    showNotification('Please sign in to add items to your cart', 'error');
                    openModal('authModal');
                    return;
                }
                
                cart.push({ 
                    name: itemName, 
                    price: price, 
                    type: type,
                    id: Date.now() + Math.random()
                });
                updateCartDisplay();
                showNotification(`"${itemName}" added to cart!`, 'success');
            } catch (e) {
                console.error('Error adding to cart: ' + e.message);
                showNotification('Error adding item to cart. Please try again.', 'error');
            }
        }

        function updateCartDisplay() {
            try {
                document.getElementById('cartCount').textContent = cart.length;
                
                // Update cart modal if open
                const cartItems = document.getElementById('cartItems');
                const cartTotal = document.querySelector('.cart-total');
                
                if (cart.length === 0) {
                    cartItems.innerHTML = `
                        <div style="text-align: center; padding: 2rem; color: var(--dark-gray);">
                            <i class="fas fa-shopping-cart" style="font-size: 3rem; margin-bottom: 1rem; opacity: 0.5;"></i>
                            <h4>Your cart is empty</h4>
                            <p>Browse our store to add items to your cart</p>
                            <button class="btn btn-primary" onclick="closeModal('cartModal'); switchTab('books');" style="margin-top: 1rem;">
                                <i class="fas fa-book"></i> Browse Books
                            </button>
                        </div>
                    `;
                    cartTotal.style.display = 'none';
                } else {
                    cartItems.innerHTML = '';
                    let total = 0;
                    
                    cart.forEach((item, index) => {
                        total += item.price;
                        const cartItem = document.createElement('div');
                        cartItem.className = 'cart-item';
                        cartItem.style.display = 'flex';
                        cartItem.style.justifyContent = 'space-between';
                        cartItem.style.alignItems = 'center';
                        cartItem.style.padding = '1rem';
                        cartItem.style.borderBottom = '1px solid var(--medium-gray)';
                        cartItem.innerHTML = `
                            <div style="flex: 1;">
                                <div style="font-weight: 600; margin-bottom: 0.5rem;">${item.name}</div>
                                <div style="color: var(--primary-blue); font-weight: 600;">R ${item.price.toFixed(2)}</div>
                            </div>
                            <button class="btn btn-outline btn-small" onclick="removeFromCart(${index})">
                                <i class="fas fa-trash"></i> Remove
                            </button>
                        `;
                        cartItems.appendChild(cartItem);
                    });
                    
                    document.getElementById('cartTotalAmount').textContent = `R ${total.toFixed(2)}`;
                    cartTotal.style.display = 'block';
                }
            } catch (e) {
                console.error('Error updating cart display: ' + e.message);
                showNotification('Error updating cart. Please try again.', 'error');
            }
        }

        function removeFromCart(index) {
            try {
                const removedItem = cart[index];
                cart.splice(index, 1);
                updateCartDisplay();
                showNotification(`Removed ${removedItem.name} from cart`, 'info');
            } catch (e) {
                console.error('Error removing from cart: ' + e.message);
                showNotification('Error removing item from cart. Please try again.', 'error');
            }
        }

        function checkout() {
            try {
                if (cart.length === 0) {
                    showNotification('Your cart is empty', 'error');
                    return;
                }

                showNotification('Processing your order...', 'warning');
                setTimeout(() => {
                    const total = cart.reduce((sum, item) => sum + item.price, 0);
                    showNotification(`Order completed successfully! Total: R ${total.toFixed(2)}`, 'success');
                    cart = [];
                    updateCartDisplay();
                    closeModal('cartModal');
                }, 2000);
            } catch (e) {
                console.error('Error during checkout: ' + e.message);
                showNotification('Error during checkout. Please try again.', 'error');
            }
        }

        // ===== ACTION FUNCTIONS =====
        function registerForWorkshop(title, price) {
            try {
                if (!currentUser) {
                    showNotification('Please sign in to register for workshops', 'error');
                    openModal('authModal');
                    return;
                }
                addToCart(title, price, 'workshop');
            } catch (e) {
                console.error('Error registering for workshop: ' + e.message);
                showNotification('Error registering for workshop. Please try again.', 'error');
            }
        }

        function previewItem(title, description, price) {
            try {
                showNotification(`Preview: ${title} - R${price.toFixed(2)}\n\n${description}`, 'info');
            } catch (e) {
                console.error('Error previewing item: ' + e.message);
                showNotification('Error previewing item. Please try again.', 'error');
            }
        }

        function showWorkshopDetails(title, description) {
            try {
                showNotification(`Workshop Details: ${title}\n\n${description}`, 'info');
            } catch (e) {
                console.error('Error showing workshop details: ' + e.message);
                showNotification('Error showing details. Please try again.', 'error');
            }
        }

        function downloadResource(title) {
            try {
                if (!currentUser) {
                    showNotification('Please sign in to download resources', 'error');
                    openModal('authModal');
                    return;
                }
                showNotification(`Downloading "${title}"...`, 'success');
            } catch (e) {
                console.error('Error downloading resource: ' + e.message);
                showNotification('Error downloading resource. Please try again.', 'error');
            }
        }

        // ===== NOTIFICATION SYSTEM =====
        function showNotification(message, type = 'info') {
            try {
                // Create notification element
                const notification = document.createElement('div');
                notification.className = `notification ${type}`;
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
                        if (document.body.contains(notification)) {
                            document.body.removeChild(notification);
                        }
                    }, 300);
                }, 4000);
            } catch (e) {
                console.error('Error showing notification: ' + e.message);
                // Fallback to alert if notification system fails
                alert(message);
            }
        }

        // ===== INITIALIZATION =====
        document.addEventListener('DOMContentLoaded', function() {
            console.log('=== STARTING FULL DIAGNOSTICS ===');
            
            // Hide loading screen
            setTimeout(() => {
                try {
                    document.getElementById('loadingScreen').style.display = 'none';
                    showNotification('The Definitive Word loaded successfully! All systems operational.', 'success');
                } catch (e) {
                    console.error('Error during initialization: ' + e.message);
                    // If loading screen fails to hide, force it
                    const loadingScreen = document.getElementById('loadingScreen');
                    if (loadingScreen) loadingScreen.style.display = 'none';
                }
            }, 2000);

            // Set up tab switching for navigation links
            try {
                document.querySelectorAll('.nav-link').forEach(link => {
                    link.addEventListener('click', function(e) {
                        e.preventDefault();
                        const tabName = this.getAttribute('href').substring(1);
                        switchTab(tabName);
                    });
                });
            } catch (e) {
                console.error('Error setting up navigation: ' + e.message);
            }

            // Set up footer link functionality
            try {
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
            } catch (e) {
                console.error('Error setting up footer links: ' + e.message);
            }

            // Run initial diagnostics
            setTimeout(() => {
                runDiagnostics();
            }, 1000);

            console.log('=== DIAGNOSTICS COMPLETE ===');
        });

        // ===== ERROR BOUNDARY =====
        window.addEventListener('error', function(e) {
            console.error('Global error caught:', e.error);
            showNotification('An unexpected error occurred. Please refresh the page.', 'error');
            
            // Update diagnostics to show error
            diagnostics.appState = 'error';
            updateDiagnosticDisplay();
        });

        // ===== GLOBAL ERROR HANDLER =====
        window.onerror = function(message, source, lineno, colno, error) {
            console.error('Global error:', message, 'at', source, 'line', lineno);
            showNotification('A system error occurred. The application may not function properly.', 'error');
            return true;
        };

        console.log('The Definitive Word Platform - Professional Edition with Diagnostics');
    </script>
</body>
</html>
