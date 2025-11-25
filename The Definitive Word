<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prophetic Books | Interactive Ebook Store</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --white: #ffffff;
            --prophetic-blue: #1a73e8;
            --crimson-red: #dc143c;
            --light-gray: #f5f5f5;
            --dark-gray: #333333;
            --medium-gray: #666666;
            --success-green: #28a745;
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
            overflow-x: hidden;
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
            transition: border-color 0.3s;
        }
        
        .search-bar input:focus {
            border-color: var(--prophetic-blue);
            outline: none;
        }
        
        .search-bar button {
            background-color: var(--prophetic-blue);
            color: var(--white);
            border: none;
            padding: 0 15px;
            border-radius: 0 4px 4px 0;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .search-bar button:hover {
            background-color: #0d62d3;
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
            transition: color 0.3s;
        }
        
        .user-actions a:hover {
            color: var(--prophetic-blue);
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
            position: relative;
        }
        
        nav ul li a:hover {
            color: var(--prophetic-blue);
        }
        
        nav ul li a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--prophetic-blue);
            transition: width 0.3s;
        }
        
        nav ul li a:hover::after {
            width: 100%;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--prophetic-blue), #0d47a1);
            color: var(--white);
            padding: 60px 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><path d="M0,0 L100,0 L100,100 Z" fill="rgba(255,255,255,0.1)"/></svg>');
            background-size: cover;
        }
        
        .hero-content {
            position: relative;
            z-index: 1;
            animation: fadeInUp 1s ease-out;
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
            transition: all 0.3s;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        
        .cta-button:hover {
            background-color: #b01030;
            transform: translateY(-2px);
            box-shadow: 0 6px 8px rgba(0, 0, 0, 0.15);
        }
        
        /* Featured Books */
        .section-title {
            text-align: center;
            margin: 40px 0 30px;
            font-size: 28px;
            color: var(--dark-gray);
            position: relative;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background-color: var(--prophetic-blue);
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
            transition: all 0.3s;
            position: relative;
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
            overflow: hidden;
        }
        
        .book-cover img {
            max-width: 100%;
            max-height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .book-card:hover .book-cover img {
            transform: scale(1.05);
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
            z-index: 2;
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
            transition: all 0.3s;
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
            transition: all 0.3s;
            cursor: pointer;
        }
        
        .category-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
        }
        
        .category-icon {
            font-size: 36px;
            color: var(--prophetic-blue);
            margin-bottom: 15px;
            transition: transform 0.3s;
        }
        
        .category-card:hover .category-icon {
            transform: scale(1.1);
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
            transition: all 0.3s;
        }
        
        .resource-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
        }
        
        .resource-image {
            height: 180px;
            background-color: var(--light-gray);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: background-color 0.3s;
        }
        
        .resource-card:hover .resource-image {
            background-color: #e9e9e9;
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
            display: inline-flex;
            align-items: center;
            transition: all 0.3s;
        }
        
        .resource-link i {
            margin-left: 5px;
            transition: transform 0.3s;
        }
        
        .resource-link:hover i {
            transform: translateX(3px);
        }
        
        /* Sample Books Section */
        .samples {
            background-color: var(--light-gray);
            padding: 40px 0;
        }
        
        .sample-books {
            display: flex;
            gap: 20px;
            overflow-x: auto;
            padding: 20px 0;
            scrollbar-width: thin;
            scrollbar-color: var(--prophetic-blue) var(--light-gray);
        }
        
        .sample-books::-webkit-scrollbar {
            height: 8px;
        }
        
        .sample-books::-webkit-scrollbar-track {
            background: var(--light-gray);
            border-radius: 4px;
        }
        
        .sample-books::-webkit-scrollbar-thumb {
            background-color: var(--prophetic-blue);
            border-radius: 4px;
        }
        
        .sample-book {
            flex: 0 0 auto;
            width: 200px;
            background-color: var(--white);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: all 0.3s;
        }
        
        .sample-book:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
        }
        
        .sample-cover {
            height: 250px;
            background-color: var(--light-gray);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
        }
        
        .sample-cover img {
            max-width: 100%;
            max-height: 100%;
            object-fit: cover;
        }
        
        .sample-info {
            padding: 15px;
        }
        
        .sample-title {
            font-weight: 600;
            margin-bottom: 5px;
            font-size: 16px;
        }
        
        .sample-author {
            color: var(--medium-gray);
            font-size: 14px;
            margin-bottom: 10px;
        }
        
        .read-sample {
            display: block;
            width: 100%;
            background-color: var(--prophetic-blue);
            color: var(--white);
            border: none;
            border-radius: 4px;
            padding: 8px 0;
            text-align: center;
            text-decoration: none;
            font-size: 14px;
            transition: background-color 0.3s;
        }
        
        .read-sample:hover {
            background-color: #0d62d3;
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
            transition: all 0.3s;
        }
        
        .social-icons a:hover {
            background-color: var(--prophetic-blue);
            transform: translateY(-3px);
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 14px;
            color: #ccc;
        }
        
        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        
        .modal-content {
            background-color: var(--white);
            border-radius: 8px;
            width: 90%;
            max-width: 800px;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
            animation: modalFadeIn 0.3s ease-out;
        }
        
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            border-bottom: 1px solid #eee;
        }
        
        .modal-header h2 {
            color: var(--prophetic-blue);
        }
        
        .close-modal {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--medium-gray);
            transition: color 0.3s;
        }
        
        .close-modal:hover {
            color: var(--crimson-red);
        }
        
        .modal-body {
            padding: 20px;
        }
        
        .sample-content {
            line-height: 1.8;
        }
        
        .sample-content h3 {
            margin: 20px 0 10px;
            color: var(--prophetic-blue);
        }
        
        .sample-content p {
            margin-bottom: 15px;
        }
        
        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes modalFadeIn {
            from {
                opacity: 0;
                transform: scale(0.9);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }
        
        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.5s, transform 0.5s;
        }
        
        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        /* Toast Notification */
        .toast {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: var(--success-green);
            color: var(--white);
            padding: 12px 20px;
            border-radius: 4px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
            z-index: 1001;
            display: flex;
            align-items: center;
            gap: 10px;
            transform: translateY(100px);
            opacity: 0;
            transition: all 0.3s;
        }
        
        .toast.show {
            transform: translateY(0);
            opacity: 1;
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
            
            .books-grid {
                grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
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
            <div class="hero-content">
                <h2>Discover Prophetic Wisdom & Spiritual Insight</h2>
                <p>Explore our curated collection of ebooks, resources, and community to deepen your spiritual journey and understanding.</p>
                <a href="#" class="cta-button">Browse Our Collection</a>
            </div>
        </div>
    </section>

    <!-- Featured Books -->
    <section class="featured-books">
        <div class="container">
            <h2 class="section-title">Featured Books</h2>
            <div class="books-grid">
                <!-- Book 1 -->
                <div class="book-card fade-in">
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
                <div class="book-card fade-in">
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
                <div class="book-card fade-in">
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
                <div class="book-card fade-in">
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

    <!-- Sample Books Section -->
    <section class="samples">
        <div class="container">
            <h2 class="section-title">Read Free Samples</h2>
            <div class="sample-books">
                <!-- Sample 1 -->
                <div class="sample-book">
                    <div class="sample-cover">
                        <img src="https://via.placeholder.com/140x200/1a73e8/ffffff?text=Sample+1" alt="Sample Book 1">
                    </div>
                    <div class="sample-info">
                        <h3 class="sample-title">Prophetic Foundations</h3>
                        <p class="sample-author">by Dr. Michael Johnson</p>
                        <button class="read-sample" data-sample="1">Read Sample</button>
                    </div>
                </div>
                
                <!-- Sample 2 -->
                <div class="sample-book">
                    <div class="sample-cover">
                        <img src="https://via.placeholder.com/140x200/dc143c/ffffff?text=Sample+2" alt="Sample Book 2">
                    </div>
                    <div class="sample-info">
                        <h3 class="sample-title">Prayer & Spiritual Warfare</h3>
                        <p class="sample-author">by Sarah Williams</p>
                        <button class="read-sample" data-sample="2">Read Sample</button>
                    </div>
                </div>
                
                <!-- Sample 3 -->
                <div class="sample-book">
                    <div class="sample-cover">
                        <img src="https://via.placeholder.com/140x200/333333/ffffff?text=Sample+3" alt="Sample Book 3">
                    </div>
                    <div class="sample-info">
                        <h3 class="sample-title">Biblical Dream Interpretation</h3>
                        <p class="sample-author">by Pastor James Miller</p>
                        <button class="read-sample" data-sample="3">Read Sample</button>
                    </div>
                </div>
                
                <!-- Sample 4 -->
                <div class="sample-book">
                    <div class="sample-cover">
                        <img src="https://via.placeholder.com/140x200/1a73e8/ffffff?text=Sample+4" alt="Sample Book 4">
                    </div>
                    <div class="sample-info">
                        <h3 class="sample-title">The Holy Spirit's Guidance</h3>
                        <p class="sample-author">by Rebecca Thompson</p>
                        <button class="read-sample" data-sample="4">Read Sample</button>
                    </div>
                </div>
                
                <!-- Sample 5 -->
                <div class="sample-book">
                    <div class="sample-cover">
                        <img src="https://via.placeholder.com/140x200/dc143c/ffffff?text=Sample+5" alt="Sample Book 5">
                    </div>
                    <div class="sample-info">
                        <h3 class="sample-title">Faith in Difficult Times</h3>
                        <p class="sample-author">by David Chen</p>
                        <button class="read-sample" data-sample="5">Read Sample</button>
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
                <div class="category-card fade-in">
                    <div class="category-icon">
                        <i class="fas fa-book-open"></i>
                    </div>
                    <h3>Prophetic Teachings</h3>
                    <p>Deepen your understanding of prophetic ministry and gifts</p>
                </div>
                
                <div class="category-card fade-in">
                    <div class="category-icon">
                        <i class="fas fa-pray"></i>
                    </div>
                    <h3>Spiritual Growth</h3>
                    <p>Resources to help you grow in your faith and relationship with God</p>
                </div>
                
                <div class="category-card fade-in">
                    <div class="category-icon">
                        <i class="fas fa-hands-helping"></i>
                    </div>
                    <h3>Ministry Resources</h3>
                    <p>Tools and guides for effective ministry and leadership</p>
                </div>
                
                <div class="category-card fade-in">
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
                <div class="resource-card fade-in">
                    <div class="resource-image">
                        <i class="fas fa-file-pdf" style="font-size: 48px; color: #1a73e8;"></i>
                    </div>
                    <div class="resource-content">
                        <h3>Sample Chapter: Prophetic Foundations</h3>
                        <p>Get a free sample chapter from our bestselling book on prophetic ministry.</p>
                        <a href="#" class="resource-link">Download Now <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>
                
                <div class="resource-card fade-in">
                    <div class="resource-image">
                        <i class="fas fa-video" style="font-size: 48px; color: #dc143c;"></i>
                    </div>
                    <div class="resource-content">
                        <h3>Video Teaching: Understanding Dreams</h3>
                        <p>Watch this free video teaching on interpreting dreams from a biblical perspective.</p>
                        <a href="#" class="resource-link">Watch Now <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>
                
                <div class="resource-card fade-in">
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
                    <form id="newsletter-form">
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

    <!-- Sample Book Modal -->
    <div class="modal" id="sample-modal">
        <div class="modal-content">
            <div class="modal-header">
                <h2 id="sample-title">Sample Book Title</h2>
                <button class="close-modal">&times;</button>
            </div>
            <div class="modal-body">
                <div class="sample-content" id="sample-content">
                    <!-- Sample content will be inserted here -->
                </div>
            </div>
        </div>
    </div>

    <!-- Toast Notification -->
    <div class="toast" id="toast">
        <i class="fas fa-check-circle"></i>
        <span id="toast-message">Item added to cart!</span>
    </div>

    <script>
        // Sample book content
        const sampleContents = {
            1: {
                title: "Prophetic Foundations - Sample",
                content: `
                    <h3>Chapter 1: Understanding Prophetic Ministry</h3>
                    <p>Prophetic ministry is a gift from God to His church, designed to edify, exhort, and comfort believers. Throughout Scripture, we see God speaking to His people through prophets, and this pattern continues today through the gift of prophecy.</p>
                    <p>The purpose of prophetic ministry is not to draw attention to the prophet but to point people to Jesus Christ. A true prophetic word will always align with Scripture and bring glory to God.</p>
                    <p>In this chapter, we will explore the biblical foundations of prophetic ministry, examining both Old Testament prophets and New Testament prophetic gifts. We'll discover how God speaks today and how we can rightly judge prophetic words.</p>
                    <h3>Chapter 2: The Role of the Prophet</h3>
                    <p>Prophets play a unique role in the body of Christ. They are not fortune-tellers or mystics, but rather servants of God who communicate His heart to His people.</p>
                    <p>A prophet's primary function is to speak forth God's word with accuracy and authority. This may involve forthtelling (proclaiming God's truth) or foretelling (revealing future events).</p>
                    <p>In the New Testament, prophets work alongside other ministry gifts to build up the church. They provide direction, correction, and encouragement to the body of Christ.</p>
                    <p>This sample chapter continues for several more pages, exploring the characteristics of true prophets, the testing of prophetic words, and practical steps for developing prophetic gifting.</p>
                `
            },
            2: {
                title: "Prayer & Spiritual Warfare - Sample",
                content: `
                    <h3>Introduction: The Battle for Your Soul</h3>
                    <p>Every Christian is engaged in spiritual warfare whether they realize it or not. The enemy seeks to steal, kill, and destroy, but Jesus came that we might have life abundantly.</p>
                    <p>Prayer is our primary weapon in this spiritual battle. Through prayer, we access God's power and authority to overcome the schemes of the devil.</p>
                    <p>In this book, we will explore the dynamics of spiritual warfare and how to pray effectively against spiritual forces. We'll learn to put on the full armor of God and stand firm against the enemy's attacks.</p>
                    <h3>Chapter 1: Understanding Our Authority</h3>
                    <p>As believers in Jesus Christ, we have been given authority over all the power of the enemy. This authority is not based on our own strength but on the finished work of Christ on the cross.</p>
                    <p>When Jesus rose from the dead, He declared, "All authority in heaven and on earth has been given to me." Then He commissioned His disciples to go in that authority.</p>
                    <p>We exercise this authority through prayer, commanding sickness to leave, demons to flee, and circumstances to align with God's will. This is not positive thinking or mind over matter—it is spiritual reality.</p>
                    <p>This sample continues with practical examples of exercising spiritual authority, common misconceptions about spiritual warfare, and how to pray when you don't see immediate results.</p>
                `
            },
            3: {
                title: "Biblical Dream Interpretation - Sample",
                content: `
                    <h3>Introduction: God Still Speaks in Dreams</h3>
                    <p>Throughout Scripture, we see God speaking to people through dreams. From Joseph in the Old Testament to Joseph the husband of Mary in the New Testament, dreams have been a significant means of divine communication.</p>
                    <p>In our modern, rationalistic age, many Christians have neglected dreams as a way God speaks. But the Bible tells us that in the last days, God will pour out His Spirit, and young men will see visions and old men will dream dreams.</p>
                    <p>This book will help you understand how God speaks through dreams today and provide practical tools for interpreting them biblically.</p>
                    <h3>Chapter 1: Different Types of Dreams</h3>
                    <p>Not every dream is from God. Some dreams are simply the processing of daily events, while others may be influenced by what we eat or our emotional state. But some dreams are genuinely from God.</p>
                    <p>In this chapter, we'll explore different types of dreams:</p>
                    <ul>
                        <li><strong>Message Dreams:</strong> Dreams that contain a clear message from God</li>
                        <li><strong>Symbolic Dreams:</strong> Dreams that use symbols to convey meaning</li>
                        <li><strong>Warning Dreams:</strong> Dreams that alert us to danger or wrong direction</li>
                        <li><strong>Encouragement Dreams:</strong> Dreams that build us up and confirm God's love</li>
                    </ul>
                    <p>We'll also discuss how to discern which dreams are from God and which are not, using biblical principles and the witness of the Holy Spirit.</p>
                `
            },
            4: {
                title: "The Holy Spirit's Guidance - Sample",
                content: `
                    <h3>Introduction: Led by the Spirit</h3>
                    <p>Jesus promised that the Holy Spirit would guide us into all truth. As Christians, we have the incredible privilege of being led by the Spirit of God in our daily lives.</p>
                    <p>But how does this guidance work? How can we distinguish the Holy Spirit's voice from our own thoughts or other influences?</p>
                    <p>In this book, we'll explore the many ways the Holy Spirit guides believers, from the inner witness to prophetic words, from Scripture to circumstances. We'll learn to recognize His voice and follow His leading with confidence.</p>
                    <h3>Chapter 1: The Inner Witness</h3>
                    <p>One of the primary ways the Holy Spirit guides us is through what many call the "inner witness"—a deep, intuitive sense of peace or unrest about a decision or direction.</p>
                    <p>This inner witness is described in Romans 8:16: "The Spirit himself testifies with our spirit that we are God's children." The same Spirit who confirms our identity in Christ also guides our steps.</p>
                    <p>The inner witness is not primarily an emotional feeling, though it may affect our emotions. It is a spiritual certainty that comes from the Holy Spirit bearing witness with our human spirit.</p>
                    <p>In this chapter, we'll explore how to cultivate sensitivity to the inner witness, how to test it against Scripture, and how to respond when we sense the Spirit's guidance.</p>
                `
            },
            5: {
                title: "Faith in Difficult Times - Sample",
                content: `
                    <h3>Introduction: When Faith Is Tested</h3>
                    <p>Every believer will face seasons of difficulty that test their faith. Whether it's illness, financial struggle, relationship problems, or other challenges, these trials can either weaken our faith or strengthen it.</p>
                    <p>The Bible doesn't promise that Christians will be exempt from trouble. In fact, Jesus told His disciples, "In this world you will have trouble. But take heart! I have overcome the world."</p>
                    <p>This book is about how to maintain strong faith when circumstances seem to contradict God's promises. It's about standing firm when everything around you is shaking.</p>
                    <h3>Chapter 1: The Nature of Faith</h3>
                    <p>Faith is not the absence of doubt but the choice to believe God despite our doubts. It's not a feeling but a decision to trust in God's character and promises.</p>
                    <p>The writer of Hebrews defines faith as "confidence in what we hope for and assurance about what we do not see." This kind of faith is able to sustain us when we can't see how God is working.</p>
                    <p>In difficult times, our faith is refined like gold in the fire. The impurities are burned away, and what remains is pure, genuine faith that brings glory to God.</p>
                    <p>This chapter explores biblical examples of faith under pressure, from Abraham offering Isaac to Shadrach, Meshach, and Abednego in the fiery furnace. We'll discover principles for strengthening our faith when it's tested.</p>
                `
            }
        };

        // DOM Content Loaded
        document.addEventListener('DOMContentLoaded', function() {
            // Initialize animations
            initAnimations();
            
            // Cart functionality
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
                    
                    // Show toast notification
                    showToast('Book added to cart!');
                    
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
                performSearch();
            });
            
            searchInput.addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    performSearch();
                }
            });
            
            // Sample book functionality
            const readSampleButtons = document.querySelectorAll('.read-sample');
            const sampleModal = document.getElementById('sample-modal');
            const closeModal = document.querySelector('.close-modal');
            const sampleTitle = document.getElementById('sample-title');
            const sampleContent = document.getElementById('sample-content');
            
            readSampleButtons.forEach(button => {
                button.addEventListener('click', function() {
                    const sampleId = this.getAttribute('data-sample');
                    openSampleModal(sampleId);
                });
            });
            
            closeModal.addEventListener('click', function() {
                closeSampleModal();
            });
            
            // Close modal when clicking outside
            window.addEventListener('click', function(e) {
                if (e.target === sampleModal) {
                    closeSampleModal();
                }
            });
            
            // Newsletter form
            const newsletterForm = document.getElementById('newsletter-form');
            newsletterForm.addEventListener('submit', function(e) {
                e.preventDefault();
                const email = this.querySelector('input[type="email"]').value;
                if (email) {
                    showToast('Thank you for subscribing!');
                    this.reset();
                }
            });
            
            // Category card interactions
            const categoryCards = document.querySelectorAll('.category-card');
            categoryCards.forEach(card => {
                card.addEventListener('click', function() {
                    const category = this.querySelector('h3').textContent;
                    showToast(`Browsing ${category} books`);
                });
            });
            
            // Function to perform search
            function performSearch() {
                if (searchInput.value.trim() !== '') {
                    showToast(`Searching for: ${searchInput.value}`);
                    // In a real application, this would redirect to search results
                }
            }
            
            // Function to open sample modal
            function openSampleModal(sampleId) {
                if (sampleContents[sampleId]) {
                    sampleTitle.textContent = sampleContents[sampleId].title;
                    sampleContent.innerHTML = sampleContents[sampleId].content;
                    sampleModal.style.display = 'flex';
                    document.body.style.overflow = 'hidden';
                }
            }
            
            // Function to close sample modal
            function closeSampleModal() {
                sampleModal.style.display = 'none';
                document.body.style.overflow = 'auto';
            }
            
            // Function to show toast notification
            function showToast(message) {
                const toast = document.getElementById('toast');
                const toastMessage = document.getElementById('toast-message');
                
                toastMessage.textContent = message;
                toast.classList.add('show');
                
                setTimeout(() => {
                    toast.classList.remove('show');
                }, 3000);
            }
            
            // Function to initialize animations
            function initAnimations() {
                // Observe elements for scroll animations
                const fadeElements = document.querySelectorAll('.fade-in');
                
                const observer = new IntersectionObserver((entries) => {
                    entries.forEach(entry => {
                        if (entry.isIntersecting) {
                            entry.target.classList.add('visible');
                        }
                    });
                }, { threshold: 0.1 });
                
                fadeElements.forEach(element => {
                    observer.observe(element);
                });
            }
        });
    </script>
</body>
</html>
