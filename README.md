<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Christian Resources & Ebooks</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        /* === PROFESSIONAL STYLES === */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

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
        }

        body {
            font-family: 'Georgia', 'Times New Roman', serif;
            color: var(--dark-text);
            line-height: 1.6;
            background: var(--white);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
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
        }

        .nav-link:hover {
            color: var(--accent-color);
        }

        .nav-link:after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background: var(--gold-color);
            transition: width 0.3s ease;
        }

        .nav-link:hover:after {
            width: 100%;
        }

        .dropdown {
            position: relative;
        }

        .dropdown-content {
            display: none;
            position: absolute;
            background: var(--white);
            min-width: 220px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.15);
            border-radius: 8px;
            top: 100%;
            left: 0;
            border-top: 3px solid var(--gold-color);
        }

        .dropdown:hover .dropdown-content {
            display: block;
        }

        .dropdown-content a {
            display: block;
            padding: 14px 20px;
            text-decoration: none;
            color: var(--dark-text);
            border-bottom: 1px solid var(--border);
            transition: all 0.3s ease;
        }

        .dropdown-content a:hover {
            background: var(--light-bg);
            color: var(--accent-color);
            padding-left: 25px;
        }

        .header-actions {
            display: flex;
            gap: 1.2rem;
            align-items: center;
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

        .cart-icon {
            position: relative;
            color: var(--primary-color);
            font-size: 1.4rem;
            text-decoration: none;
        }

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

        /* Hero Section */
        .hero-section {
            background: linear-gradient(135deg, var(--primary-color) 0%, #2c5282 100%);
            color: var(--white);
            padding: 120px 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero-section:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 100" fill="%23ffffff10"><path d="M500 50L550 30L600 50L650 30L700 50L750 30L800 50L850 30L900 50L950 30L1000 50L1000 100L0 100L0 50Z"/></svg>');
            background-size: cover;
        }

        .hero-title {
            font-size: 3.8rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            font-family: 'Georgia', serif;
            position: relative;
        }

        .hero-subtitle {
            font-size: 1.4rem;
            margin-bottom: 2.5rem;
            opacity: 0.9;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            line-height: 1.8;
        }

        .hero-actions {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
            position: relative;
        }

        /* Sections */
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

        .section-subtitle {
            text-align: center;
            color: var(--light-text);
            margin-bottom: 4rem;
            font-size: 1.3rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        /* Categories */
        .categories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2.5rem;
        }

        .category-card {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 2.5rem 2rem;
            text-align: center;
            transition: all 0.3s ease;
            text-decoration: none;
            color: var(--dark-text);
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            position: relative;
            overflow: hidden;
        }

        .category-card:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: var(--gold-color);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .category-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.15);
        }

        .category-card:hover:before {
            transform: scaleX(1);
        }

        .category-icon {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            color: var(--primary-color);
        }

        .category-card h3 {
            font-size: 1.4rem;
            margin-bottom: 1rem;
            color: var(--primary-color);
        }

        /* Books Grid */
        .books-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2.5rem;
        }

        .book-card {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 12px;
            overflow: hidden;
            transition: all 0.3s ease;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            position: relative;
        }

        .book-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.15);
        }

        .book-badge {
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

        .book-image {
            height: 220px;
            background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-weight: 600;
            font-size: 1.1rem;
            position: relative;
            overflow: hidden;
        }

        .book-image:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.1);
        }

        .book-info {
            padding: 2rem;
        }

        .book-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--primary-color);
            line-height: 1.4;
        }

        .book-author {
            color: var(--light-text);
            margin-bottom: 1rem;
            font-size: 1rem;
            font-style: italic;
        }

        .book-description {
            color: var(--light-text);
            margin-bottom: 1.5rem;
            font-size: 0.95rem;
            line-height: 1.6;
        }

        .book-price {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
            margin-bottom: 1.5rem;
        }

        .book-price .original {
            text-decoration: line-through;
            color: var(--light-text);
            font-size: 1.1rem;
            margin-right: 0.5rem;
        }

        .book-actions {
            display: flex;
            gap: 1rem;
        }

        .btn-small {
            padding: 10px 20px;
            font-size: 0.9rem;
            flex: 1;
            text-align: center;
        }

        /* Payment Methods */
        .payment-section {
            background: var(--light-bg);
            padding: 80px 0;
        }

        .payment-methods {
            display: flex;
            justify-content: center;
            gap: 3rem;
            flex-wrap: wrap;
            margin-top: 3rem;
        }

        .payment-method {
            background: var(--white);
            padding: 2rem;
            border-radius: 12px;
            text-align: center;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            min-width: 200px;
        }

        .payment-icon {
            font-size: 3rem;
            color: var(--primary-color);
            margin-bottom: 1rem;
        }

        /* Ministry Section */
        .ministry-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2.5rem;
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

        /* Blog Section */
        .blog-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
            gap: 2.5rem;
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
            font-size: 1.1rem;
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

        /* Footer */
        .footer {
            background: var(--primary-color);
            color: var(--white);
            padding: 80px 0 30px;
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

        /* Responsive Design */
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

            .hero-actions {
                flex-direction: column;
                align-items: center;
            }

            .books-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="container">
            <div class="header-content">
                <a href="#" class="logo">
                    The <span>Definitive</span> Word
                </a>
                
                <nav class="nav">
                    <a href="#home" class="nav-link">Home</a>
                    
                    <div class="dropdown">
                        <a href="#ministry" class="nav-link">Ministry</a>
                        <div class="dropdown-content">
                            <a href="#youth-ministry"><i class="fas fa-users"></i> Youth Ministry</a>
                            <a href="#womens-ministry"><i class="fas fa-female"></i> Women's Ministry</a>
                            <a href="#mens-ministry"><i class="fas fa-male"></i> Men's Ministry</a>
                            <a href="#children-ministry"><i class="fas fa-child"></i> Children's Ministry</a>
                        </div>
                    </div>
                    
                    <a href="#store" class="nav-link">Store</a>
                    <a href="#community" class="nav-link">Community</a>
                    <a href="#blog" class="nav-link">Blog</a>
                    <a href="#about" class="nav-link">About</a>
                </nav>

                <div class="header-actions">
                    <a href="#cart" class="cart-icon">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count">3</span>
                    </a>
                    <a href="#login" class="btn btn-outline">Sign In</a>
                    <a href="#register" class="btn btn-primary">Get Started</a>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero-section">
        <div class="container">
            <h1 class="hero-title">The Definitive Word</h1>
            <p class="hero-subtitle">Your trusted source for biblical teaching, spiritual growth resources, and Christian community. Discover timeless wisdom for modern living.</p>
            <div class="hero-actions">
                <a href="#store" class="btn btn-primary">Explore Resources</a>
                <a href="#ministry" class="btn btn-outline" style="background: rgba(255,255,255,0.1); color: white; border-color: white;">Join Our Ministry</a>
            </div>
        </div>
    </section>

    <!-- Store Section -->
    <section id="store" class="section">
        <div class="container">
            <h2 class="section-title">Featured Resources</h2>
            <p class="section-subtitle">Discover our curated collection of Christian books, study guides, and spiritual growth materials</p>
            
            <div class="books-grid">
                <!-- Book 1 -->
                <div class="book-card">
                    <div class="book-badge">Bestseller</div>
                    <div class="book-image">Daily Devotional Cover</div>
                    <div class="book-info">
                        <h3 class="book-title">Morning Reflections: 365 Days with God</h3>
                        <p class="book-author">by Dr. Michael Thompson</p>
                        <p class="book-description">Start each day with profound biblical insights and practical applications for modern Christian living.</p>
                        <div class="book-price">
                            <span class="original">$24.99</span>
                            $19.99
                        </div>
                        <div class="book-actions">
                            <a href="#" class="btn btn-primary btn-small">Add to Cart</a>
                            <a href="#" class="btn btn-outline btn-small">Preview</a>
                        </div>
                    </div>
                </div>

                <!-- Book 2 -->
                <div class="book-card">
                    <div class="book-badge">New Release</div>
                    <div class="book-image">Bible Study Cover</div>
                    <div class="book-info">
                        <h3 class="book-title">Understanding God's Grace</h3>
                        <p class="book-author">by Pastor Sarah Johnson</p>
                        <p class="book-description">A comprehensive study on the transformative power of grace in the life of every believer.</p>
                        <div class="book-price">$22.99</div>
                        <div class="book-actions">
                            <a href="#" class="btn btn-primary btn-small">Add to Cart</a>
                            <a href="#" class="btn btn-outline btn-small">Preview</a>
                        </div>
                    </div>
                </div>

                <!-- Book 3 -->
                <div class="book-card">
                    <div class="book-image">Christian Living Cover</div>
                    <div class="book-info">
                        <h3 class="book-title">Faith in Action: Living the Gospel</h3>
                        <p class="book-author">by Elder James Wilson</p>
                        <p class="book-description">Practical guidance for applying biblical principles to everyday challenges and opportunities.</p>
                        <div class="book-price">$18.99</div>
                        <div class="book-actions">
                            <a href="#" class="btn btn-primary btn-small">Add to Cart</a>
                            <a href="#" class="btn btn-outline btn-small">Preview</a>
                        </div>
                    </div>
                </div>
            </div>
            
            <div style="text-align: center; margin-top: 4rem;">
                <a href="#full-store" class="btn btn-outline">View All Resources</a>
            </div>
        </div>
    </section>

    <!-- Payment Methods Section -->
    <section class="payment-section">
        <div class="container">
            <h2 class="section-title">Secure Payment Options</h2>
            <p class="section-subtitle">We offer multiple secure payment methods for your convenience</p>
            
            <div class="payment-methods">
                <div class="payment-method">
                    <div class="payment-icon"><i class="fab fa-cc-visa"></i></div>
                    <h4>Credit Cards</h4>
                    <p>Visa, MasterCard, American Express</p>
                </div>
                
                <div class="payment-method">
                    <div class="payment-icon"><i class="fab fa-paypal"></i></div>
                    <h4>PayPal</h4>
                    <p>Secure online payments</p>
                </div>
                
                <div class="payment-method">
                    <div class="payment-icon"><i class="fas fa-mobile-alt"></i></div>
                    <h4>Mobile Money</h4>
                    <p>MPesa, Airtel Money, etc.</p>
                </div>
                
                <div class="payment-method">
                    <div class="payment-icon"><i class="fas fa-university"></i></div>
                    <h4>Bank Transfer</h4>
                    <p>Direct bank deposits</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Categories Section -->
    <section class="section" style="background: var(--light-bg);">
        <div class="container">
            <h2 class="section-title">Resource Categories</h2>
            <p class="section-subtitle">Browse our comprehensive collection of Christian resources</p>
            
            <div class="categories-grid">
                <a href="#devotionals" class="category-card">
                    <div class="category-icon"><i class="fas fa-book-open"></i></div>
                    <h3>Daily Devotionals</h3>
                    <p>Start your day with God's Word and spiritual guidance</p>
                </a>
                
                <a href="#bible-studies" class="category-card">
                    <div class="category-icon"><i class="fas fa-bible"></i></div>
                    <h3>Bible Studies</h3>
                    <p>In-depth exploration of Scripture and biblical principles</p>
                </a>
                
                <a href="#christian-living" class="category-card">
                    <div class="category-icon"><i class="fas fa-hands-helping"></i></div>
                    <h3>Christian Living</h3>
                    <p>Practical guidance for daily Christian walk</p>
                </a>
                
                <a href="#prayer" class="category-card">
                    <div class="category-icon"><i class="fas fa-pray"></i></div>
                    <h3>Prayer & Worship</h3>
                    <p>Resources to deepen your prayer life and worship</p>
                </a>
                
                <a href="#theology" class="category-card">
                    <div class="category-icon"><i class="fas fa-graduation-cap"></i></div>
                    <h3>Theology & Doctrine</h3>
                    <p>Study Christian beliefs and theological foundations</p>
                </a>
                
                <a href="#family" class="category-card">
                    <div class="category-icon"><i class="fas fa-home"></i></div>
                    <h3>Family & Marriage</h3>
                    <p>Building strong Christian families and marriages</p>
                </a>
            </div>
        </div>
    </section>

    <!-- Ministry Section -->
    <section id="ministry" class="section">
        <div class="container">
            <h2 class="section-title">Ministry Programs</h2>
            <p class="section-subtitle">Join our various ministry programs designed to nurture spiritual growth</p>
            
            <div class="ministry-grid">
                <div class="ministry-card">
                    <div class="ministry-icon"><i class="fas fa-users"></i></div>
                    <h3>Youth Ministry</h3>
                    <p>Engaging programs for young believers aged 13-25. Weekly meetings, retreats, leadership training, and mission opportunities.</p>
                    <a href="#youth-details" class="btn btn-outline" style="margin-top: 1.5rem;">Learn More</a>
                </div>
                
                <div class="ministry-card">
                    <div class="ministry-icon"><i class="fas fa-female"></i></div>
                    <h3>Women's Ministry</h3>
                    <p>Support and fellowship for women of all ages. Bible studies, prayer groups, annual conferences, and mentorship programs.</p>
                    <a href="#womens-details" class="btn btn-outline" style="margin-top: 1.5rem;">Learn More</a>
                </div>
                
                <div class="ministry-card">
                    <div class="ministry-icon"><i class="fas fa-male"></i></div>
                    <h3>Men's Ministry</h3>
                    <p>Building strong Christian men through accountability groups, workshops, service projects, and spiritual leadership training.</p>
                    <a href="#mens-details" class="btn btn-outline" style="margin-top: 1.5rem;">Learn More</a>
                </div>
            </div>
        </div>
    </section>

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
                    <a href="#home">Home</a>
                    <a href="#store">Resource Store</a>
                    <a href="#ministry">Ministry Programs</a>
                    <a href="#community">Community</a>
                    <a href="#blog">Blog & Articles</a>
                </div>
                
                <div class="footer-section">
                    <h4>Ministry</h4>
                    <a href="#youth-ministry">Youth Ministry</a>
                    <a href="#womens-ministry">Women's Ministry</a>
                    <a href="#mens-ministry">Men's Ministry</a>
                    <a href="#children-ministry">Children's Ministry</a>
                    <a href="#prayer-requests">Prayer Requests</a>
                </div>
                
                <div class="footer-section">
                    <h4>Support</h4>
                    <a href="#contact">Contact Us</a>
                    <a href="#faq">FAQ</a>
                    <a href="#shipping">Shipping Info</a>
                    <a href="#returns">Returns</a>
                    <a href="#privacy">Privacy Policy</a>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2024 The Definitive Word Ministry. All rights reserved. | Spreading God's Truth, Transforming Lives</p>
            </div>
        </div>
    </footer>

    <script>
        // Simple shopping cart functionality
        document.addEventListener('DOMContentLoaded', function() {
            // Smooth scrolling
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        target.scrollIntoView({
                            behavior: 'smooth',
                            block: 'start'
                        });
                    }
                });
            });

            // Add to cart functionality
            const addToCartButtons = document.querySelectorAll('.btn-primary');
            const cartCount = document.querySelector('.cart-count');
            let itemCount = 3;

            addToCartButtons.forEach(button => {
                button.addEventListener('click', function(e) {
                    if (this.textContent.includes('Add to Cart')) {
                        e.preventDefault();
                        itemCount++;
                        cartCount.textContent = itemCount;
                        
                        // Show added notification
                        const originalText = this.textContent;
                        this.textContent = 'Added!';
                        this.style.background = 'var(--success)';
                        
                        setTimeout(() => {
                            this.textContent = originalText;
                            this.style.background = '';
                        }, 2000);
                    }
                });
            });

            console.log('The Definitive Word Ministry Store loaded successfully!');
        });
    </script>
</body>
</html>
