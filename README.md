<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word Ministry Platform</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --prophetic-blue: #1a3a8f;
            --gold: #d4af37;
            --light-blue: #2a4da7;
            --white: #ffffff;
            --off-white: #f8f9fa;
            --dark-blue: #0d2568;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--off-white);
            color: #333;
            line-height: 1.6;
        }
        
        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--prophetic-blue), var(--dark-blue));
            color: var(--white);
            padding: 1rem 2rem;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo i {
            font-size: 2rem;
            color: var(--gold);
        }
        
        .logo h1 {
            font-size: 1.8rem;
            font-weight: 600;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }
        
        nav a {
            color: var(--white);
            text-decoration: none;
            font-weight: 500;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            transition: all 0.3s ease;
        }
        
        nav a:hover, nav a.active {
            background-color: rgba(255, 255, 255, 0.2);
            color: var(--gold);
        }
        
        .auth-buttons {
            display: flex;
            gap: 1rem;
        }
        
        .btn {
            padding: 0.6rem 1.2rem;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .btn-login {
            background-color: transparent;
            color: var(--white);
            border: 1px solid var(--white);
        }
        
        .btn-register {
            background-color: var(--gold);
            color: var(--dark-blue);
        }
        
        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        
        /* Main Content */
        .container {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1.5rem;
        }
        
        .page {
            display: none;
            animation: fadeIn 0.5s ease;
        }
        
        .page.active {
            display: block;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        .page-header {
            text-align: center;
            margin-bottom: 2rem;
            padding-bottom: 1rem;
            border-bottom: 2px solid var(--gold);
        }
        
        .page-header h2 {
            color: var(--prophetic-blue);
            font-size: 2.2rem;
            margin-bottom: 0.5rem;
        }
        
        .page-header p {
            color: #666;
            font-size: 1.1rem;
        }
        
        /* Login Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }
        
        .modal.active {
            display: flex;
        }
        
        .modal-content {
            background-color: var(--white);
            width: 90%;
            max-width: 450px;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }
        
        .modal-header {
            background: linear-gradient(135deg, var(--prophetic-blue), var(--dark-blue));
            color: var(--white);
            padding: 1.5rem;
            text-align: center;
            position: relative;
        }
        
        .modal-header h3 {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
        }
        
        .close-modal {
            position: absolute;
            top: 1rem;
            right: 1.5rem;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--white);
        }
        
        .modal-body {
            padding: 2rem;
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--prophetic-blue);
            font-weight: 500;
        }
        
        .form-control {
            width: 100%;
            padding: 0.8rem 1rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
            transition: border 0.3s ease;
        }
        
        .form-control:focus {
            border-color: var(--prophetic-blue);
            outline: none;
            box-shadow: 0 0 0 2px rgba(26, 58, 143, 0.2);
        }
        
        .remember-me {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }
        
        .remember-me input {
            width: auto;
        }
        
        .btn-login-submit {
            width: 100%;
            background: linear-gradient(135deg, var(--prophetic-blue), var(--dark-blue));
            color: var(--white);
            padding: 0.8rem;
            font-size: 1rem;
            margin-bottom: 1rem;
        }
        
        .forgot-password {
            text-align: center;
            display: block;
            color: var(--prophetic-blue);
            text-decoration: none;
        }
        
        /* Cards */
        .card-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }
        
        .card {
            background-color: var(--white);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
        }
        
        .card-img {
            height: 180px;
            background-color: var(--light-blue);
            display: flex;
            justify-content: center;
            align-items: center;
            color: var(--white);
            font-size: 3rem;
        }
        
        .card-body {
            padding: 1.5rem;
        }
        
        .card-title {
            color: var(--prophetic-blue);
            margin-bottom: 0.5rem;
            font-size: 1.3rem;
        }
        
        .card-text {
            color: #666;
            margin-bottom: 1rem;
        }
        
        .card-price {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--gold);
            margin-bottom: 1rem;
        }
        
        .card-actions {
            display: flex;
            gap: 0.5rem;
        }
        
        .btn-card {
            flex: 1;
            padding: 0.5rem;
            text-align: center;
            border-radius: 4px;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .btn-preview {
            background-color: var(--prophetic-blue);
            color: var(--white);
        }
        
        .btn-buy {
            background-color: var(--gold);
            color: var(--dark-blue);
        }
        
        /* Payment System */
        .payment-section {
            background-color: var(--white);
            border-radius: 8px;
            padding: 2rem;
            margin-top: 2rem;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }
        
        .payment-methods {
            display: flex;
            gap: 1rem;
            margin: 1.5rem 0;
            flex-wrap: wrap;
        }
        
        .payment-method {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.8rem 1.2rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .payment-method:hover, .payment-method.active {
            border-color: var(--prophetic-blue);
            background-color: rgba(26, 58, 143, 0.05);
        }
        
        .payment-method i {
            font-size: 1.5rem;
            color: var(--prophetic-blue);
        }
        
        /* Footer */
        footer {
            background: linear-gradient(135deg, var(--prophetic-blue), var(--dark-blue));
            color: var(--white);
            padding: 3rem 2rem 2rem;
            margin-top: 4rem;
        }
        
        .footer-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }
        
        .footer-section h3 {
            font-size: 1.3rem;
            margin-bottom: 1.5rem;
            padding-bottom: 0.5rem;
            border-bottom: 1px solid rgba(255, 255, 255, 0.2);
            color: var(--gold);
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 0.8rem;
        }
        
        .footer-links a {
            color: var(--white);
            text-decoration: none;
            transition: color 0.3s ease;
        }
        
        .footer-links a:hover {
            color: var(--gold);
        }
        
        .copyright {
            text-align: center;
            margin-top: 3rem;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.2);
            color: rgba(255, 255, 255, 0.7);
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                gap: 1rem;
            }
            
            nav ul {
                gap: 1rem;
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .card-grid {
                grid-template-columns: 1fr;
            }
            
            .payment-methods {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="header-container">
            <div class="logo">
                <i class="fas fa-bible"></i>
                <h1>The Definitive Word Ministry</h1>
            </div>
            
            <nav>
                <ul>
                    <li><a href="#" class="nav-link active" data-page="home">Home</a></li>
                    <li><a href="#" class="nav-link" data-page="books">Ministry Books</a></li>
                    <li><a href="#" class="nav-link" data-page="workshops">Workshops</a></li>
                    <li><a href="#" class="nav-link" data-page="prayer">Intercessory Prayer</a></li>
                    <li><a href="#" class="nav-link" data-page="registration">Registration</a></li>
                </ul>
            </nav>
            
            <div class="auth-buttons">
                <button class="btn btn-login" id="loginBtn">Login</button>
                <button class="btn btn-register" id="registerBtn">Register</button>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="container">
        <!-- Home Page -->
        <section id="home" class="page active">
            <div class="page-header">
                <h2>Welcome to The Definitive Word Ministry</h2>
                <p>Where God's Word Comes to Life Through Teaching, Prayer, and Community</p>
            </div>
            
            <div class="hero-section" style="text-align: center; margin: 3rem 0;">
                <div style="background: linear-gradient(135deg, var(--prophetic-blue), var(--dark-blue)); color: white; padding: 3rem; border-radius: 8px;">
                    <h2 style="font-size: 2.5rem; margin-bottom: 1rem;">Experience The Definitive Word</h2>
                    <p style="font-size: 1.2rem; max-width: 800px; margin: 0 auto;">Join our growing community of believers dedicated to studying God's Word, developing spiritual gifts, and supporting one another in faith.</p>
                    <button class="btn" style="background-color: var(--gold); color: var(--dark-blue); margin-top: 2rem; padding: 0.8rem 2rem;">Begin Your Journey</button>
                </div>
            </div>
            
            <div class="card-grid">
                <div class="card">
                    <div class="card-img">
                        <i class="fas fa-book"></i>
                    </div>
                    <div class="card-body">
                        <h3 class="card-title">Ministry Books</h3>
                        <p class="card-text">Explore our collection of biblically sound books and publications for spiritual growth.</p>
                        <a href="#" class="btn-card btn-preview" data-page="books">Browse Books</a>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-img">
                        <i class="fas fa-chalkboard-teacher"></i>
                    </div>
                    <div class="card-body">
                        <h3 class="card-title">Workshops & Training</h3>
                        <p class="card-text">Join our biblically-based workshops and training programs for spiritual development.</p>
                        <a href="#" class="btn-card btn-preview" data-page="workshops">View Programs</a>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-img">
                        <i class="fas fa-pray"></i>
                    </div>
                    <div class="card-body">
                        <h3 class="card-title">Intercessory Prayer</h3>
                        <p class="card-text">Submit prayer requests and join our dedicated prayer warriors community.</p>
                        <a href="#" class="btn-card btn-preview" data-page="prayer">Pray With Us</a>
                    </div>
                </div>
            </div>
        </section>

        <!-- Ministry Books Page -->
        <section id="books" class="page">
            <div class="page-header">
                <h2>Ministry Books & Publications</h2>
                <p>Biblically-based resources to strengthen your faith and understanding</p>
            </div>
            
            <div class="card-grid">
                <div class="card">
                    <div class="card-img" style="background-color: #2a4da7;">
                        <i class="fas fa-book-open"></i>
                    </div>
                    <div class="card-body">
                        <h3 class="card-title">The Definitive Word: Volume 1</h3>
                        <p class="card-text">Foundational teachings on key biblical principles for Christian living.</p>
                        <div class="card-price">$24.99</div>
                        <div class="card-actions">
                            <a href="#" class="btn-card btn-preview">Preview</a>
                            <a href="#" class="btn-card btn-buy">Purchase</a>
                        </div>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-img" style="background-color: #1a3a8f;">
                        <i class="fas fa-bible"></i>
                    </div>
                    <div class="card-body">
                        <h3 class="card-title">Prophetic Insights</h3>
                        <p class="card-text">Understanding God's voice and prophetic ministry in the modern church.</p>
                        <div class="card-price">$19.99</div>
                        <div class="card-actions">
                            <a href="#" class="btn-card btn-preview">Preview</a>
                            <a href="#" class="btn-card btn-buy">Purchase</a>
                        </div>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-img" style="background-color: #0d2568;">
                        <i class="fas fa-praying-hands"></i>
                    </div>
                    <div class="card-body">
                        <h3 class="card-title">Prayer That Moves Mountains</h3>
                        <p class="card-text">A practical guide to developing a powerful and effective prayer life.</p>
                        <div class="card-price">$29.99</div>
                        <div class="card-actions">
                            <a href="#" class="btn-card btn-preview">Preview</a>
                            <a href="#" class="btn-card btn-buy">Purchase</a>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Payment System -->
            <div class="payment-section">
                <h3 style="color: var(--prophetic-blue); margin-bottom: 1rem;">Secure Payment Options</h3>
                <p>All transactions are encrypted and secure. Choose your preferred payment method:</p>
                
                <div class="payment-methods">
                    <div class="payment-method active">
                        <i class="fab fa-cc-visa"></i>
                        <span>Credit/Debit Card</span>
                    </div>
                    <div class="payment-method">
                        <i class="fab fa-paypal"></i>
                        <span>PayPal</span>
                    </div>
                    <div class="payment-method">
                        <i class="fas fa-mobile-alt"></i>
                        <span>Mobile Money</span>
                    </div>
                    <div class="payment-method">
                        <i class="fas fa-university"></i>
                        <span>Bank Transfer</span>
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="card-number">Card Number</label>
                    <input type="text" id="card-number" class="form-control" placeholder="1234 5678 9012 3456">
                </div>
                
                <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem;">
                    <div class="form-group">
                        <label for="expiry-date">Expiry Date</label>
                        <input type="text" id="expiry-date" class="form-control" placeholder="MM/YY">
                    </div>
                    
                    <div class="form-group">
                        <label for="cvv">CVV</label>
                        <input type="text" id="cvv" class="form-control" placeholder="123">
                    </div>
                </div>
                
                <button class="btn btn-login-submit">Complete Purchase</button>
            </div>
        </section>

        <!-- Workshops Page -->
        <section id="workshops" class="page">
            <div class="page-header">
                <h2>Workshops & Training Programs</h2>
                <p>Transformative biblical training for spiritual growth and ministry development</p>
            </div>
            
            <div class="card-grid">
                <div class="card">
                    <div class="card-img" style="background-color: #2a4da7;">
                        <i class="fas fa-users"></i>
                    </div>
                    <div class="card-body">
                        <h3 class="card-title">Biblical Interpretation Workshop</h3>
                        <p class="card-text">Learn proper hermeneutics and exegesis for accurate Bible study.</p>
                        <div class="card-price">$149.99</div>
                        <div class="card-actions">
                            <a href="#" class="btn-card btn-preview">Details</a>
                            <a href="#" class="btn-card btn-buy">Register</a>
                        </div>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-img" style="background-color: #1a3a8f;">
                        <i class="fas fa-hands-helping"></i>
                    </div>
                    <div class="card-body">
                        <h3 class="card-title">Intercessory Prayer Workshop</h3>
                        <p class="card-text">Develop effective prayer strategies based on biblical principles.</p>
                        <div class="card-price">$99.99</div>
                        <div class="card-actions">
                            <a href="#" class="btn-card btn-preview">Details</a>
                            <a href="#" class="btn-card btn-buy">Register</a>
                        </div>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-img" style="background-color: #0d2568;">
                        <i class="fas fa-church"></i>
                    </div>
                    <div class="card-body">
                        <h3 class="card-title">Ministry Leadership Intensive</h3>
                        <p class="card-text">Equipping leaders for effective ministry based on biblical models.</p>
                        <div class="card-price">$199.99</div>
                        <div class="card-actions">
                            <a href="#" class="btn-card btn-preview">Details</a>
                            <a href="#" class="btn-card btn-buy">Register</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Prayer Page -->
        <section id="prayer" class="page">
            <div class="page-header">
                <h2>Intercessory Prayer</h2>
                <p>Submit your prayer requests and join our prayer community</p>
            </div>
            
            <div style="max-width: 800px; margin: 0 auto; background-color: white; padding: 2rem; border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
                <h3 style="color: var(--prophetic-blue); margin-bottom: 1.5rem;">Submit Prayer Request</h3>
                
                <div class="form-group">
                    <label for="prayer-name">Your Name</label>
                    <input type="text" id="prayer-name" class="form-control" placeholder="Enter your name">
                </div>
                
                <div class="form-group">
                    <label for="prayer-email">Email Address</label>
                    <input type="email" id="prayer-email" class="form-control" placeholder="Enter your email">
                </div>
                
                <div class="form-group">
                    <label for="prayer-category">Prayer Category</label>
                    <select id="prayer-category" class="form-control">
                        <option value="">Select a category</option>
                        <option value="healing">Healing</option>
                        <option value="guidance">Guidance</option>
                        <option value="family">Family</option>
                        <option value="finances">Finances</option>
                        <option value="salvation">Salvation</option>
                        <option value="other">Other</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label for="prayer-request">Prayer Request</label>
                    <textarea id="prayer-request" class="form-control" rows="5" placeholder="Please share your prayer request..."></textarea>
                </div>
                
                <div class="form-group">
                    <label>
                        <input type="checkbox"> I would like to be contacted for follow-up prayer
                    </label>
                </div>
                
                <button class="btn btn-login-submit">Submit Prayer Request</button>
            </div>
            
            <div style="margin-top: 3rem; text-align: center;">
                <h3 style="color: var(--prophetic-blue); margin-bottom: 1rem;">Join Our Prayer Community</h3>
                <p>Participate in our weekly prayer sessions and connect with other believers.</p>
                <button class="btn" style="background-color: var(--gold); color: var(--dark-blue); margin-top: 1rem;">Join Prayer Group</button>
            </div>
        </section>

        <!-- Registration Page -->
        <section id="registration" class="page">
            <div class="page-header">
                <h2>Registration</h2>
                <p>Register for products, workshops, and membership</p>
            </div>
            
            <div style="max-width: 800px; margin: 0 auto; background-color: white; padding: 2rem; border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
                <h3 style="color: var(--prophetic-blue); margin-bottom: 1.5rem;">Create Your Account</h3>
                
                <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem;">
                    <div class="form-group">
                        <label for="reg-firstname">First Name</label>
                        <input type="text" id="reg-firstname" class="form-control" placeholder="Enter your first name">
                    </div>
                    
                    <div class="form-group">
                        <label for="reg-lastname">Last Name</label>
                        <input type="text" id="reg-lastname" class="form-control" placeholder="Enter your last name">
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="reg-email">Email Address</label>
                    <input type="email" id="reg-email" class="form-control" placeholder="Enter your email">
                </div>
                
                <div class="form-group">
                    <label for="reg-phone">Phone Number</label>
                    <input type="tel" id="reg-phone" class="form-control" placeholder="Enter your phone number">
                </div>
                
                <div class="form-group">
                    <label for="reg-password">Password</label>
                    <input type="password" id="reg-password" class="form-control" placeholder="Create a password">
                </div>
                
                <div class="form-group">
                    <label for="reg-confirm">Confirm Password</label>
                    <input type="password" id="reg-confirm" class="form-control" placeholder="Confirm your password">
                </div>
                
                <div class="form-group">
                    <label>Interests (Select all that apply)</label>
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 0.5rem; margin-top: 0.5rem;">
                        <label><input type="checkbox"> Ministry Books</label>
                        <label><input type="checkbox"> Workshops</label>
                        <label><input type="checkbox"> Prayer Groups</label>
                        <label><input type="checkbox"> Online Community</label>
                    </div>
                </div>
                
                <button class="btn btn-login-submit">Create Account</button>
            </div>
        </section>
    </main>

    <!-- Login Modal -->
    <div class="modal" id="loginModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Member Login</h3>
                <p>Access your account and spiritual resources</p>
                <span class="close-modal">&times;</span>
            </div>
            <div class="modal-body">
                <form id="loginForm">
                    <div class="form-group">
                        <label for="login-email">Email Address</label>
                        <input type="email" id="login-email" class="form-control" placeholder="Enter your email" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="login-password">Password</label>
                        <input type="password" id="login-password" class="form-control" placeholder="Enter your password" required>
                    </div>
                    
                    <div class="remember-me">
                        <input type="checkbox" id="remember">
                        <label for="remember">Remember me</label>
                    </div>
                    
                    <button type="submit" class="btn btn-login-submit">Login to Your Account</button>
                    
                    <a href="#" class="forgot-password">Forgot your password?</a>
                </form>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="footer-container">
            <div class="footer-section">
                <h3>The Definitive Word Ministry</h3>
                <p>Providing biblically-based spiritual guidance, resources, and community for believers worldwide.</p>
            </div>
            
            <div class="footer-section">
                <h3>Quick Links</h3>
                <ul class="footer-links">
                    <li><a href="#" data-page="home">Home</a></li>
                    <li><a href="#" data-page="books">Ministry Books</a></li>
                    <li><a href="#" data-page="workshops">Workshops</a></li>
                    <li><a href="#" data-page="prayer">Intercessory Prayer</a></li>
                </ul>
            </div>
            
            <div class="footer-section">
                <h3>Contact Us</h3>
                <ul class="footer-links">
                    <li><i class="fas fa-map-marker-alt"></i> 123 Faith Avenue, Spiritual City</li>
                    <li><i class="fas fa-phone"></i> (555) 123-4567</li>
                    <li><i class="fas fa-envelope"></i> contact@definitiveword.org</li>
                </ul>
            </div>
            
            <div class="footer-section">
                <h3>Connect With Us</h3>
                <div style="display: flex; gap: 1rem; margin-top: 1rem;">
                    <a href="#" style="color: white; font-size: 1.5rem;"><i class="fab fa-facebook"></i></a>
                    <a href="#" style="color: white; font-size: 1.5rem;"><i class="fab fa-twitter"></i></a>
                    <a href="#" style="color: white; font-size: 1.5rem;"><i class="fab fa-instagram"></i></a>
                    <a href="#" style="color: white; font-size: 1.5rem;"><i class="fab fa-youtube"></i></a>
                </div>
            </div>
        </div>
        
        <div class="copyright">
            <p>&copy; 2023 The Definitive Word Ministry. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Page Navigation
        document.querySelectorAll('.nav-link, .btn-preview[data-page]').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                const pageId = this.getAttribute('data-page');
                
                // Update active nav link
                document.querySelectorAll('.nav-link').forEach(nav => {
                    nav.classList.remove('active');
                });
                this.classList.add('active');
                
                // Show selected page
                document.querySelectorAll('.page').forEach(page => {
                    page.classList.remove('active');
                });
                document.getElementById(pageId).classList.add('active');
                
                // Scroll to top
                window.scrollTo(0, 0);
            });
        });

        // Login Modal
        const loginModal = document.getElementById('loginModal');
        const loginBtn = document.getElementById('loginBtn');
        const registerBtn = document.getElementById('registerBtn');
        const closeModal = document.querySelector('.close-modal');
        
        loginBtn.addEventListener('click', () => {
            loginModal.classList.add('active');
        });
        
        registerBtn.addEventListener('click', () => {
            // Navigate to registration page
            document.querySelectorAll('.nav-link').forEach(nav => {
                nav.classList.remove('active');
            });
            document.querySelector('[data-page="registration"]').classList.add('active');
            
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById('registration').classList.add('active');
            
            window.scrollTo(0, 0);
        });
        
        closeModal.addEventListener('click', () => {
            loginModal.classList.remove('active');
        });
        
        window.addEventListener('click', (e) => {
            if (e.target === loginModal) {
                loginModal.classList.remove('active');
            }
        });

        // Login Form Submission
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            // In a real application, you would handle authentication here
            alert('Login functionality would be implemented with backend services');
            loginModal.classList.remove('active');
        });

        // Remember Me functionality
        const rememberCheckbox = document.getElementById('remember');
        const loginEmail = document.getElementById('login-email');
        
        // Check if credentials are stored
        if (localStorage.getItem('rememberMe') === 'true') {
            rememberCheckbox.checked = true;
            loginEmail.value = localStorage.getItem('rememberedEmail') || '';
        }
        
        // Update storage when checkbox changes
        rememberCheckbox.addEventListener('change', function() {
            if (this.checked) {
                localStorage.setItem('rememberMe', 'true');
                localStorage.setItem('rememberedEmail', loginEmail.value);
            } else {
                localStorage.removeItem('rememberMe');
                localStorage.removeItem('rememberedEmail');
            }
        });

        // Payment Method Selection
        document.querySelectorAll('.payment-method').forEach(method => {
            method.addEventListener('click', function() {
                document.querySelectorAll('.payment-method').forEach(m => {
                    m.classList.remove('active');
                });
                this.classList.add('active');
            });
        });
    </script>
</body>
</html>
