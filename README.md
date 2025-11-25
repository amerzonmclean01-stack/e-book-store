<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prophetic Books | Premium Ebook Store</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --white: #ffffff;
            --prophetic-blue: #1a73e8;
            --crimson-red: #dc143c;
            --light-gray: #f5f5f5;
            --dark-gray: #333333;
            --medium-gray: #666666;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--white);
            color: var(--dark-gray);
            line-height: 1.6;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header Styles */
        header {
            background-color: var(--white);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-top {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        
        .logo {
            display: flex;
            align-items: center;
        }
        
        .logo h1 {
            font-size: 24px;
            font-weight: 700;
            color: var(--prophetic-blue);
        }
        
        .logo span {
            color: var(--crimson-red);
        }
        
        .search-bar {
            display: flex;
            width: 40%;
        }
        
        .search-bar input {
            width: 100%;
            padding: 10px 15px;
            border: 1px solid #ddd;
            border-radius: 4px 0 0 4px;
            font-size: 14px;
        }
        
        .search-bar button {
            background-color: var(--prophetic-blue);
            color: var(--white);
            border: none;
            padding: 0 15px;
            border-radius: 0 4px 4px 0;
            cursor: pointer;
        }
        
        .user-actions {
            display: flex;
            align-items: center;
            gap: 20px;
        }
        
        .user-actions a {
            color: var(--dark-gray);
            text-decoration: none;
            font-size: 14px;
        }
        
        .user-actions i {
            font-size: 18px;
        }
        
        .cart-icon {
            position: relative;
        }
        
        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: var(--crimson-red);
            color: var(--white);
            border-radius: 50%;
            width: 18px;
            height: 18px;
            font-size: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            border-top: 1px solid #eee;
            padding: 15px 0;
        }
        
        nav ul li {
            margin-right: 25px;
        }
        
        nav ul li a {
            text-decoration: none;
            color: var(--dark-gray);
            font-weight: 500;
            transition: color 0.3s;
        }
        
        nav ul li a:hover {
            color: var(--prophetic-blue);
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--prophetic-blue), #0d47a1);
            color: var(--white);
            padding: 60px 0;
            text-align: center;
        }
        
        .hero h2 {
            font-size: 36px;
            margin-bottom: 15px;
        }
        
        .hero p {
            font-size: 18px;
            margin-bottom: 25px;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .cta-button {
            display: inline-block;
            background-color: var(--crimson-red);
            color: var(--white);
            padding: 12px 30px;
            border-radius: 4px;
            text-decoration: none;
            font-weight: 600;
            transition: background-color 0.3s;
        }
        
        .cta-button:hover {
            background-color: #b01030;
        }
        
        /* Featured Books */
        .section-title {
            text-align: center;
            margin: 40px 0 30px;
            font-size: 28px;
            color: var(--dark-gray);
        }
        
        .books-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }
        
        .book-card {
            background-color: var(--white);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .book-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
        }
        
        .book-cover {
            height: 280px;
            background-color: var(--light-gray);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
        }
        
        .book-cover img {
            max-width: 100%;
            max-height: 100%;
            object-fit: cover;
        }
        
        .book-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: var(--crimson-red);
            color: var(--white);
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 12px;
            font-weight: 600;
        }
        
        .book-info {
            padding: 15px;
        }
        
        .book-title {
            font-weight: 600;
            margin-bottom: 5px;
            font-size: 16px;
        }
        
        .book-author {
            color: var(--medium-gray);
            font-size: 14px;
            margin-bottom: 10px;
        }
        
        .book-price {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .price {
            font-weight: 700;
            color: var(--prophetic-blue);
        }
        
        .original-price {
            text-decoration: line-through;
            color: var(--medium-gray);
            font-size: 14px;
            margin-right: 5px;
        }
        
        .add-to-cart {
            background-color: var(--prophetic-blue);
            color: var(--white);
            border: none;
            border-radius: 4px;
            padding: 6px 12px;
            cursor: pointer;
            font-size: 14px;
            transition: background-color 0.3s;
        }
        
        .add-to-cart:hover {
            background-color: #0d62d3;
        }
        
        /* Categories Section */
        .categories {
            background-color: var(--light-gray);
            padding: 40px 0;
        }
        
        .categories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
        }
        
        .category-card {
            background-color: var(--white);
            border-radius: 8px;
            padding: 25px;
            text-align: center;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
        }
        
        .category-card:hover {
            transform: translateY(-5px);
        }
        
        .category-icon {
            font-size: 36px;
            color: var(--prophetic-blue);
            margin-bottom: 15px;
        }
        
        .category-card h3 {
            margin-bottom: 10px;
            font-size: 18px;
        }
        
        .category-card p {
            color: var(--medium-gray);
            font-size: 14px;
        }
        
        /* Resources Section */
        .resources {
            padding: 40px 0;
        }
        
        .resources-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 25px;
        }
        
        .resource-card {
            background-color: var(--white);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        
        .resource-image {
            height: 180px;
            background-color: var(--light-gray);
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .resource-content {
            padding: 20px;
        }
        
        .resource-content h3 {
            margin-bottom: 10px;
            font-size: 18px;
        }
        
        .resource-content p {
            color: var(--medium-gray);
            font-size: 14px;
            margin-bottom: 15px;
        }
        
        .resource-link {
            color: var(--prophetic-blue);
            text-decoration: none;
            font-weight: 600;
            font-size: 14px;
        }
        
        /* Community Section */
        .community {
            background-color: var(--light-gray);
            padding: 40px 0;
        }
        
        .community-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            max-width: 700px;
            margin: 0 auto;
        }
        
        .community-content h2 {
            margin-bottom: 15px;
        }
        
        .community-content p {
            margin-bottom: 25px;
            color: var(--medium-gray);
        }
        
        /* Footer */
        footer {
            background-color: var(--dark-gray);
            color: var(--white);
            padding: 50px 0 20px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }
        
        .footer-column h3 {
            font-size: 18px;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 40px;
            height: 2px;
            background-color: var(--crimson-red);
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 10px;
        }
        
        .footer-column ul li a {
            color: #ccc;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-column ul li a:hover {
            color: var(--white);
        }
        
        .social-icons {
            display: flex;
            gap: 15px;
            margin-top: 15px;
        }
        
        .social-icons a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 36px;
            height: 36px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: var(--white);
            text-decoration: none;
            transition: background-color 0.3s;
        }
        
        .social-icons a:hover {
            background-color: var(--prophetic-blue);
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 14px;
            color: #ccc;
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .header-top {
                flex-direction: column;
                gap: 15px;
            }
            
            .search-bar {
                width: 100%;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .hero h2 {
                font-size: 28px;
            }
            
            .hero p {
                font-size: 16px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-top">
                <div class="logo">
                    <h1>Prophetic<span>Books</span></h1>
                </div>
                <div class="search-bar">
                    <input type="text" placeholder="Search for books, authors, or topics...">
                    <button><i class="fas fa-search"></i></button>
                </div>
                <div class="user-actions">
                    <a href="#"><i class="fas fa-user"></i> Account</a>
                    <a href="#" class="cart-icon">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count">3</span>
                    </a>
                </div>
            </div>
            <nav>
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">Books</a></li>
                    <li><a href="#">Resources</a></li>
                    <li><a href="#">Community</a></li>
                    <li><a href="#">Ministry</a></li>
                    <li><a href="#">Sample Books</a></li>
                    <li><a href="#">About</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h2>Discover Prophetic Wisdom & Spiritual Insight</h2>
            <p>Explore our curated collection of ebooks, resources, and community to deepen your spiritual journey and understanding.</p>
            <a href="#" class="cta-button">Browse Our Collection</a>
        </div>
    </section>

    <!-- Featured Books -->
    <section class="featured-books">
        <div class="container">
            <h2 class="section-title">Featured Books</h2>
            <div class="books-grid">
                <!-- Book 1 -->
                <div class="book-card">
                    <div class="book-cover">
                        <span class="book-badge">Bestseller</span>
                        <img src="https://via.placeholder.com/160x240/1a73e8/ffffff?text=Prophetic+Insights" alt="Prophetic Insights">
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">Prophetic Insights for Today</h3>
                        <p class="book-author">by Dr. Michael Johnson</p>
                        <div class="book-price">
                            <div class="price">
                                <span class="original-price">$24.99</span>
                                $19.99
                            </div>
                            <button class="add-to-cart">Add to Cart</button>
                        </div>
                    </div>
                </div>
                
                <!-- Book 2 -->
                <div class="book-card">
                    <div class="book-cover">
                        <img src="https://via.placeholder.com/160x240/dc143c/ffffff?text=Spiritual+Growth" alt="Spiritual Growth">
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">Path to Spiritual Growth</h3>
                        <p class="book-author">by Sarah Williams</p>
                        <div class="book-price">
                            <div class="price">$14.99</div>
                            <button class="add-to-cart">Add to Cart</button>
                        </div>
                    </div>
                </div>
                
                <!-- Book 3 -->
                <div class="book-card">
                    <div class="book-cover">
                        <span class="book-badge">New</span>
                        <img src="https://via.placeholder.com/160x240/333333/ffffff?text=Divine+Revelation" alt="Divine Revelation">
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">Understanding Divine Revelation</h3>
                        <p class="book-author">by Pastor James Miller</p>
                        <div class="book-price">
                            <div class="price">$22.99</div>
                            <button class="add-to-cart">Add to Cart</button>
                        </div>
                    </div>
                </div>
                
                <!-- Book 4 -->
                <div class="book-card">
                    <div class="book-cover">
                        <img src="https://via.placeholder.com/160x240/1a73e8/ffffff?text=Faith+Journey" alt="Faith Journey">
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">The Faith Journey</h3>
                        <p class="book-author">by Rebecca Thompson</p>
                        <div class="book-price">
                            <div class="price">
                                <span class="original-price">$18.99</span>
                                $12.99
                            </div>
                            <button class="add-to-cart">Add to Cart</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Categories Section -->
    <section class="categories">
        <div class="container">
            <h2 class="section-title">Browse Categories</h2>
            <div class="categories-grid">
                <div class="category-card">
                    <div class="category-icon">
                        <i class="fas fa-book-open"></i>
                    </div>
                    <h3>Prophetic Teachings</h3>
                    <p>Deepen your understanding of prophetic ministry and gifts</p>
                </div>
                
                <div class="category-card">
                    <div class="category-icon">
                        <i class="fas fa-pray"></i>
                    </div>
                    <h3>Spiritual Growth</h3>
                    <p>Resources to help you grow in your faith and relationship with God</p>
                </div>
                
                <div class="category-card">
                    <div class="category-icon">
                        <i class="fas fa-hands-helping"></i>
                    </div>
                    <h3>Ministry Resources</h3>
                    <p>Tools and guides for effective ministry and leadership</p>
                </div>
                
                <div class="category-card">
                    <div class="category-icon">
                        <i class="fas fa-users"></i>
                    </div>
                    <h3>Community</h3>
                    <p>Connect with like-minded believers and share insights</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Resources Section -->
    <section class="resources">
        <div class="container">
            <h2 class="section-title">Free Resources</h2>
            <div class="resources-grid">
                <div class="resource-card">
                    <div class="resource-image">
                        <i class="fas fa-file-pdf" style="font-size: 48px; color: #1a73e8;"></i>
                    </div>
                    <div class="resource-content">
                        <h3>Sample Chapter: Prophetic Foundations</h3>
                        <p>Get a free sample chapter from our bestselling book on prophetic ministry.</p>
                        <a href="#" class="resource-link">Download Now <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>
                
                <div class="resource-card">
                    <div class="resource-image">
                        <i class="fas fa-video" style="font-size: 48px; color: #dc143c;"></i>
                    </div>
                    <div class="resource-content">
                        <h3>Video Teaching: Understanding Dreams</h3>
                        <p>Watch this free video teaching on interpreting dreams from a biblical perspective.</p>
                        <a href="#" class="resource-link">Watch Now <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>
                
                <div class="resource-card">
                    <div class="resource-image">
                        <i class="fas fa-headphones" style="font-size: 48px; color: #333333;"></i>
                    </div>
                    <div class="resource-content">
                        <h3>Podcast: Prophetic Perspectives</h3>
                        <p>Listen to our latest podcast episode discussing current events from a prophetic viewpoint.</p>
                        <a href="#" class="resource-link">Listen Now <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Community Section -->
    <section class="community">
        <div class="container">
            <div class="community-content">
                <h2>Join Our Growing Community</h2>
                <p>Connect with thousands of believers worldwide. Share insights, ask questions, and grow together in your spiritual journey.</p>
                <a href="#" class="cta-button">Join Community</a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Prophetic Books</h3>
                    <p>Your trusted source for spiritual growth resources, prophetic teachings, and community connection.</p>
                    <div class="social-icons">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
                
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#">All Books</a></li>
                        <li><a href="#">Free Resources</a></li>
                        <li><a href="#">Sample Chapters</a></li>
                        <li><a href="#">Ministry Resources</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Customer Service</h3>
                    <ul>
                        <li><a href="#">Contact Us</a></li>
                        <li><a href="#">FAQ</a></li>
                        <li><a href="#">Shipping & Returns</a></li>
                        <li><a href="#">Privacy Policy</a></li>
                        <li><a href="#">Terms of Service</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Newsletter</h3>
                    <p>Subscribe to receive updates on new releases and special offers.</p>
                    <form>
                        <input type="email" placeholder="Your email address" style="width: 100%; padding: 10px; margin: 10px 0; border: none; border-radius: 4px;">
                        <button type="submit" class="cta-button" style="width: 100%;">Subscribe</button>
                    </form>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2023 Prophetic Books. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Simple cart functionality
        document.addEventListener('DOMContentLoaded', function() {
            const addToCartButtons = document.querySelectorAll('.add-to-cart');
            const cartCount = document.querySelector('.cart-count');
            let count = 3; // Starting with 3 items in cart for demo
            
            addToCartButtons.forEach(button => {
                button.addEventListener('click', function() {
                    count++;
                    cartCount.textContent = count;
                    
                    // Add animation effect
                    this.textContent = 'Added!';
                    this.style.backgroundColor = '#28a745';
                    
                    setTimeout(() => {
                        this.textContent = 'Add to Cart';
                        this.style.backgroundColor = '';
                    }, 1500);
                });
            });
            
            // Search functionality
            const searchInput = document.querySelector('.search-bar input');
            const searchButton = document.querySelector('.search-bar button');
            
            searchButton.addEventListener('click', function() {
                if (searchInput.value.trim() !== '') {
                    alert(`Searching for: ${searchInput.value}`);
                    // In a real application, this would redirect to search results
                }
            });
            
            searchInput.addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    if (searchInput.value.trim() !== '') {
                        alert(`Searching for: ${searchInput.value}`);
                        // In a real application, this would redirect to search results
                    }
                }
            });
        });
    </script>
</body>
</html>
