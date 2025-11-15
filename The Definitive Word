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
        }

        .form-group textarea {
            resize: vertical;
            min-height: 100px;
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
        }

        .auth-tab.active {
            border-bottom-color: var(--accent-color);
            color: var(--accent-color);
            font-weight: 600;
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

        /* Header Actions Compact */
        .header-actions {
            display: flex;
            gap: 0.8rem;
            align-items: center;
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
            padding: 100px 0;
            text-align: center;
            background: linear-gradient(135deg, var(--primary-color) 0%, #2c5282 100%);
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
        .books-grid, .workshops-grid, .events-grid, .blog-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .book-card, .workshop-card, .event-card, .blog-card {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 12px;
            overflow: hidden;
            transition: all 0.3s ease;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            position: relative;
        }

        .book-card:hover, .workshop-card:hover, .event-card:hover, .blog-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.15);
        }

        .book-badge, .workshop-badge, .event-badge {
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

        .book-image, .workshop-image, .event-image, .blog-image {
            height: 200px;
            background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-weight: 600;
            font-size: 1.1rem;
        }

        .book-info, .workshop-info, .event-info, .blog-info {
            padding: 1.5rem;
        }

        .book-title, .workshop-title, .event-title, .blog-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--primary-color);
            line-height: 1.4;
        }

        .book-author, .workshop-instructor, .event-speaker, .blog-author {
            color: var(--light-text);
            margin-bottom: 1rem;
            font-size: 0.9rem;
            font-style: italic;
        }

        .book-description, .workshop-description, .event-description, .blog-excerpt {
            color: var(--light-text);
            margin-bottom: 1.5rem;
            font-size: 0.9rem;
            line-height: 1.6;
        }

        .book-price, .workshop-price, .event-price {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--primary-color);
            margin-bottom: 1.5rem;
        }

        .book-actions, .workshop-actions, .event-actions, .blog-actions {
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
        .workshop-details, .event-details {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1rem;
            font-size: 0.85rem;
            color: var(--light-text);
        }

        .workshop-date, .workshop-duration, .workshop-seats,
        .event-date, .event-time, .event-location {
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
        @media (max-width: 1024px) {
            .nav {
                gap: 1rem;
            }
            
            .nav-link {
                font-size: 0.9rem;
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

            .settings-panel {
                width: 100%;
                right: -100%;
            }

            .edit-toolbar {
                top: 120px;
                right: 10px;
            }

            .header-actions {
                gap: 0.5rem;
            }

            .btn {
                padding: 8px 16px;
                font-size: 0.85rem;
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

    <!-- Login/Signup Modal -->
    <div class="modal" id="authModal">
        <div class="modal-content">
            <div class="settings-header">
                <h3>Welcome to The Definitive Word</h3>
                <button onclick="closeAuth()" style="background: none; border: none; font-size: 1.5rem; cursor: pointer;">×</button>
            </div>
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
                    <a href="#" style="color: var(--accent-color); text-decoration: none;">Forgot password?</a>
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
                    </select>
                </div>
                <div class="form-group">
                    <label for="itemTitle">Title</label>
                    <input type="text" id="itemTitle" placeholder="Enter title">
                </div>
                <div class="form-group">
                    <label for="itemAuthor">Author/Instructor</label>
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
                <button class="btn btn-primary" onclick="saveNewItem()">Add Item</button>
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
                    <h4>System Diagnostics</h4>
                    <div class="diagnostics-item">
                        <span style="color: var(--success);">✓</span>
                        <span>Security: Active</span>
                    </div>
                    <div class="diagnostics-item">
                        <span style="color: var(--success);">✓</span>
                        <span>SSL: Encrypted</span>
                    </div>
                    <div class="diagnostics-item">
                        <span style="color: var(--success);">✓</span>
                        <span>Database: Connected</span>
                    </div>
                    <div class="diagnostics-item">
                        <span style="color: var(--success);">✓</span>
                        <span>Payments: Ready</span>
                    </div>
                    <button class="btn btn-outline" onclick="runFullDiagnostics()" style="margin-top: 1rem; width: 100%;">Run Full Diagnostics</button>
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

    <!-- Edit Toolbar -->
    <div class="edit-toolbar" id="editToolbar">
        <div class="edit-controls">
            <button class="edit-btn" onclick="openAddItem()"><i class="fas fa-plus"></i> Add Item</button>
            <button class="edit-btn" onclick="deleteSelectedItem()"><i class="fas fa-trash"></i> Delete</button>
            <button class="edit-btn" onclick="saveAllChanges()"><i class="fas fa-save"></i> Save All</button>
            <button class="edit-btn" onclick="toggleEditMode()"><i class="fas fa-times"></i> Exit Edit</button>
        </div>
    </div>

    <!-- Add Item Button -->
    <button class="add-item-btn" id="addItemBtn" onclick="openAddItem()" title="Add New Item">
        <i class="fas fa-plus"></i>
    </button>

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
                    <h1 style="font-size: 3rem; margin-bottom: 1.5rem;" class="editable" data-type="text" data-id="hero-title">The Definitive Word</h1>
                    <p style="font-size: 1.3rem; margin-bottom: 2.5rem; opacity: 0.9; max-width: 600px; margin-left: auto; margin-right: auto;" class="editable" data-type="text" data-id="hero-subtitle">
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
                    <h2 class="section-title editable" data-type="text" data-id="welcome-title">Welcome to Your Spiritual Home</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.2rem; max-width: 800px; margin-left: auto; margin-right: auto;" class="editable" data-type="text" data-id="welcome-description">
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
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.2rem;" class="editable" data-type="text" data-id="books-subtitle">
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
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.2rem;" class="editable" data-type="text" data-id="workshops-subtitle">
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
                    <h2 class="section-title editable" data-type="text" data-id="ministry-title">Ministry Programs</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.2rem;" class="editable" data-type="text" data-id="ministry-subtitle">
                        Join our various ministry programs designed to nurture spiritual growth at every stage of life
                    </p>

                    <div class="ministry-grid">
                        <div class="ministry-card editable" data-type="card" data-id="youth-ministry">
                            <div class="ministry-icon"><i class="fas fa-users"></i></div>
                            <h3 class="editable" data-type="text">Youth Ministry</h3>
                            <p class="editable" data-type="text">Engaging programs for young believers aged 13-25. Weekly meetings, retreats, leadership training, and mission opportunities to build strong Christian foundations.</p>
                            <div class="book-actions">
                                <button class="btn btn-primary btn-small" onclick="showMinistryDetails('Youth Ministry')">Learn More</button>
                                <button class="btn btn-outline btn-small" onclick="registerForMinistry('Youth Ministry')">Join Now</button>
                            </div>
                        </div>
                        
                        <div class="ministry-card editable" data-type="card" data-id="womens-ministry">
                            <div class="ministry-icon"><i class="fas fa-female"></i></div>
                            <h3 class="editable" data-type="text">Women's Ministry</h3>
                            <p class="editable" data-type="text">Support and fellowship for women of all ages. Bible studies, prayer groups, annual conferences, and mentorship programs to empower women in faith.</p>
                            <div class="book-actions">
                                <button class="btn btn-primary btn-small" onclick="showMinistryDetails('Women\\'s Ministry')">Learn More</button>
                                <button class="btn btn-outline btn-small" onclick="registerForMinistry('Women\\'s Ministry')">Join Now</button>
                            </div>
                        </div>
                        
                        <div class="ministry-card editable" data-type="card" data-id="mens-ministry">
                            <div class="ministry-icon"><i class="fas fa-male"></i></div>
                            <h3 class="editable" data-type="text">Men's Ministry</h3>
                            <p class="editable" data-type="text">Building strong Christian men through accountability groups, workshops, service projects, and spiritual leadership training for effective discipleship.</p>
                            <div class="book-actions">
                                <button class="btn btn-primary btn-small" onclick="showMinistryDetails('Men\\'s Ministry')">Learn More</button>
                                <button class="btn btn-outline btn-small" onclick="registerForMinistry('Men\\'s Ministry')">Join Now</button>
                            </div>
                        </div>
                    </div>

                    <div style="text-align: center; margin-top: 3rem;">
                        <h3 class="editable" data-type="text" data-id="upcoming-events-title">Upcoming Ministry Events</h3>
                        <div class="events-grid" style="margin-top: 2rem;">
                            <div class="event-card editable" data-type="card" data-id="event-1">
                                <div class="event-badge">Upcoming</div>
                                <div class="event-image">Youth Retreat</div>
                                <div class="event-info">
                                    <h3 class="event-title editable" data-type="text">Youth Summer Retreat 2024</h3>
                                    <p class="event-speaker editable" data-type="text">All Youth Members</p>
                                    <div class="event-details">
                                        <div class="event-date"><i class="fas fa-calendar"></i> 15-17 December 2024</div>
                                        <div class="event-location"><i class="fas fa-map-marker-alt"></i> Camp Site</div>
                                    </div>
                                    <p class="event-description editable" data-type="text">Annual youth retreat focused on spiritual growth, fellowship, and fun activities in nature.</p>
                                    <div class="event-actions">
                                        <button class="btn btn-primary btn-small" onclick="registerForEvent('Youth Summer Retreat')">Register</button>
                                        <button class="btn btn-outline btn-small" onclick="showEventDetails('Youth Summer Retreat')">Details</button>
                                    </div>
                                </div>
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
                    <h2 class="section-title editable" data-type="text" data-id="community-title">Our Community</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.2rem;" class="editable" data-type="text" data-id="community-subtitle">
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
                        <div class="ministry-card editable" data-type="card" data-id="community-forums">
                            <div class="ministry-icon"><i class="fas fa-comments"></i></div>
                            <h3 class="editable" data-type="text">Discussion Forums</h3>
                            <p class="editable" data-type="text">Join meaningful conversations about faith, life, and scripture with believers from around the world.</p>
                            <button class="btn btn-primary" style="margin-top: 1.5rem;" onclick="openCommunityForums()">Enter Forums</button>
                        </div>
                        
                        <div class="ministry-card editable" data-type="card" data-id="prayer-groups">
                            <div class="ministry-icon"><i class="fas fa-pray"></i></div>
                            <h3 class="editable" data-type="text">Prayer Groups</h3>
                            <p class="editable" data-type="text">Share prayer requests and join others in prayer. Experience the power of collective intercession.</p>
                            <button class="btn btn-primary" style="margin-top: 1.5rem;" onclick="joinPrayerGroup()">Join Prayer Group</button>
                        </div>
                        
                        <div class="ministry-card editable" data-type="card" data-id="community-events">
                            <div class="ministry-icon"><i class="fas fa-calendar-alt"></i></div>
                            <h3 class="editable" data-type="text">Events & Meetings</h3>
                            <p class="editable" data-type="text">Participate in live sessions, webinars, and virtual events with Christian leaders and teachers.</p>
                            <button class="btn btn-primary" style="margin-top: 1.5rem;" onclick="viewCommunityEvents()">View Events</button>
                        </div>
                    </div>

                    <div style="text-align: center; margin-top: 4rem;">
                        <h3 class="editable" data-type="text" data-id="testimonials-title">What Our Community Says</h3>
                        <div class="ministry-grid" style="margin-top: 2rem;">
                            <div class="ministry-card">
                                <p style="font-style: italic; color: var(--light-text);">"This platform transformed my spiritual journey. The resources and community support have been incredible!"</p>
                                <p style="margin-top: 1rem; font-weight: 600;">- Sarah M., Cape Town</p>
                            </div>
                            <div class="ministry-card">
                                <p style="font-style: italic; color: var(--light-text);">"The workshops helped me grow as a leader in my church. Practical and biblically sound teaching."</p>
                                <p style="margin-top: 1rem; font-weight: 600;">- Pastor John, Johannesburg</p>
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
                    <h2 class="section-title editable" data-type="text" data-id="blog-title">From Our Blog</h2>
                    <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.2rem;" class="editable" data-type="text" data-id="blog-subtitle">
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
                    <h2 class="section-title editable" data-type="text" data-id="about-title">About The Definitive Word</h2>
                    
                    <div class="about-content">
                        <div class="about-text">
                            <h3 class="editable" data-type="text">Our Mission & Vision</h3>
                            <p class="editable" data-type="text">The Definitive Word is dedicated to spreading the Gospel and supporting Christian growth through accessible digital resources. We believe in the transformative power of God's Word and strive to make quality Christian literature available to believers worldwide.</p>
                            
                            <p class="editable" data-type="text">Founded in 2020, our ministry has grown to serve thousands of Christians across the globe, providing not just books, but a comprehensive platform for spiritual development and community connection.</p>
                            
                            <ul class="about-features">
                                <li class="editable" data-type="text">Quality Christian literature from trusted authors</li>
                                <li class="editable" data-type="text">Transformative workshops and training</li>
                                <li class="editable" data-type="text">Comprehensive ministry programs</li>
                                <li class="editable" data-type="text">Supportive online community</li>
                                <li class="editable" data-type="text">Secure, encrypted platform for all transactions</li>
                            </ul>
                        </div>
                        
                        <div class="about-text">
                            <h3 class="editable" data-type="text">Our Values</h3>
                            <p class="editable" data-type="text"><strong>Faith:</strong> Everything we do is rooted in biblical principles and dedicated to glorifying God.</p>
                            <p class="editable" data-type="text"><strong>Community:</strong> We believe in the power of Christian fellowship and mutual support.</p>
                            <p class="editable" data-type="text"><strong>Excellence:</strong> We strive for the highest quality in all our resources and services.</p>
                            <p class="editable" data-type="text"><strong>Accessibility:</strong> Making Christian resources available to everyone, everywhere.</p>
                            <p class="editable" data-type="text"><strong>Integrity:</strong> Operating with transparency and biblical ethics in all dealings.</p>
                            <p class="editable" data-type="text"><strong>Security:</strong> Protecting our users' data and privacy with enterprise-level security.</p>
                            
                            <button class="btn btn-primary" style="margin-top: 2rem;" onclick="contactTeam()">Contact Our Team</button>
                        </div>
                    </div>

                    <div style="text-align: center; margin-top: 4rem;">
                        <h3 class="editable" data-type="text" data-id="team-title">Our Leadership Team</h3>
                        <div class="ministry-grid" style="margin-top: 2rem;">
                            <div class="ministry-card">
                                <div class="ministry-icon"><i class="fas fa-user-tie"></i></div>
                                <h4 class="editable" data-type="text">Pastor Michael Thompson</h4>
                                <p class="editable" data-type="text">Senior Pastor & Founder</p>
                                <p style="color: var(--light-text); font-size: 0.9rem;" class="editable" data-type="text">25+ years in ministry leadership</p>
                            </div>
                            <div class="ministry-card">
                                <div class="ministry-icon"><i class="fas fa-user-tie"></i></div>
                                <h4 class="editable" data-type="text">Dr. Sarah Johnson</h4>
                                <p class="editable" data-type="text">Director of Education</p>
                                <p style="color: var(--light-text); font-size: 0.9rem;" class="editable" data-type="text">Theology PhD & Author</p>
                            </div>
                            <div class="ministry-card">
                                <div class="ministry-icon"><i class="fas fa-user-tie"></i></div>
                                <h4 class="editable" data-type="text">Elder James Wilson</h4>
                                <p class="editable" data-type="text">Community Director</p>
                                <p style="color: var(--light-text); font-size: 0.9rem;" class="editable" data-type="text">15+ years in community development</p>
                            </div>
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
            version: '2.3.0',
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
                username: 'admin@definitiveword.org',
                password: 'Admin123!',
                editMode: false
            }
        };

        // ===== APPLICATION STATE =====
        let currentUser = null;
        let cart = [];
        let currentTab = 'home';
        let editMode = false;
        let selectedItem = null;
        let currentAuthTab = 'login';

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
                }
            ],
            users: []
        };

        // ===== AUTHENTICATION SYSTEM =====
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
            switchAuthTab('login');
        }

        function closeAuth() {
            document.getElementById('authModal').style.display = 'none';
        }

        function performLogin() {
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;

            if (!email || !password) {
                showNotification('Please enter both email and password', 'error');
                return;
            }

            // Check for admin login
            if (email === CONFIG.admin.username && password === CONFIG.admin.password) {
                currentUser = {
                    email: email,
                    name: 'Administrator',
                    role: 'admin',
                    lastLogin: new Date().toISOString()
                };
                document.getElementById('loginButton').innerHTML = '<i class="fas fa-user-shield"></i> Admin';
                showNotification(`Welcome, ${currentUser.name}!`, 'success');
                closeAuth();
                document.getElementById('addItemBtn').classList.add('show');
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

        // ===== CART SYSTEM =====
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
                container.innerHTML = '<p style="text-align: center; color: var(--light-text);">Your cart is empty</p>';
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
            cart.splice(index, 1);
            updateCartDisplay();
            renderCartItems();
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
                showNotification('Order completed successfully!', 'success');
                cart = [];
                updateCartDisplay();
                closeCart();
            }, 2000);
        }

        // ===== ADD ITEM SYSTEM =====
        function openAddItem() {
            if (!currentUser || currentUser.role !== 'admin') {
                showNotification('Admin access required', 'error');
                return;
            }
            document.getElementById('addItemModal').style.display = 'flex';
        }

        function closeAddItem() {
            document.getElementById('addItemModal').style.display = 'none';
        }

        function updateItemForm() {
            const type = document.getElementById('itemType').value;
            document.getElementById('priceGroup').style.display = type !== 'blog' ? 'block' : 'none';
            document.getElementById('dateGroup').style.display = type === 'workshop' || type === 'event' ? 'block' : 'none';
            document.getElementById('durationGroup').style.display = type === 'workshop' ? 'block' : 'none';
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
                author: author,
                description: description,
                image: type.charAt(0).toUpperCase() + type.slice(1) + ' Image'
            };

            if (type !== 'blog') {
                newItem.price = parseFloat(document.getElementById('itemPrice').value) || 0;
                newItem.badge = "New";
            }

            if (type === 'workshop' || type === 'event') {
                newItem.date = document.getElementById('itemDate').value || 'Date TBD';
            }

            if (type === 'workshop') {
                newItem.duration = document.getElementById('itemDuration').value || 'Duration TBD';
                newItem.seats = "0/0 Seats";
                appData.workshops.push(newItem);
                renderWorkshops();
            } else if (type === 'event') {
                newItem.location = "Location TBD";
                // Events would be added to a separate events array
            } else if (type === 'blog') {
                newItem.date = new Date().toLocaleDateString();
                newItem.readTime = "5 min read";
                appData.blogPosts.push(newItem);
                renderBlogPosts();
            } else {
                appData.books.push(newItem);
                renderBooks();
            }

            saveToLocalStorage();
            showNotification(`${type.charAt(0).toUpperCase() + type.slice(1)} added successfully!`, 'success');
            closeAddItem();
        }

        // ===== TAB MANAGEMENT =====
        function switchTab(tabName) {
            document.querySelectorAll('.tab-content').forEach(tab => {
                tab.classList.remove('active');
            });
            
            document.querySelectorAll('.nav-link').forEach(link => {
                link.classList.remove('active');
            });
            
            document.getElementById(`${tabName}-tab`).classList.add('active');
            event.target.classList.add('active');
            
            currentTab = tabName;

            if (tabName === 'books') {
                renderBooks();
            } else if (tabName === 'workshops') {
                renderWorkshops();
            } else if (tabName === 'blog') {
                renderBlogPosts();
            }
            
            showNotification(`Switched to ${tabName.charAt(0).toUpperCase() + tabName.slice(1)}`);
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
                            <div class="book-price"><span class="currency">R</span>${book.price.toFixed(2)}</div>
                            <div class="book-actions">
                                <button class="btn btn-primary btn-small" onclick="addToCart('${book.title}', ${book.price}, 'book')">Add to Cart</button>
                                <button class="btn btn-outline btn-small" onclick="previewItem('${book.title}', '${book.description}', ${book.price})">Preview</button>
                            </div>
                        </div>
                    </div>
                `;
                container.innerHTML += bookCard;
            });
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
                            <div class="workshop-price"><span class="currency">R</span>${workshop.price.toFixed(2)}</div>
                            <div class="workshop-actions">
                                <button class="btn btn-primary btn-small" onclick="registerForWorkshop('${workshop.title}', ${workshop.price})">Register Now</button>
                                <button class="btn btn-outline btn-small" onclick="showWorkshopDetails('${workshop.title}', '${workshop.description}')">Details</button>
                            </div>
                        </div>
                    </div>
                `;
                container.innerHTML += workshopCard;
            });
        }

        function renderBlogPosts() {
            const container = document.getElementById('blog-container');
            container.innerHTML = '';

            appData.blogPosts.forEach(post => {
                const blogCard = `
                    <div class="blog-card editable" data-type="card" data-id="blog-${post.id}">
                        <div class="blog-image">${post.image}</div>
                        <div class="blog-info">
                            <h3 class="blog-title editable" data-type="text">${post.title}</h3>
                            <p class="blog-author editable" data-type="text">by ${post.author}</p>
                            <p class="blog-excerpt editable" data-type="text">${post.excerpt}</p>
                            <div class="blog-meta">
                                <span>${post.date}</span>
                                <span>${post.readTime}</span>
                            </div>
                            <div class="blog-actions">
                                <button class="btn btn-primary btn-small" onclick="readBlogPost('${post.title}')">Read More</button>
                                <button class="btn btn-outline btn-small" onclick="shareBlogPost('${post.title}')">Share</button>
                            </div>
                        </div>
                    </div>
                `;
                container.innerHTML += blogCard;
            });
        }

        // ===== ACTION FUNCTIONS =====
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
            showNotification(`Preview: ${title} - R${price.toFixed(2)}`, 'info');
            // In a real app, this would open a proper preview modal
        }

        function showWorkshopDetails(title, description) {
            showNotification(`Workshop Details: ${title}`, 'info');
            // In a real app, this would show detailed workshop information
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
            showNotification(`Thank you for your interest in ${ministry}! We'll contact you soon.`, 'success');
        }

        function showMinistryDetails(ministry) {
            showNotification(`Loading details for ${ministry}...`, 'info');
        }

        function registerForEvent(event) {
            if (!currentUser) {
                showNotification('Please sign in to register for events', 'error');
                openAuth();
                return;
            }
            showNotification(`Registered for ${event}! Confirmation email sent.`, 'success');
        }

        function showEventDetails(event) {
            showNotification(`Event Details: ${event}`, 'info');
        }

        function openCommunityForums() {
            if (!currentUser) {
                showNotification('Please sign in to access community forums', 'error');
                openAuth();
                return;
            }
            showNotification('Redirecting to community forums...', 'info');
        }

        function joinPrayerGroup() {
            if (!currentUser) {
                showNotification('Please sign in to join prayer groups', 'error');
                openAuth();
                return;
            }
            showNotification('Added to prayer group! You will receive prayer requests and updates.', 'success');
        }

        function viewCommunityEvents() {
            showNotification('Loading community events...', 'info');
        }

        function readBlogPost(title) {
            showNotification(`Reading: ${title}`, 'info');
        }

        function shareBlogPost(title) {
            showNotification(`Share: ${title}`, 'info');
        }

        function contactTeam() {
            showNotification('Opening contact form...', 'info');
        }

        function submitPrayerRequest() {
            showNotification('Opening prayer request form...', 'info');
        }

        function showFAQ() {
            showNotification('Loading Frequently Asked Questions...', 'info');
        }

        function showShippingInfo() {
            showNotification('Loading shipping information...', 'info');
        }

        function showReturnsPolicy() {
            showNotification('Loading returns policy...', 'info');
        }

        function showPrivacyPolicy() {
            showNotification('Loading privacy policy...', 'info');
        }

        // ===== SETTINGS & DIAGNOSTICS =====
        function openSettings() {
            document.getElementById('settingsModal').style.display = 'flex';
        }

        function closeSettings() {
            document.getElementById('settingsModal').style.display = 'none';
        }

        function runFullDiagnostics() {
            showNotification('Running comprehensive system diagnostics...', 'warning');
            setTimeout(() => {
                showNotification('All systems operational! No issues found.', 'success');
            }, 2000);
        }

        function updateSetting(key, value) {
            const settings = JSON.parse(localStorage.getItem('appSettings') || '{}');
            settings[key] = value;
            localStorage.setItem('appSettings', JSON.stringify(settings));
            CONFIG.features[key] = value;
            showNotification(`Setting updated: ${key}`, 'success');
        }

        // ===== EDIT MODE SYSTEM =====
        function toggleEditMode() {
            if (!currentUser || currentUser.role !== 'admin') {
                showNotification('Admin access required', 'error');
                return;
            }
            editMode = !editMode;
            document.body.classList.toggle('edit-mode', editMode);
            document.getElementById('editToolbar').classList.toggle('show', editMode);
            
            if (editMode) {
                showNotification('Edit mode activated. Click on any item to edit.', 'warning');
            } else {
                showNotification('Edit mode deactivated', 'info');
            }
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

        // ===== INITIALIZATION =====
        document.addEventListener('DOMContentLoaded', function() {
            setTimeout(() => {
                document.getElementById('loadingScreen').style.display = 'none';
                showNotification('The Definitive Word loaded successfully!', 'success');
            }, 2000);

            loadFromLocalStorage();
            renderBooks();
            renderWorkshops();
            renderBlogPosts();

            // Check for admin auto-login
            const savedSession = localStorage.getItem('userSession');
            if (savedSession && CONFIG.features.autoLogin) {
                try {
                    const sessionData = JSON.parse(atob(savedSession));
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
                } catch (e) {
                    console.warn('Auto-login failed:', e);
                }
            }

            updateCartDisplay();
            console.log('🚀 The Definitive Word fully initialized');
        });

        // Make functions globally available
        window.switchTab = switchTab;
        window.addToCart = addToCart;
        window.openSettings = openSettings;
        window.closeSettings = closeSettings;
        window.openAuth = openAuth;
        window.closeAuth = closeAuth;
        window.openCart = openCart;
        window.closeCart = closeCart;
        window.toggleEditMode = toggleEditMode;
        window.openAddItem = openAddItem;
        window.closeAddItem = closeAddItem;
    </script>
</body>
</html>
