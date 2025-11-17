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
        
        .header-actions {
            display: flex;
            align-items: center;
            gap: 1rem;
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
        
        .cart-icon {
            position: relative;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: var(--gold);
            color: var(--dark-blue);
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
            font-weight: bold;
        }
        
        .user-info {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            color: var(--white);
        }
        
        .user-avatar {
            width: 36px;
            height: 36px;
            border-radius: 50%;
            background-color: var(--gold);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            color: var(--dark-blue);
        }
        
        /* Main Content */
        .container {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1.5rem;
            min-height: 70vh;
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
            cursor: pointer;
            border: none;
        }
        
        .btn-preview {
            background-color: var(--prophetic-blue);
            color: var(--white);
        }
        
        .btn-buy {
            background-color: var(--gold);
            color: var(--dark-blue);
        }
        
        /* Cart Modal */
        .cart-modal {
            width: 90%;
            max-width: 800px;
        }
        
        .cart-items {
            max-height: 400px;
            overflow-y: auto;
            margin-bottom: 1.5rem;
        }
        
        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem;
            border-bottom: 1px solid #eee;
        }
        
        .cart-item-details {
            display: flex;
            align-items: center;
            gap: 1rem;
        }
        
        .cart-item-img {
            width: 60px;
            height: 60px;
            background-color: var(--light-blue);
            border-radius: 4px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
        }
        
        .cart-item-info h4 {
            color: var(--prophetic-blue);
            margin-bottom: 0.3rem;
        }
        
        .cart-item-price {
            color: var(--gold);
            font-weight: 600;
        }
        
        .cart-item-actions {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        
        .quantity-control {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        
        .quantity-btn {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            border: 1px solid #ddd;
            background: white;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .cart-total {
            display: flex;
            justify-content: space-between;
            font-size: 1.2rem;
            font-weight: 600;
            padding: 1rem 0;
            border-top: 2px solid #eee;
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
        
        /* Content Management */
        .content-management {
            background-color: var(--white);
            border-radius: 8px;
            padding: 2rem;
            margin-top: 2rem;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }
        
        .content-form {
            display: grid;
            gap: 1rem;
        }
        
        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
        }
        
        .btn-save {
            background-color: var(--gold);
            color: var(--dark-blue);
            padding: 0.8rem 1.5rem;
            margin-top: 1rem;
        }
        
        /* Order History */
        .order-history {
            margin-top: 2rem;
        }
        
        .order-item {
            background-color: var(--white);
            border-radius: 8px;
            padding: 1.5rem;
            margin-bottom: 1rem;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
        }
        
        .order-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1rem;
            padding-bottom: 0.5rem;
            border-bottom: 1px solid #eee;
        }
        
        .order-id {
            font-weight: 600;
            color: var(--prophetic-blue);
        }
        
        .order-date {
            color: #666;
        }
        
        .order-status {
            padding: 0.3rem 0.8rem;
            border-radius: 4px;
            font-size: 0.8rem;
            font-weight: 600;
        }
        
        .status-completed {
            background-color: #e6f7ee;
            color: #0d6832;
        }
        
        .status-pending {
            background-color: #fff8e6;
            color: #8a6d0d;
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
        
        /* Toast Notifications */
        .toast {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: var(--prophetic-blue);
            color: white;
            padding: 1rem 1.5rem;
            border-radius: 4px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
            z-index: 3000;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            transform: translateY(100px);
            opacity: 0;
            transition: all 0.3s ease;
        }
        
        .toast.show {
            transform: translateY(0);
            opacity: 1;
        }
        
        .toast.success {
            background-color: #0d6832;
        }
        
        .toast.error {
            background-color: #8a0d0d;
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
            
            .form-row {
                grid-template-columns: 1fr;
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
                    <li><a href="#" class="nav-link" data-page="admin">Admin Panel</a></li>
                </ul>
            </nav>
            
            <div class="header-actions">
                <div class="auth-buttons" id="authButtons">
                    <button class="btn btn-login" id="loginBtn">Login</button>
                    <button class="btn btn-register" id="registerBtn">Register</button>
                </div>
                <div class="user-info" id="userInfo" style="display: none;">
                    <div class="user-avatar" id="userAvatar">U</div>
                    <span id="userName">User</span>
                    <button class="btn btn-login" id="logoutBtn" style="margin-left: 10px;">Logout</button>
                </div>
                <div class="cart-icon" id="cartIcon">
                    <i class="fas fa-shopping-cart"></i>
                    <span class="cart-count">0</span>
                </div>
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
                    <button class="btn" style="background-color: var(--gold); color: var(--dark-blue); margin-top: 2rem; padding: 0.8rem 2rem;" id="beginJourneyBtn">Begin Your Journey</button>
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
            
            <div class="card-grid" id="booksGrid">
                <!-- Books will be dynamically loaded here -->
            </div>
        </section>

        <!-- Workshops Page -->
        <section id="workshops" class="page">
            <div class="page-header">
                <h2>Workshops & Training Programs</h2>
                <p>Transformative biblical training for spiritual growth and ministry development</p>
            </div>
            
            <div class="card-grid" id="workshopsGrid">
                <!-- Workshops will be dynamically loaded here -->
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
                        <input type="checkbox" id="follow-up"> I would like to be contacted for follow-up prayer
                    </label>
                </div>
                
                <button class="btn btn-login-submit" id="submitPrayerBtn">Submit Prayer Request</button>
            </div>
            
            <div style="margin-top: 3rem; text-align: center;">
                <h3 style="color: var(--prophetic-blue); margin-bottom: 1rem;">Join Our Prayer Community</h3>
                <p>Participate in our weekly prayer sessions and connect with other believers.</p>
                <button class="btn" style="background-color: var(--gold); color: var(--dark-blue); margin-top: 1rem;" id="joinPrayerBtn">Join Prayer Group</button>
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
                        <label><input type="checkbox" class="interest" value="books"> Ministry Books</label>
                        <label><input type="checkbox" class="interest" value="workshops"> Workshops</label>
                        <label><input type="checkbox" class="interest" value="prayer"> Prayer Groups</label>
                        <label><input type="checkbox" class="interest" value="community"> Online Community</label>
                    </div>
                </div>
                
                <button class="btn btn-login-submit" id="createAccountBtn">Create Account</button>
            </div>
        </section>

        <!-- Admin Panel -->
        <section id="admin" class="page">
            <div class="page-header">
                <h2>Admin Panel</h2>
                <p>Manage your ministry content and website settings</p>
            </div>
            
            <div class="content-management">
                <h3 style="color: var(--prophetic-blue); margin-bottom: 1.5rem;">Add New Book</h3>
                <div class="content-form">
                    <div class="form-group">
                        <label for="book-title">Book Title</label>
                        <input type="text" id="book-title" class="form-control" placeholder="Enter book title">
                    </div>
                    
                    <div class="form-group">
                        <label for="book-description">Description</label>
                        <textarea id="book-description" class="form-control" rows="3" placeholder="Enter book description"></textarea>
                    </div>
                    
                    <div class="form-row">
                        <div class="form-group">
                            <label for="book-price">Price ($)</label>
                            <input type="number" id="book-price" class="form-control" placeholder="Enter price">
                        </div>
                        
                        <div class="form-group">
                            <label for="book-icon">Icon Class (Font Awesome)</label>
                            <input type="text" id="book-icon" class="form-control" placeholder="fas fa-book">
                        </div>
                    </div>
                    
                    <button class="btn btn-save" id="addBookBtn">Add Book</button>
                </div>
            </div>
            
            <div class="content-management">
                <h3 style="color: var(--prophetic-blue); margin-bottom: 1.5rem;">Add New Workshop</h3>
                <div class="content-form">
                    <div class="form-group">
                        <label for="workshop-title">Workshop Title</label>
                        <input type="text" id="workshop-title" class="form-control" placeholder="Enter workshop title">
                    </div>
                    
                    <div class="form-group">
                        <label for="workshop-description">Description</label>
                        <textarea id="workshop-description" class="form-control" rows="3" placeholder="Enter workshop description"></textarea>
                    </div>
                    
                    <div class="form-row">
                        <div class="form-group">
                            <label for="workshop-price">Price ($)</label>
                            <input type="number" id="workshop-price" class="form-control" placeholder="Enter price">
                        </div>
                        
                        <div class="form-group">
                            <label for="workshop-icon">Icon Class (Font Awesome)</label>
                            <input type="text" id="workshop-icon" class="form-control" placeholder="fas fa-users">
                        </div>
                    </div>
                    
                    <button class="btn btn-save" id="addWorkshopBtn">Add Workshop</button>
                </div>
            </div>
            
            <div class="content-management">
                <h3 style="color: var(--prophetic-blue); margin-bottom: 1.5rem;">Edit Footer Content</h3>
                <div class="content-form">
                    <div class="form-group">
                        <label for="footer-about">About Text</label>
                        <textarea id="footer-about" class="form-control" rows="3" placeholder="Enter about text"></textarea>
                    </div>
                    
                    <div class="form-group">
                        <label for="footer-contact">Contact Email</label>
                        <input type="email" id="footer-contact" class="form-control" placeholder="Enter contact email">
                    </div>
                    
                    <div class="form-group">
                        <label for="footer-phone">Contact Phone</label>
                        <input type="text" id="footer-phone" class="form-control" placeholder="Enter contact phone">
                    </div>
                    
                    <div class="form-group">
                        <label for="footer-address">Address</label>
                        <input type="text" id="footer-address" class="form-control" placeholder="Enter address">
                    </div>
                    
                    <button class="btn btn-save" id="saveFooterBtn">Save Footer Changes</button>
                </div>
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

    <!-- Cart Modal -->
    <div class="modal" id="cartModal">
        <div class="modal-content cart-modal">
            <div class="modal-header">
                <h3>Your Shopping Cart</h3>
                <p>Review your items and proceed to checkout</p>
                <span class="close-modal">&times;</span>
            </div>
            <div class="modal-body">
                <div class="cart-items" id="cartItems">
                    <!-- Cart items will be dynamically loaded here -->
                </div>
                
                <div class="cart-total">
                    <span>Total:</span>
                    <span id="cartTotal">$0.00</span>
                </div>
                
                <div class="payment-section">
                    <h3 style="color: var(--prophetic-blue); margin-bottom: 1rem;">Payment Method</h3>
                    
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
                    
                    <button class="btn btn-login-submit" id="checkoutBtn">Complete Purchase</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Toast Notification -->
    <div class="toast" id="toast">
        <i class="fas fa-check-circle"></i>
        <span id="toastMessage">Operation completed successfully</span>
    </div>

    <!-- Footer -->
    <footer>
        <div class="footer-container">
            <div class="footer-section">
                <h3>The Definitive Word Ministry</h3>
                <p id="footer-about-text">Providing biblically-based spiritual guidance, resources, and community for believers worldwide.</p>
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
                    <li><i class="fas fa-map-marker-alt"></i> <span id="footer-address-text">123 Faith Avenue, Spiritual City</span></li>
                    <li><i class="fas fa-phone"></i> <span id="footer-phone-text">(555) 123-4567</span></li>
                    <li><i class="fas fa-envelope"></i> <span id="footer-email-text">contact@definitiveword.org</span></li>
                </ul>
            </div>
            
            <div class="footer-section">
                <h3>Connect With Us</h3>
                <div style="display: flex; gap: 1rem; margin-top: 1rem;">
                    <a href="https://facebook.com" target="_blank" style="color: white; font-size: 1.5rem;"><i class="fab fa-facebook"></i></a>
                    <a href="https://twitter.com" target="_blank" style="color: white; font-size: 1.5rem;"><i class="fab fa-twitter"></i></a>
                    <a href="https://instagram.com" target="_blank" style="color: white; font-size: 1.5rem;"><i class="fab fa-instagram"></i></a>
                    <a href="https://youtube.com" target="_blank" style="color: white; font-size: 1.5rem;"><i class="fab fa-youtube"></i></a>
                </div>
            </div>
        </div>
        
        <div class="copyright">
            <p>&copy; 2023 The Definitive Word Ministry. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Data storage for the application
        let cart = JSON.parse(localStorage.getItem('ministryCart')) || [];
        let books = JSON.parse(localStorage.getItem('ministryBooks')) || [
            {
                id: 1,
                title: "The Definitive Word: Volume 1",
                description: "Foundational teachings on key biblical principles for Christian living.",
                price: 24.99,
                icon: "fas fa-book-open"
            },
            {
                id: 2,
                title: "Prophetic Insights",
                description: "Understanding God's voice and prophetic ministry in the modern church.",
                price: 19.99,
                icon: "fas fa-bible"
            },
            {
                id: 3,
                title: "Prayer That Moves Mountains",
                description: "A practical guide to developing a powerful and effective prayer life.",
                price: 29.99,
                icon: "fas fa-praying-hands"
            }
        ];
        
        let workshops = JSON.parse(localStorage.getItem('ministryWorkshops')) || [
            {
                id: 1,
                title: "Biblical Interpretation Workshop",
                description: "Learn proper hermeneutics and exegesis for accurate Bible study.",
                price: 149.99,
                icon: "fas fa-users"
            },
            {
                id: 2,
                title: "Intercessory Prayer Workshop",
                description: "Develop effective prayer strategies based on biblical principles.",
                price: 99.99,
                icon: "fas fa-hands-helping"
            },
            {
                id: 3,
                title: "Ministry Leadership Intensive",
                description: "Equipping leaders for effective ministry based on biblical models.",
                price: 199.99,
                icon: "fas fa-church"
            }
        ];

        let users = JSON.parse(localStorage.getItem('ministryUsers')) || [];
        let currentUser = JSON.parse(localStorage.getItem('currentUser')) || null;
        let orders = JSON.parse(localStorage.getItem('ministryOrders')) || [];

        // DOM Elements
        const loginModal = document.getElementById('loginModal');
        const cartModal = document.getElementById('cartModal');
        const loginBtn = document.getElementById('loginBtn');
        const registerBtn = document.getElementById('registerBtn');
        const cartIcon = document.getElementById('cartIcon');
        const closeModalButtons = document.querySelectorAll('.close-modal');
        const beginJourneyBtn = document.getElementById('beginJourneyBtn');
        const submitPrayerBtn = document.getElementById('submitPrayerBtn');
        const joinPrayerBtn = document.getElementById('joinPrayerBtn');
        const createAccountBtn = document.getElementById('createAccountBtn');
        const addBookBtn = document.getElementById('addBookBtn');
        const addWorkshopBtn = document.getElementById('addWorkshopBtn');
        const saveFooterBtn = document.getElementById('saveFooterBtn');
        const checkoutBtn = document.getElementById('checkoutBtn');
        const booksGrid = document.getElementById('booksGrid');
        const workshopsGrid = document.getElementById('workshopsGrid');
        const cartItems = document.getElementById('cartItems');
        const cartTotal = document.getElementById('cartTotal');
        const cartCount = document.querySelector('.cart-count');
        const authButtons = document.getElementById('authButtons');
        const userInfo = document.getElementById('userInfo');
        const userName = document.getElementById('userName');
        const userAvatar = document.getElementById('userAvatar');
        const logoutBtn = document.getElementById('logoutBtn');
        const toast = document.getElementById('toast');
        const toastMessage = document.getElementById('toastMessage');

        // Initialize the application
        function init() {
            renderBooks();
            renderWorkshops();
            updateCartCount();
            
            // Load saved footer content
            loadFooterContent();
            
            // Check if user is logged in
            checkUserStatus();
        }

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

        // Modal Controls
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
        
        cartIcon.addEventListener('click', () => {
            renderCartItems();
            cartModal.classList.add('active');
        });
        
        closeModalButtons.forEach(button => {
            button.addEventListener('click', () => {
                loginModal.classList.remove('active');
                cartModal.classList.remove('active');
            });
        });
        
        window.addEventListener('click', (e) => {
            if (e.target === loginModal) {
                loginModal.classList.remove('active');
            }
            if (e.target === cartModal) {
                cartModal.classList.remove('active');
            }
        });

        // Button Actions
        beginJourneyBtn.addEventListener('click', () => {
            showToast('Welcome to The Definitive Word Ministry! We\'re excited to have you begin this spiritual journey with us.', 'success');
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
        
        submitPrayerBtn.addEventListener('click', () => {
            const name = document.getElementById('prayer-name').value;
            const email = document.getElementById('prayer-email').value;
            const category = document.getElementById('prayer-category').value;
            const request = document.getElementById('prayer-request').value;
            const followUp = document.getElementById('follow-up').checked;
            
            if (!name || !email || !category || !request) {
                showToast('Please fill in all required fields.', 'error');
                return;
            }
            
            // Save prayer request to localStorage
            const prayerRequests = JSON.parse(localStorage.getItem('prayerRequests')) || [];
            const newRequest = {
                id: Date.now(),
                name,
                email,
                category,
                request,
                followUp,
                date: new Date().toISOString()
            };
            prayerRequests.push(newRequest);
            localStorage.setItem('prayerRequests', JSON.stringify(prayerRequests));
            
            showToast(`Thank you, ${name}! Your prayer request has been submitted. Our prayer team will be lifting you up in prayer.`, 'success');
            
            // Reset form
            document.getElementById('prayer-name').value = '';
            document.getElementById('prayer-email').value = '';
            document.getElementById('prayer-category').value = '';
            document.getElementById('prayer-request').value = '';
            document.getElementById('follow-up').checked = false;
        });
        
        joinPrayerBtn.addEventListener('click', () => {
            showToast('Thank you for your interest in joining our prayer community! You will receive an email with details about our prayer groups and meeting times.', 'success');
        });
        
        createAccountBtn.addEventListener('click', () => {
            const firstName = document.getElementById('reg-firstname').value;
            const lastName = document.getElementById('reg-lastname').value;
            const email = document.getElementById('reg-email').value;
            const phone = document.getElementById('reg-phone').value;
            const password = document.getElementById('reg-password').value;
            const confirm = document.getElementById('reg-confirm').value;
            
            if (!firstName || !lastName || !email || !password || !confirm) {
                showToast('Please fill in all required fields.', 'error');
                return;
            }
            
            if (password !== confirm) {
                showToast('Passwords do not match.', 'error');
                return;
            }
            
            // Check if user already exists
            if (users.find(user => user.email === email)) {
                showToast('An account with this email already exists.', 'error');
                return;
            }
            
            const interests = Array.from(document.querySelectorAll('.interest:checked')).map(cb => cb.value);
            
            // Create new user
            const newUser = {
                id: Date.now(),
                firstName,
                lastName,
                email,
                phone,
                password, // In a real app, this would be hashed
                interests,
                date: new Date().toISOString()
            };
            
            users.push(newUser);
            localStorage.setItem('ministryUsers', JSON.stringify(users));
            
            // Log the user in
            currentUser = newUser;
            localStorage.setItem('currentUser', JSON.stringify(currentUser));
            checkUserStatus();
            
            showToast(`Thank you, ${firstName} ${lastName}! Your account has been created successfully. Welcome to The Definitive Word Ministry!`, 'success');
            
            // Reset form
            document.getElementById('reg-firstname').value = '';
            document.getElementById('reg-lastname').value = '';
            document.getElementById('reg-email').value = '';
            document.getElementById('reg-phone').value = '';
            document.getElementById('reg-password').value = '';
            document.getElementById('reg-confirm').value = '';
            document.querySelectorAll('.interest').forEach(cb => cb.checked = false);
            
            // Navigate to home page
            document.querySelectorAll('.nav-link').forEach(nav => {
                nav.classList.remove('active');
            });
            document.querySelector('[data-page="home"]').classList.add('active');
            
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById('home').classList.add('active');
        });
        
        addBookBtn.addEventListener('click', () => {
            const title = document.getElementById('book-title').value;
            const description = document.getElementById('book-description').value;
            const price = parseFloat(document.getElementById('book-price').value);
            const icon = document.getElementById('book-icon').value;
            
            if (!title || !description || !price || !icon) {
                showToast('Please fill in all fields.', 'error');
                return;
            }
            
            const newBook = {
                id: Date.now(),
                title,
                description,
                price,
                icon
            };
            
            books.push(newBook);
            localStorage.setItem('ministryBooks', JSON.stringify(books));
            renderBooks();
            
            showToast('Book added successfully!', 'success');
            
            // Reset form
            document.getElementById('book-title').value = '';
            document.getElementById('book-description').value = '';
            document.getElementById('book-price').value = '';
            document.getElementById('book-icon').value = '';
        });
        
        addWorkshopBtn.addEventListener('click', () => {
            const title = document.getElementById('workshop-title').value;
            const description = document.getElementById('workshop-description').value;
            const price = parseFloat(document.getElementById('workshop-price').value);
            const icon = document.getElementById('workshop-icon').value;
            
            if (!title || !description || !price || !icon) {
                showToast('Please fill in all fields.', 'error');
                return;
            }
            
            const newWorkshop = {
                id: Date.now(),
                title,
                description,
                price,
                icon
            };
            
            workshops.push(newWorkshop);
            localStorage.setItem('ministryWorkshops', JSON.stringify(workshops));
            renderWorkshops();
            
            showToast('Workshop added successfully!', 'success');
            
            // Reset form
            document.getElementById('workshop-title').value = '';
            document.getElementById('workshop-description').value = '';
            document.getElementById('workshop-price').value = '';
            document.getElementById('workshop-icon').value = '';
        });
        
        saveFooterBtn.addEventListener('click', () => {
            const about = document.getElementById('footer-about').value;
            const contact = document.getElementById('footer-contact').value;
            const phone = document.getElementById('footer-phone').value;
            const address = document.getElementById('footer-address').value;
            
            // Save to localStorage
            if (about) localStorage.setItem('footerAbout', about);
            if (contact) localStorage.setItem('footerContact', contact);
            if (phone) localStorage.setItem('footerPhone', phone);
            if (address) localStorage.setItem('footerAddress', address);
            
            // Update footer display
            loadFooterContent();
            
            showToast('Footer content updated successfully!', 'success');
            
            // Reset form
            document.getElementById('footer-about').value = '';
            document.getElementById('footer-contact').value = '';
            document.getElementById('footer-phone').value = '';
            document.getElementById('footer-address').value = '';
        });
        
        checkoutBtn.addEventListener('click', () => {
            if (cart.length === 0) {
                showToast('Your cart is empty. Please add items before checking out.', 'error');
                return;
            }
            
            const cardNumber = document.getElementById('card-number').value;
            const expiryDate = document.getElementById('expiry-date').value;
            const cvv = document.getElementById('cvv').value;
            
            if (!cardNumber || !expiryDate || !cvv) {
                showToast('Please fill in all payment details.', 'error');
                return;
            }
            
            // Create order
            const order = {
                id: 'ORD-' + Date.now(),
                items: [...cart],
                total: cart.reduce((total, item) => total + (item.price * item.quantity), 0),
                date: new Date().toISOString(),
                status: 'completed',
                userId: currentUser ? currentUser.id : null
            };
            
            orders.push(order);
            localStorage.setItem('ministryOrders', JSON.stringify(orders));
            
            // Clear cart
            cart = [];
            localStorage.setItem('ministryCart', JSON.stringify(cart));
            updateCartCount();
            cartModal.classList.remove('active');
            
            showToast('Payment processed successfully! Thank you for your purchase. You will receive a confirmation email shortly.', 'success');
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

        // Login Form Submission
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const email = document.getElementById('login-email').value;
            const password = document.getElementById('login-password').value;
            
            // Find user
            const user = users.find(u => u.email === email && u.password === password);
            
            if (user) {
                currentUser = user;
                localStorage.setItem('currentUser', JSON.stringify(currentUser));
                checkUserStatus();
                loginModal.classList.remove('active');
                showToast(`Welcome back, ${user.firstName}!`, 'success');
            } else {
                showToast('Invalid email or password. Please try again.', 'error');
            }
        });

        // Logout functionality
        logoutBtn.addEventListener('click', () => {
            currentUser = null;
            localStorage.removeItem('currentUser');
            checkUserStatus();
            showToast('You have been logged out successfully.', 'success');
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

        // Render Functions
        function renderBooks() {
            booksGrid.innerHTML = '';
            books.forEach(book => {
                const bookCard = document.createElement('div');
                bookCard.className = 'card';
                bookCard.innerHTML = `
                    <div class="card-img" style="background-color: #2a4da7;">
                        <i class="${book.icon}"></i>
                    </div>
                    <div class="card-body">
                        <h3 class="card-title">${book.title}</h3>
                        <p class="card-text">${book.description}</p>
                        <div class="card-price">$${book.price.toFixed(2)}</div>
                        <div class="card-actions">
                            <button class="btn-card btn-preview" onclick="previewItem('book', ${book.id})">Preview</button>
                            <button class="btn-card btn-buy" onclick="addToCart('book', ${book.id})">Add to Cart</button>
                        </div>
                    </div>
                `;
                booksGrid.appendChild(bookCard);
            });
        }
        
        function renderWorkshops() {
            workshopsGrid.innerHTML = '';
            workshops.forEach(workshop => {
                const workshopCard = document.createElement('div');
                workshopCard.className = 'card';
                workshopCard.innerHTML = `
                    <div class="card-img" style="background-color: #2a4da7;">
                        <i class="${workshop.icon}"></i>
                    </div>
                    <div class="card-body">
                        <h3 class="card-title">${workshop.title}</h3>
                        <p class="card-text">${workshop.description}</p>
                        <div class="card-price">$${workshop.price.toFixed(2)}</div>
                        <div class="card-actions">
                            <button class="btn-card btn-preview" onclick="previewItem('workshop', ${workshop.id})">Details</button>
                            <button class="btn-card btn-buy" onclick="addToCart('workshop', ${workshop.id})">Register</button>
                        </div>
                    </div>
                `;
                workshopsGrid.appendChild(workshopCard);
            });
        }
        
        function renderCartItems() {
            cartItems.innerHTML = '';
            
            if (cart.length === 0) {
                cartItems.innerHTML = '<p style="text-align: center; padding: 2rem;">Your cart is empty</p>';
                cartTotal.textContent = '$0.00';
                return;
            }
            
            let total = 0;
            
            cart.forEach(item => {
                const cartItem = document.createElement('div');
                cartItem.className = 'cart-item';
                cartItem.innerHTML = `
                    <div class="cart-item-details">
                        <div class="cart-item-img">
                            <i class="${item.icon}"></i>
                        </div>
                        <div class="cart-item-info">
                            <h4>${item.title}</h4>
                            <div class="cart-item-price">$${item.price.toFixed(2)}</div>
                        </div>
                    </div>
                    <div class="cart-item-actions">
                        <div class="quantity-control">
                            <button class="quantity-btn" onclick="updateQuantity(${item.id}, -1)">-</button>
                            <span>${item.quantity}</span>
                            <button class="quantity-btn" onclick="updateQuantity(${item.id}, 1)">+</button>
                        </div>
                        <button class="btn-card btn-preview" onclick="removeFromCart(${item.id})" style="padding: 0.3rem 0.8rem;">Remove</button>
                    </div>
                `;
                cartItems.appendChild(cartItem);
                total += item.price * item.quantity;
            });
            
            cartTotal.textContent = `$${total.toFixed(2)}`;
        }
        
        function loadFooterContent() {
            const about = localStorage.getItem('footerAbout');
            const contact = localStorage.getItem('footerContact');
            const phone = localStorage.getItem('footerPhone');
            const address = localStorage.getItem('footerAddress');
            
            if (about) document.getElementById('footer-about-text').textContent = about;
            if (contact) document.getElementById('footer-email-text').textContent = contact;
            if (phone) document.getElementById('footer-phone-text').textContent = phone;
            if (address) document.getElementById('footer-address-text').textContent = address;
        }
        
        function checkUserStatus() {
            if (currentUser) {
                authButtons.style.display = 'none';
                userInfo.style.display = 'flex';
                userName.textContent = currentUser.firstName;
                userAvatar.textContent = currentUser.firstName.charAt(0);
            } else {
                authButtons.style.display = 'flex';
                userInfo.style.display = 'none';
            }
        }
        
        function showToast(message, type = 'success') {
            toastMessage.textContent = message;
            toast.className = 'toast';
            toast.classList.add(type);
            toast.classList.add('show');
            
            setTimeout(() => {
                toast.classList.remove('show');
            }, 5000);
        }

        // Cart Functions
        function addToCart(type, id) {
            let item;
            if (type === 'book') {
                item = books.find(book => book.id === id);
            } else {
                item = workshops.find(workshop => workshop.id === id);
            }
            
            if (!item) return;
            
            const existingItem = cart.find(cartItem => cartItem.id === id && cartItem.type === type);
            
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({
                    ...item,
                    type,
                    quantity: 1
                });
            }
            
            localStorage.setItem('ministryCart', JSON.stringify(cart));
            updateCartCount();
            showToast(`${item.title} has been added to your cart!`, 'success');
        }
        
        function removeFromCart(id) {
            cart = cart.filter(item => item.id !== id);
            localStorage.setItem('ministryCart', JSON.stringify(cart));
            updateCartCount();
            renderCartItems();
        }
        
        function updateQuantity(id, change) {
            const item = cart.find(item => item.id === id);
            if (item) {
                item.quantity += change;
                if (item.quantity <= 0) {
                    removeFromCart(id);
                } else {
                    localStorage.setItem('ministryCart', JSON.stringify(cart));
                    updateCartCount();
                    renderCartItems();
                }
            }
        }
        
        function updateCartCount() {
            const count = cart.reduce((total, item) => total + item.quantity, 0);
            cartCount.textContent = count;
        }
        
        function previewItem(type, id) {
            let item;
            if (type === 'book') {
                item = books.find(book => book.id === id);
            } else {
                item = workshops.find(workshop => workshop.id === id);
            }
            
            if (!item) return;
            
            showToast(`Preview: ${item.title}\n\n${item.description}\n\nPrice: $${item.price.toFixed(2)}`, 'success');
        }

        // Initialize the application
        init();
    </script>
</body>
</html>
