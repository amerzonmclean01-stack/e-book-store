<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NexusReads - Professional Ebook Store</title>
    <style>
        /* === PROFESSIONAL STYLES === */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #2c5530;
            --secondary-color: #4a7c59;
            --accent-color: #8fb996;
            --light-bg: #f8f9fa;
            --dark-text: #2d3748;
            --light-text: #718096;
            --white: #ffffff;
            --border: #e2e8f0;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
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
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
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
        }

        .logo span {
            color: var(--secondary-color);
        }

        .nav {
            display: flex;
            gap: 2rem;
            align-items: center;
        }

        .nav-link {
            color: var(--dark-text);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-link:hover {
            color: var(--primary-color);
        }

        .dropdown {
            position: relative;
        }

        .dropdown-content {
            display: none;
            position: absolute;
            background: var(--white);
            min-width: 200px;
            box-shadow: 0 8px 16px rgba(0,0,0,0.1);
            border-radius: 8px;
            top: 100%;
            left: 0;
        }

        .dropdown:hover .dropdown-content {
            display: block;
        }

        .dropdown-content a {
            display: block;
            padding: 12px 16px;
            text-decoration: none;
            color: var(--dark-text);
            border-bottom: 1px solid var(--border);
        }

        .dropdown-content a:hover {
            background: var(--light-bg);
        }

        .header-actions {
            display: flex;
            gap: 1rem;
            align-items: center;
        }

        .btn {
            padding: 10px 24px;
            border-radius: 6px;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            display: inline-block;
        }

        .btn-primary {
            background: var(--primary-color);
            color: var(--white);
        }

        .btn-primary:hover {
            background: var(--secondary-color);
            transform: translateY(-2px);
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

        /* Hero Section */
        .hero-section {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: var(--white);
            padding: 100px 0;
            text-align: center;
        }

        .hero-title {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
        }

        .hero-subtitle {
            font-size: 1.3rem;
            margin-bottom: 2.5rem;
            opacity: 0.9;
        }

        .hero-actions {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        /* Sections */
        .section {
            padding: 80px 0;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 3rem;
            color: var(--primary-color);
        }

        .section-subtitle {
            text-align: center;
            color: var(--light-text);
            margin-bottom: 4rem;
            font-size: 1.2rem;
        }

        /* Categories */
        .categories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .category-card {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 2rem;
            text-align: center;
            transition: all 0.3s ease;
            text-decoration: none;
            color: var(--dark-text);
        }

        .category-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            border-color: var(--accent-color);
        }

        .category-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        /* Books Grid */
        .books-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
        }

        .book-card {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 12px;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .book-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .book-image {
            height: 200px;
            background: linear-gradient(45deg, var(--accent-color), var(--secondary-color));
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-weight: 600;
            font-size: 1.1rem;
        }

        .book-info {
            padding: 1.5rem;
        }

        .book-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--dark-text);
        }

        .book-author {
            color: var(--light-text);
            margin-bottom: 1rem;
            font-size: 0.9rem;
        }

        .book-price {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--primary-color);
            margin-bottom: 1rem;
        }

        /* Ministry Section */
        .ministry-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .ministry-card {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 2rem;
            text-align: center;
        }

        .ministry-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: var(--primary-color);
        }

        /* Blog Section */
        .blog-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .blog-card {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 12px;
            overflow: hidden;
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
            padding: 1.5rem;
        }

        .blog-title {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: var(--dark-text);
        }

        .blog-excerpt {
            color: var(--light-text);
            margin-bottom: 1rem;
        }

        .blog-meta {
            color: var(--light-text);
            font-size: 0.9rem;
        }

        /* Community Section */
        .community-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            text-align: center;
            margin-bottom: 4rem;
        }

        .stat-card {
            padding: 2rem;
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

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
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
            background: var(--dark-text);
            color: var(--white);
            padding: 60px 0 20px;
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
        }

        .footer-section a {
            display: block;
            color: #cbd5e0;
            text-decoration: none;
            margin-bottom: 0.8rem;
            transition: color 0.3s ease;
        }

        .footer-section a:hover {
            color: var(--white);
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
                gap: 1rem;
            }

            .nav {
                flex-wrap: wrap;
                justify-content: center;
            }

            .hero-title {
                font-size: 2.5rem;
            }

            .about-content {
                grid-template-columns: 1fr;
            }

            .footer-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .hero-actions {
                flex-direction: column;
                align-items: center;
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
                    Nexus<span>Reads</span>
                </a>
                
                <nav class="nav">
                    <a href="#home" class="nav-link">Home</a>
                    
                    <div class="dropdown">
                        <a href="#ministry" class="nav-link">Ministry</a>
                        <div class="dropdown-content">
                            <a href="#youth-ministry">Youth Ministry</a>
                            <a href="#womens-ministry">Women's Ministry</a>
                            <a href="#mens-ministry">Men's Ministry</a>
                            <a href="#children-ministry">Children's Ministry</a>
                        </div>
                    </div>
                    
                    <a href="#store" class="nav-link">Store</a>
                    <a href="#community" class="nav-link">Community</a>
                    <a href="#blog" class="nav-link">Blog</a>
                    <a href="#about" class="nav-link">About Us</a>
                </nav>

                <div class="header-actions">
                    <a href="#login" class="btn btn-outline">Sign In</a>
                    <a href="#register" class="btn btn-primary">Get Started</a>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero-section">
        <div class="container">
            <h1 class="hero-title">Transform Your Spiritual Journey</h1>
            <p class="hero-subtitle">Discover inspiring Christian ebooks, connect with believers worldwide, and grow in your faith through our ministry resources.</p>
            <div class="hero-actions">
                <a href="#store" class="btn btn-primary">Explore Store</a>
                <a href="#ministry" class="btn btn-outline" style="background: rgba(255,255,255,0.2); color: white; border-color: white;">Ministry Programs</a>
            </div>
        </div>
    </section>

    <!-- Ministry Section -->
    <section id="ministry" class="section" style="background: var(--light-bg);">
        <div class="container">
            <h2 class="section-title">Ministry Programs</h2>
            <p class="section-subtitle">Join our various ministry programs designed to nurture spiritual growth</p>
            
            <div class="ministry-grid">
                <div class="ministry-card">
                    <div class="ministry-icon">🙋‍♂️</div>
                    <h3>Youth Ministry</h3>
                    <p>Engaging programs for young believers aged 13-25. Weekly meetings, retreats, and leadership training.</p>
                    <a href="#youth-details" class="btn btn-outline" style="margin-top: 1rem;">Learn More</a>
                </div>
                
                <div class="ministry-card">
                    <div class="ministry-icon">👩‍👧‍👦</div>
                    <h3>Women's Ministry</h3>
                    <p>Support and fellowship for women of all ages. Bible studies, prayer groups, and annual conferences.</p>
                    <a href="#womens-details" class="btn btn-outline" style="margin-top: 1rem;">Learn More</a>
                </div>
                
                <div class="ministry-card">
                    <div class="ministry-icon">👨‍👦‍👦</div>
                    <h3>Men's Ministry</h3>
                    <p>Building strong Christian men through accountability groups, workshops, and service projects.</p>
                    <a href="#mens-details" class="btn btn-outline" style="margin-top: 1rem;">Learn More</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Store Section -->
    <section id="store" class="section">
        <div class="container">
            <h2 class="section-title">Featured Ebooks</h2>
            <p class="section-subtitle">Browse our collection of inspirational Christian literature</p>
            
            <div class="books-grid">
                <!-- Book 1 -->
                <div class="book-card">
                    <div class="book-image">Daily Devotions</div>
                    <div class="book-info">
                        <h3 class="book-title">Morning with God</h3>
                        <p class="book-author">by Pastor John Smith</p>
                        <div class="book-price">$9.99</div>
                        <a href="#" class="btn btn-primary" style="width: 100%; text-align: center;">Add to Cart</a>
                    </div>
                </div>

                <!-- Book 2 -->
                <div class="book-card">
                    <div class="book-image">Bible Study</div>
                    <div class="book-info">
                        <h3 class="book-title">Understanding Grace</h3>
                        <p class="book-author">by Dr. Sarah Johnson</p>
                        <div class="book-price">$12.99</div>
                        <a href="#" class="btn btn-primary" style="width: 100%; text-align: center;">Add to Cart</a>
                    </div>
                </div>

                <!-- Book 3 -->
                <div class="book-card">
                    <div class="book-image">Christian Living</div>
                    <div class="book-info">
                        <h3 class="book-title">Faith in Action</h3>
                        <p class="book-author">by Michael Thompson</p>
                        <div class="book-price">$14.99</div>
                        <a href="#" class="btn btn-primary" style="width: 100%; text-align: center;">Add to Cart</a>
                    </div>
                </div>

                <!-- Book 4 -->
                <div class="book-card">
                    <div class="book-image">Prayer Guide</div>
                    <div class="book-info">
                        <h3 class="book-title">The Power of Prayer</h3>
                        <p class="book-author">by Elder Maria Garcia</p>
                        <div class="book-price">$8.99</div>
                        <a href="#" class="btn btn-primary" style="width: 100%; text-align: center;">Add to Cart</a>
                    </div>
                </div>
            </div>
            
            <div style="text-align: center; margin-top: 3rem;">
                <a href="#full-store" class="btn btn-outline">View All Books</a>
            </div>
        </div>
    </section>

    <!-- Categories Section -->
    <section class="section" style="background: var(--light-bg);">
        <div class="container">
            <h2 class="section-title">Book Categories</h2>
            <p class="section-subtitle">Explore books by category</p>
            
            <div class="categories-grid">
                <a href="#devotionals" class="category-card">
                    <div class="category-icon">📖</div>
                    <h3>Daily Devotionals</h3>
                    <p>Start your day with God</p>
                </a>
                
                <a href="#bible-studies" class="category-card">
                    <div class="category-icon">✝️</div>
                    <h3>Bible Studies</h3>
                    <p>Deep dive into Scripture</p>
                </a>
                
                <a href="#christian-living" class="category-card">
                    <div class="category-icon">🌟</div>
                    <h3>Christian Living</h3>
                    <p>Practical faith application</p>
                </a>
                
                <a href="#prayer" class="category-card">
                    <div class="category-icon">🙏</div>
                    <h3>Prayer & Worship</h3>
                    <p>Deepen your prayer life</p>
                </a>
                
                <a href="#theology" class="category-card">
                    <div class="category-icon">🎓</div>
                    <h3>Theology</h3>
                    <p>Study Christian doctrine</p>
                </a>
                
                <a href="#family" class="category-card">
                    <div class="category-icon">👨‍👩‍👧‍👦</div>
                    <h3>Family & Marriage</h3>
                    <p>Building Christian homes</p>
                </a>
            </div>
        </div>
    </section>

    <!-- Community Section -->
    <section id="community" class="section">
        <div class="container">
            <h2 class="section-title">Our Community</h2>
            <p class="section-subtitle">Join thousands of believers in our growing community</p>
            
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
                    <div class="stat-label">Ministry Programs</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">24/7</div>
                    <div class="stat-label">Prayer Support</div>
                </div>
            </div>

            <div style="text-align: center;">
                <h3 style="margin-bottom: 2rem; color: var(--primary-color);">Community Features</h3>
                <div class="categories-grid">
                    <div class="category-card">
                        <div class="category-icon">💬</div>
                        <h3>Discussion Forums</h3>
                        <p>Connect with other believers</p>
                    </div>
                    <div class="category-card">
                        <div class="category-icon">📅</div>
                        <h3>Events & Meetings</h3>
                        <p>Join live sessions and events</p>
                    </div>
                    <div class="category-card">
                        <div class="category-icon">🤝</div>
                        <h3>Prayer Groups</h3>
                        <p>Support and be supported</p>
                    </div>
                    <div class="category-card">
                        <div class="category-icon">📚</div>
                        <h3>Study Groups</h3>
                        <p>Learn together in small groups</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Blog Section -->
    <section id="blog" class="section" style="background: var(--light-bg);">
        <div class="container">
            <h2 class="section-title">From Our Blog</h2>
            <p class="section-subtitle">Inspirational articles and Christian insights</p>
            
            <div class="blog-grid">
                <div class="blog-card">
                    <div class="blog-image">Featured Blog Image</div>
                    <div class="blog-content">
                        <h3 class="blog-title">5 Ways to Deepen Your Prayer Life</h3>
                        <p class="blog-excerpt">Discover practical steps to strengthen your communication with God and transform your spiritual journey.</p>
                        <div class="blog-meta">Posted on March 15, 2024 • 5 min read</div>
                        <a href="#" class="btn btn-outline" style="margin-top: 1rem;">Read More</a>
                    </div>
                </div>
                
                <div class="blog-card">
                    <div class="blog-image">Featured Blog Image</div>
                    <div class="blog-content">
                        <h3 class="blog-title">Understanding God's Grace in Difficult Times</h3>
                        <p class="blog-excerpt">Learn how to recognize and embrace God's grace even when facing life's biggest challenges.</p>
                        <div class="blog-meta">Posted on March 12, 2024 • 7 min read</div>
                        <a href="#" class="btn btn-outline" style="margin-top: 1rem;">Read More</a>
                    </div>
                </div>
                
                <div class="blog-card">
                    <div class="blog-image">Featured Blog Image</div>
                    <div class="blog-content">
                        <h3 class="blog-title">Building a Christian Family in Modern Times</h3>
                        <p class="blog-excerpt">Practical advice for maintaining strong Christian values and relationships in today's world.</p>
                        <div class="blog-meta">Posted on March 8, 2024 • 6 min read</div>
                        <a href="#" class="btn btn-outline" style="margin-top: 1rem;">Read More</a>
                    </div>
                </div>
            </div>
            
            <div style="text-align: center; margin-top: 3rem;">
                <a href="#all-blogs" class="btn btn-outline">View All Blog Posts</a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section">
        <div class="container">
            <h2 class="section-title">About NexusReads</h2>
            
            <div class="about-content">
                <div class="about-text">
                    <h3>Our Mission & Vision</h3>
                    <p>NexusReads is dedicated to spreading the Gospel and supporting Christian growth through accessible digital resources. We believe in the transformative power of God's Word and strive to make quality Christian literature available to believers worldwide.</p>
                    
                    <p>Founded in 2020, our ministry has grown to serve thousands of Christians across the globe, providing not just books, but a comprehensive platform for spiritual development and community connection.</p>
                    
                    <ul class="about-features">
                        <li>Quality Christian literature from trusted authors</li>
                        <li>Comprehensive ministry programs for all ages</li>
                        <li>Supportive online community</li>
                        <li>Regular inspirational content and resources</li>
                        <li>Affordable pricing for global accessibility</li>
                    </ul>
                    
                    <a href="#contact" class="btn btn-primary" style="margin-top: 2rem;">Contact Us</a>
                </div>
                
                <div class="about-text">
                    <h3>Our Values</h3>
                    <p><strong>Faith:</strong> Everything we do is rooted in biblical principles and dedicated to glorifying God.</p>
                    <p><strong>Community:</strong> We believe in the power of Christian fellowship and mutual support.</p>
                    <p><strong>Excellence:</strong> We strive for the highest quality in all our resources and services.</p>
                    <p><strong>Accessibility:</strong> Making Christian resources available to everyone, everywhere.</p>
                    <p><strong>Integrity:</strong> Operating with transparency and biblical ethics in all dealings.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h4>NexusReads</h4>
                    <p>Your trusted source for Christian ebooks, ministry resources, and spiritual growth tools. Join our community of believers dedicated to growing in faith together.</p>
                </div>
                
                <div class="footer-section">
                    <h4>Quick Links</h4>
                    <a href="#home">Home</a>
                    <a href="#store">Book Store</a>
                    <a href="#ministry">Ministry</a>
                    <a href="#community">Community</a>
                    <a href="#blog">Blog</a>
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
                <p>&copy; 2024 NexusReads Ministry. All rights reserved. | Building Faith, Transforming Lives</p>
            </div>
        </div>
    </footer>

    <script>
        // Simple smooth scrolling
        document.addEventListener('DOMContentLoaded', function() {
            // Smooth scrolling for navigation links
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

            console.log('NexusReads Ministry Store loaded successfully!');
        });
    </script>
</body>
</html>
