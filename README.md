<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NexusReads - Futuristic Ebook Store</title>
    <style>
        /* === ALL STYLES IN ONE PLACE === */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --secondary-gradient: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            --dark-bg: #0a0a0f;
            --darker-bg: #050508;
            --card-bg: rgba(255, 255, 255, 0.05);
            --text-primary: #ffffff;
            --text-secondary: rgba(255, 255, 255, 0.7);
            --accent: #00d4ff;
            --accent-hover: #00b8e6;
            --border-glow: rgba(0, 212, 255, 0.3);
        }

        body {
            background: var(--dark-bg);
            color: var(--text-primary);
            font-family: 'Inter', 'Segoe UI', sans-serif;
            overflow-x: hidden;
            line-height: 1.6;
        }

        .futuristic-theme {
            background: radial-gradient(ellipse at top, #1a1a2e 0%, var(--dark-bg) 50%);
            min-height: 100vh;
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
        }

        .glass-button {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 12px;
            color: white;
            padding: 12px 24px;
            font-weight: 600;
            transition: all 0.3s ease;
            cursor: pointer;
            font-size: 16px;
            text-decoration: none;
            display: inline-block;
        }

        .glass-button:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(0, 212, 255, 0.3);
        }

        .gradient-text {
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        /* Header Styles */
        .header {
            position: sticky;
            top: 0;
            z-index: 100;
            margin: 20px;
            background: rgba(255, 255, 255, 0.05) !important;
        }

        .header-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 1rem 0;
        }

        .logo {
            font-size: 2rem;
            font-weight: 800;
            text-decoration: none;
            color: var(--text-primary);
        }

        .nav {
            display: flex;
            gap: 2rem;
            align-items: center;
        }

        .nav-link {
            color: var(--text-secondary);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-link:hover {
            color: var(--text-primary);
        }

        /* Hero Section */
        .hero-section {
            position: relative;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            text-align: center;
        }

        .hero-background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(ellipse at center, rgba(102, 126, 234, 0.1) 0%, transparent 70%);
        }

        .floating-shapes .shape {
            position: absolute;
            background: var(--primary-gradient);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
            opacity: 0.3;
        }

        .shape-1 { width: 100px; height: 100px; top: 10%; left: 10%; animation-delay: 0s; }
        .shape-2 { width: 150px; height: 150px; top: 60%; right: 10%; animation-delay: 2s; }
        .shape-3 { width: 80px; height: 80px; bottom: 20%; left: 20%; animation-delay: 4s; }

        .hero-content {
            z-index: 2;
            max-width: 800px;
            padding: 0 20px;
        }

        .hero-title {
            font-size: 4rem;
            font-weight: 800;
            margin-bottom: 1.5rem;
            line-height: 1.1;
        }

        .hero-subtitle {
            font-size: 1.5rem;
            color: var(--text-secondary);
            margin-bottom: 3rem;
            line-height: 1.6;
        }

        .hero-actions {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .glass-button.primary {
            background: var(--primary-gradient);
            border: none;
        }

        /* Categories Section */
        .categories-section {
            padding: 80px 0;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 3rem;
            font-weight: 700;
        }

        .categories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-bottom: 3rem;
        }

        .category-card {
            text-align: center;
            padding: 2rem 1rem;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .category-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.4);
        }

        .category-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        /* Books Section */
        .featured-section {
            padding: 80px 0;
        }

        .books-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
            padding: 2rem 0;
        }

        .book-card {
            border-radius: 20px;
            overflow: hidden;
            transition: all 0.3s ease;
            height: 100%;
            display: flex;
            flex-direction: column;
        }

        .book-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
        }

        .book-image {
            position: relative;
            width: 100%;
            height: 250px;
            overflow: hidden;
            background: var(--primary-gradient);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
        }

        .book-info {
            padding: 1.5rem;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .book-title {
            font-size: 1.25rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--text-primary);
        }

        .book-author {
            color: var(--text-secondary);
            font-size: 0.9rem;
            margin-bottom: 0.5rem;
        }

        .book-price {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--text-primary);
            margin-top: auto;
        }

        /* Footer */
        .footer {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            margin-top: auto;
            padding: 3rem 0;
        }

        .footer-content {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr;
            gap: 3rem;
        }

        .footer-bottom {
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            padding: 2rem 0;
            text-align: center;
            color: var(--text-secondary);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero-title { font-size: 2.5rem; }
            .hero-subtitle { font-size: 1.2rem; }
            .nav { display: none; }
            .categories-grid { grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); }
            .books-grid { grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); }
            .footer-content { grid-template-columns: 1fr; text-align: center; }
            .hero-actions { flex-direction: column; align-items: center; }
        }
    </style>
</head>
<body class="futuristic-theme">
    <!-- Header -->
    <header class="header glass-card">
        <div class="container">
            <div class="header-content">
                <a href="#" class="logo">
                    <span class="gradient-text">Nexus</span>Reads
                </a>
                
                <nav class="nav">
                    <a href="#" class="nav-link">Home</a>
                    <a href="#catalog" class="nav-link">Catalog</a>
                    <a href="#categories" class="nav-link">Categories</a>
                    <a href="#deals" class="nav-link">Deals</a>
                </nav>

                <div class="header-actions">
                    <button class="glass-button">Sign In</button>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero-section">
        <div class="hero-background">
            <div class="floating-shapes">
                <div class="shape shape-1"></div>
                <div class="shape shape-2"></div>
                <div class="shape shape-3"></div>
            </div>
        </div>
        
        <div class="hero-content">
            <h1 class="hero-title">
                Discover Your Next
                <span class="gradient-text">Digital Adventure</span>
            </h1>
            
            <p class="hero-subtitle">
                Explore thousands of ebooks with AI-powered recommendations and immersive reading experiences
            </p>

            <div class="hero-actions">
                <a href="#catalog" class="glass-button primary">
                    Explore Catalog
                </a>
                <button class="glass-button secondary">
                    Learn More
                </button>
            </div>
        </div>
    </section>

    <!-- Categories Section -->
    <section id="categories" class="categories-section">
        <div class="container">
            <h2 class="section-title">
                Explore Categories
            </h2>
            
            <div class="categories-grid">
                <div class="category-card glass-card">
                    <div class="category-icon">🚀</div>
                    <h3>Science Fiction</h3>
                    <p>1.2K books</p>
                </div>
                
                <div class="category-card glass-card">
                    <div class="category-icon">⚔️</div>
                    <h3>Fantasy</h3>
                    <p>890 books</p>
                </div>
                
                <div class="category-card glass-card">
                    <div class="category-icon">🕵️</div>
                    <h3>Mystery</h3>
                    <p>756 books</p>
                </div>
                
                <div class="category-card glass-card">
                    <div class="category-icon">💖</div>
                    <h3>Romance</h3>
                    <p>1.5K books</p>
                </div>
                
                <div class="category-card glass-card">
                    <div class="category-icon">💻</div>
                    <h3>Technology</h3>
                    <p>543 books</p>
                </div>
                
                <div class="category-card glass-card">
                    <div class="category-icon">💼</div>
                    <h3>Business</h3>
                    <p>432 books</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Books -->
    <section id="catalog" class="featured-section">
        <div class="container">
            <h2 class="section-title">
                Featured Books
            </h2>
            
            <div class="books-grid">
                <!-- Book 1 -->
                <div class="book-card glass-card">
                    <div class="book-image">
                        Digital Fortress
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">Digital Fortress</h3>
                        <p class="book-author">by Tech Author</p>
                        <div class="book-price">$12.99</div>
                        <a href="#" class="glass-button" style="margin-top: 1rem; text-align: center;">
                            View Details
                        </a>
                    </div>
                </div>

                <!-- Book 2 -->
                <div class="book-card glass-card">
                    <div class="book-image">
                        Neural Dreams
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">Neural Dreams</h3>
                        <p class="book-author">by AI Writer</p>
                        <div class="book-price">$14.99</div>
                        <a href="#" class="glass-button" style="margin-top: 1rem; text-align: center;">
                            View Details
                        </a>
                    </div>
                </div>

                <!-- Book 3 -->
                <div class="book-card glass-card">
                    <div class="book-image">
                        Quantum Legacy
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">Quantum Legacy</h3>
                        <p class="book-author">by Science Author</p>
                        <div class="book-price">$11.99</div>
                        <a href="#" class="glass-button" style="margin-top: 1rem; text-align: center;">
                            View Details
                        </a>
                    </div>
                </div>

                <!-- Book 4 -->
                <div class="book-card glass-card">
                    <div class="book-image">
                        Virtual Reality
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">Virtual Reality</h3>
                        <p class="book-author">by Future Writer</p>
                        <div class="book-price">$13.99</div>
                        <a href="#" class="glass-button" style="margin-top: 1rem; text-align: center;">
                            View Details
                        </a>
                    </div>
                </div>
            </div>
            
            <div style="text-align: center; margin-top: 3rem;">
                <a href="#catalog" class="glass-button">
                    View All Books
                </a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3 class="logo">
                        <span class="gradient-text">Nexus</span>Reads
                    </h3>
                    <p>Your gateway to the future of digital reading. Discover, explore, and immerse yourself in endless stories.</p>
                </div>
                
                <div class="footer-section">
                    <h4>Explore</h4>
                    <a href="#catalog">All Books</a>
                    <a href="#categories">Categories</a>
                    <a href="#featured">Featured</a>
                    <a href="#new">New Releases</a>
                </div>
                
                <div class="footer-section">
                    <h4>Support</h4>
                    <a href="#help">Help Center</a>
                    <a href="#contact">Contact Us</a>
                    <a href="#faq">FAQ</a>
                </div>
                
                <div class="footer-section">
                    <h4>Legal</h4>
                    <a href="#privacy">Privacy Policy</a>
                    <a href="#terms">Terms of Service</a>
                    <a href="#refunds">Refund Policy</a>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2024 NexusReads. All rights reserved. The future of reading is here.</p>
            </div>
        </div>
    </footer>

    <script>
        // Simple animations and interactions
        document.addEventListener('DOMContentLoaded', function() {
            // Add hover effects to cards
            const cards = document.querySelectorAll('.glass-card');
            cards.forEach(card => {
                card.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-5px)';
                });
                card.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0)';
                });
            });

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

            console.log('🚀 NexusReads Ebook Store loaded successfully!');
        });
    </script>
</body>
</html>
