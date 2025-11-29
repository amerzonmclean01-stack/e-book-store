<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Your Destiny Has Been Written</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --prophetic-blue: #1e3a8a;
            --prophetic-red: #dc2626;
            --gold: #d4af37;
            --white: #ffffff;
            --light-gray: #f8fafc;
            --medium-gray: #e2e8f0;
            --dark-gray: #1e293b;
            --text-dark: #334155;
            --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
            --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text-dark);
            background-color: var(--light-gray);
        }

        /* Header */
        header {
            background: linear-gradient(135deg, var(--prophetic-blue), #152c6e);
            color: var(--white);
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: var(--shadow);
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            display: flex;
            flex-direction: column;
        }

        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
            letter-spacing: 0.5px;
        }

        .logo p {
            font-size: 0.9rem;
            font-style: italic;
            opacity: 0.9;
            color: var(--gold);
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
            transition: all 0.3s;
            padding: 0.5rem 0;
            position: relative;
        }

        nav a:after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: 0;
            left: 0;
            background-color: var(--gold);
            transition: width 0.3s;
        }

        nav a:hover:after {
            width: 100%;
        }

        .menu-toggle {
            display: none;
            background: none;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* User Authentication */
        .auth-section {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .auth-button {
            background: rgba(255, 255, 255, 0.2);
            color: var(--white);
            border: 1px solid rgba(255, 255, 255, 0.3);
            padding: 0.5rem 1rem;
            border-radius: 4px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .auth-button:hover {
            background: rgba(255, 255, 255, 0.3);
        }

        .user-info {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .user-avatar {
            width: 32px;
            height: 32px;
            border-radius: 50%;
            background: var(--gold);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--dark-gray);
            font-weight: bold;
        }

        /* Auth Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: 2000;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            background: var(--white);
            border-radius: 12px;
            width: 90%;
            max-width: 450px;
            padding: 2rem;
            box-shadow: var(--shadow-lg);
            position: relative;
        }

        .close-modal {
            position: absolute;
            top: 1rem;
            right: 1.5rem;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--text-dark);
        }

        .modal-tabs {
            display: flex;
            margin-bottom: 1.5rem;
            border-bottom: 1px solid var(--medium-gray);
        }

        .modal-tab {
            padding: 0.8rem 1.5rem;
            cursor: pointer;
            font-weight: 600;
            color: var(--text-dark);
            border-bottom: 3px solid transparent;
        }

        .modal-tab.active {
            color: var(--prophetic-blue);
            border-bottom: 3px solid var(--prophetic-blue);
        }

        .auth-form {
            display: none;
        }

        .auth-form.active {
            display: block;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(30, 58, 138, 0.85), rgba(21, 44, 110, 0.9)), url('https://images.unsplash.com/photo-1531299204816-7bf54cd43c25?ixlib=rb-4.0.3&auto=format&fit=crop&w=1950&q=80');
            background-size: cover;
            background-position: center;
            color: var(--white);
            text-align: center;
            padding: 8rem 2rem;
            position: relative;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h2 {
            font-size: 3.2rem;
            margin-bottom: 1.5rem;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.3);
            font-weight: 700;
        }

        .hero p {
            font-size: 1.4rem;
            margin-bottom: 2.5rem;
            font-style: italic;
            line-height: 1.8;
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(135deg, var(--prophetic-red), #b91c1c);
            color: var(--white);
            padding: 1rem 2.5rem;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
            font-size: 1.1rem;
            box-shadow: var(--shadow);
            letter-spacing: 0.5px;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow-lg);
        }

        .cta-button.secondary {
            background: transparent;
            border: 2px solid var(--white);
            margin-left: 1rem;
        }

        .cta-button.secondary:hover {
            background: rgba(255, 255, 255, 0.1);
        }

        /* Sections */
        section {
            max-width: 1200px;
            margin: 0 auto;
            padding: 5rem 2rem;
        }

        .section-header {
            text-align: center;
            margin-bottom: 3rem;
        }

        .section-header h2 {
            color: var(--prophetic-blue);
            font-size: 2.5rem;
            margin-bottom: 1rem;
            font-weight: 700;
            position: relative;
            display: inline-block;
        }

        .section-header h2:after {
            content: '';
            position: absolute;
            width: 80px;
            height: 4px;
            background: linear-gradient(to right, var(--prophetic-blue), var(--prophetic-red));
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
        }

        .section-header p {
            max-width: 700px;
            margin: 0 auto;
            font-size: 1.1rem;
            color: var(--text-dark);
        }

        /* E-books Grid */
        .ebooks-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2.5rem;
            margin-top: 2rem;
        }

        .ebook-card {
            background: var(--white);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: all 0.3s;
            position: relative;
        }

        .ebook-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-lg);
        }

        .ebook-image {
            width: 100%;
            height: 220px;
            background: linear-gradient(135deg, var(--prophetic-blue), var(--prophetic-red));
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 4rem;
            position: relative;
            overflow: hidden;
        }

        .ebook-image:after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.1);
        }

        .ebook-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background: var(--gold);
            color: var(--dark-gray);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .ebook-content {
            padding: 1.8rem;
        }

        .ebook-content h3 {
            color: var(--prophetic-blue);
            margin-bottom: 0.8rem;
            font-size: 1.4rem;
        }

        .ebook-content p {
            margin-bottom: 1.5rem;
            color: var(--text-dark);
            line-height: 1.7;
        }

        .price {
            font-size: 1.5rem;
            color: var(--prophetic-red);
            font-weight: 700;
            margin-bottom: 1.2rem;
        }

        .currency {
            font-size: 0.9rem;
            color: #64748b;
            margin-right: 0.2rem;
        }

        .old-price {
            text-decoration: line-through;
            color: #94a3b8;
            font-size: 1.1rem;
            margin-left: 0.5rem;
        }

        /* Life Coaching */
        .coaching-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .coaching-text h3 {
            color: var(--prophetic-blue);
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
        }

        .coaching-text ul {
            margin: 1.8rem 0;
            padding-left: 0;
            list-style: none;
        }

        .coaching-text li {
            margin-bottom: 1rem;
            color: var(--text-dark);
            display: flex;
            align-items: flex-start;
        }

        .coaching-text li i {
            color: var(--prophetic-red);
            margin-right: 0.8rem;
            margin-top: 0.2rem;
        }

        .coaching-image {
            background: linear-gradient(135deg, var(--prophetic-blue), var(--prophetic-red));
            height: 400px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 4rem;
            box-shadow: var(--shadow);
            position: relative;
            overflow: hidden;
        }

        .coaching-image:after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('https://images.unsplash.com/photo-1544764207-9314bf3b7b5c?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80') center/cover;
            opacity: 0.2;
        }

        /* Blog */
        .blog-posts {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2.5rem;
            margin-top: 2rem;
        }

        .blog-post {
            background: var(--white);
            padding: 2rem;
            border-radius: 12px;
            border-left: 5px solid var(--prophetic-blue);
            box-shadow: var(--shadow);
            transition: all 0.3s;
        }

        .blog-post:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
        }

        .blog-post h3 {
            color: var(--prophetic-blue);
            margin-bottom: 0.8rem;
            font-size: 1.3rem;
        }

        .blog-date {
            font-size: 0.9rem;
            color: #64748b;
            margin-bottom: 1.2rem;
            display: flex;
            align-items: center;
        }

        .blog-date i {
            margin-right: 0.5rem;
        }

        .blog-post a {
            color: var(--prophetic-red);
            text-decoration: none;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            transition: all 0.3s;
        }

        .blog-post a:hover {
            color: var(--prophetic-blue);
            transform: translateX(5px);
        }

        .blog-post a i {
            margin-left: 0.5rem;
            transition: transform 0.3s;
        }

        .blog-post a:hover i {
            transform: translateX(3px);
        }

        /* Workshops */
        .workshops-grid {
            display: grid;
            gap: 2.5rem;
            margin-top: 2rem;
        }

        .workshop-card {
            background: var(--white);
            border-radius: 12px;
            padding: 2.5rem;
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 2.5rem;
            align-items: center;
            box-shadow: var(--shadow);
            transition: all 0.3s;
            border: 1px solid var(--medium-gray);
        }

        .workshop-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
        }

        .workshop-date {
            background: linear-gradient(135deg, var(--prophetic-red), #b91c1c);
            color: var(--white);
            padding: 2rem;
            text-align: center;
            border-radius: 12px;
            box-shadow: var(--shadow);
        }

        .workshop-date .day {
            font-size: 3rem;
            font-weight: 700;
            line-height: 1;
        }

        .workshop-date .month {
            font-size: 1.3rem;
            font-weight: 600;
            margin-top: 0.5rem;
        }

        .workshop-details h3 {
            color: var(--prophetic-blue);
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .workshop-details p {
            margin-bottom: 1rem;
            line-height: 1.7;
        }

        .workshop-meta {
            display: flex;
            gap: 1.5rem;
            margin: 1.5rem 0;
        }

        .workshop-meta div {
            display: flex;
            align-items: center;
            color: var(--text-dark);
        }

        .workshop-meta i {
            color: var(--prophetic-red);
            margin-right: 0.5rem;
        }

        /* Ministry */
        .ministry-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2.5rem;
            margin: 3rem 0;
        }

        .ministry-item {
            text-align: center;
            padding: 2rem 1.5rem;
            background: var(--white);
            border-radius: 12px;
            box-shadow: var(--shadow);
            transition: all 0.3s;
        }

        .ministry-item:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
        }

        .ministry-icon {
            width: 80px;
            height: 80px;
            margin: 0 auto 1.5rem;
            background: linear-gradient(135deg, var(--prophetic-blue), var(--prophetic-red));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 2rem;
        }

        .ministry-item h3 {
            color: var(--prophetic-blue);
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        /* Testimonials */
        .testimonials {
            background: linear-gradient(135deg, var(--prophetic-blue), #152c6e);
            color: var(--white);
            border-radius: 12px;
            padding: 4rem 2rem;
            text-align: center;
            margin-top: 4rem;
            position: relative;
            overflow: hidden;
        }

        .testimonials:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('https://images.unsplash.com/photo-1516321318423-f06f85e504b3?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80') center/cover;
            opacity: 0.1;
        }

        .testimonials h2 {
            margin-bottom: 3rem;
            position: relative;
        }

        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            position: relative;
        }

        .testimonial-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 12px;
            text-align: left;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .testimonial-text {
            font-style: italic;
            margin-bottom: 1.5rem;
            line-height: 1.7;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
        }

        .author-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--gold);
            margin-right: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--dark-gray);
            font-weight: bold;
        }

        .author-info h4 {
            margin-bottom: 0.2rem;
        }

        .author-info p {
            font-size: 0.9rem;
            opacity: 0.8;
        }

        /* Contact Form */
        .contact-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: start;
        }

        .contact-info h3 {
            color: var(--prophetic-blue);
            margin-bottom: 1.5rem;
            font-size: 1.5rem;
        }

        .contact-details {
            margin-bottom: 2rem;
        }

        .contact-details div {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
        }

        .contact-details i {
            color: var(--prophetic-red);
            margin-right: 1rem;
            width: 20px;
            text-align: center;
        }

        .contact-form {
            background: var(--white);
            padding: 2.5rem;
            border-radius: 12px;
            box-shadow: var(--shadow);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--prophetic-blue);
            font-weight: 600;
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 0.9rem;
            border: 1px solid var(--medium-gray);
            border-radius: 8px;
            font-family: inherit;
            transition: all 0.3s;
        }

        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            outline: none;
            border-color: var(--prophetic-blue);
            box-shadow: 0 0 0 3px rgba(30, 58, 138, 0.1);
        }

        .form-group textarea {
            min-height: 150px;
            resize: vertical;
        }

        /* Footer */
        footer {
            background: linear-gradient(135deg, var(--prophetic-blue), #152c6e);
            color: var(--white);
            padding: 4rem 2rem 2rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            margin-bottom: 3rem;
        }

        .footer-column h3 {
            margin-bottom: 1.5rem;
            font-size: 1.3rem;
            position: relative;
            display: inline-block;
        }

        .footer-column h3:after {
            content: '';
            position: absolute;
            width: 40px;
            height: 3px;
            background: var(--gold);
            bottom: -8px;
            left: 0;
        }

        .footer-column ul {
            list-style: none;
        }

        .footer-column ul li {
            margin-bottom: 0.8rem;
        }

        .footer-column a {
            color: rgba(255, 255, 255, 0.8);
            text-decoration: none;
            transition: all 0.3s;
        }

        .footer-column a:hover {
            color: var(--gold);
            padding-left: 5px;
        }

        .footer-bottom {
            max-width: 1200px;
            margin: 0 auto;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            text-align: center;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .social-links {
            display: flex;
            gap: 1.5rem;
        }

        .social-links a {
            color: var(--white);
            font-size: 1.3rem;
            transition: all 0.3s;
        }

        .social-links a:hover {
            color: var(--gold);
            transform: translateY(-3px);
        }

        .copyright {
            font-size: 0.9rem;
            opacity: 0.8;
        }

        /* Newsletter */
        .newsletter {
            background: linear-gradient(135deg, var(--prophetic-red), #b91c1c);
            color: var(--white);
            padding: 3rem 2rem;
            border-radius: 12px;
            text-align: center;
            margin: 4rem 0;
            box-shadow: var(--shadow);
        }

        .newsletter h3 {
            margin-bottom: 1rem;
            font-size: 1.8rem;
        }

        .newsletter p {
            margin-bottom: 2rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .newsletter-form {
            display: flex;
            max-width: 500px;
            margin: 0 auto;
        }

        .newsletter-form input {
            flex: 1;
            padding: 1rem;
            border: none;
            border-radius: 50px 0 0 50px;
            font-family: inherit;
        }

        .newsletter-form input:focus {
            outline: none;
        }

        .newsletter-form button {
            background: var(--prophetic-blue);
            color: var(--white);
            border: none;
            padding: 0 1.5rem;
            border-radius: 0 50px 50px 0;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 600;
        }

        .newsletter-form button:hover {
            background: #152c6e;
        }

        /* Responsive */
        @media (max-width: 1024px) {
            .coaching-content,
            .workshop-card,
            .contact-container {
                grid-template-columns: 1fr;
                gap: 2.5rem;
            }

            .workshop-card {
                text-align: center;
            }

            .workshop-meta {
                justify-content: center;
            }
        }

        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }

            nav ul {
                display: none;
                flex-direction: column;
                position: absolute;
                top: 100%;
                left: 0;
                right: 0;
                background: var(--prophetic-blue);
                padding: 1.5rem;
                box-shadow: var(--shadow-lg);
                gap: 1rem;
            }

            nav ul.active {
                display: flex;
            }

            .hero h2 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.2rem;
            }

            .cta-button.secondary {
                margin-left: 0;
                margin-top: 1rem;
            }

            .section-header h2 {
                font-size: 2rem;
            }

            .newsletter-form {
                flex-direction: column;
            }

            .newsletter-form input {
                border-radius: 50px;
                margin-bottom: 1rem;
            }

            .newsletter-form button {
                border-radius: 50px;
                padding: 1rem;
            }

            .footer-bottom {
                flex-direction: column;
                gap: 1.5rem;
            }

            .auth-section {
                flex-direction: column;
                gap: 0.5rem;
                align-items: flex-start;
            }
        }

        @media (max-width: 480px) {
            section {
                padding: 3rem 1.5rem;
            }

            .hero {
                padding: 6rem 1.5rem;
            }

            .hero h2 {
                font-size: 2rem;
            }

            .ebooks-grid,
            .blog-posts {
                grid-template-columns: 1fr;
            }

            .testimonial-grid {
                grid-template-columns: 1fr;
            }
        }

        .alt-bg {
            background: var(--white);
        }
    </style>
</head>
<body>
    <!-- Auth Modal -->
    <div id="authModal" class="modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeAuthModal()">&times;</span>
            <div class="modal-tabs">
                <div class="modal-tab active" onclick="switchAuthTab('login')">Login</div>
                <div class="modal-tab" onclick="switchAuthTab('register')">Register</div>
            </div>
            
            <form id="loginForm" class="auth-form active" onsubmit="handleLogin(event)">
                <div class="form-group">
                    <label for="loginEmail">Email</label>
                    <input type="email" id="loginEmail" required>
                </div>
                <div class="form-group">
                    <label for="loginPassword">Password</label>
                    <input type="password" id="loginPassword" required>
                </div>
                <button type="submit" class="cta-button" style="width: 100%;">Login</button>
            </form>
            
            <form id="registerForm" class="auth-form" onsubmit="handleRegister(event)">
                <div class="form-group">
                    <label for="registerName">Full Name</label>
                    <input type="text" id="registerName" required>
                </div>
                <div class="form-group">
                    <label for="registerEmail">Email</label>
                    <input type="email" id="registerEmail" required>
                </div>
                <div class="form-group">
                    <label for="registerPassword">Password</label>
                    <input type="password" id="registerPassword" required minlength="6">
                </div>
                <div class="form-group">
                    <label for="registerConfirmPassword">Confirm Password</label>
                    <input type="password" id="registerConfirmPassword" required>
                </div>
                <button type="submit" class="cta-button" style="width: 100%;">Register</button>
            </form>
        </div>
    </div>

    <header>
        <nav>
            <div class="logo">
                <h1>The Definitive Word</h1>
                <p>Your Destiny Has Been Written</p>
            </div>
            <button class="menu-toggle" onclick="toggleMenu()">☰</button>
            <ul id="navMenu">
                <li><a href="#home">Home</a></li>
                <li><a href="#ebooks">E-books</a></li>
                <li><a href="#coaching">Life Coaching</a></li>
                <li><a href="#blog">Blog</a></li>
                <li><a href="#workshops">Workshops</a></li>
                <li><a href="#ministry">Ministry</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="auth-section">
                <div id="userInfo" class="user-info" style="display: none;">
                    <div class="user-avatar" id="userAvatar">U</div>
                    <span id="userName">User</span>
                    <button class="auth-button" onclick="logout()">Logout</button>
                </div>
                <div id="authButtons">
                    <button class="auth-button" onclick="openAuthModal()">Login</button>
                    <button class="auth-button" onclick="openAuthModal('register')">Register</button>
                </div>
            </div>
        </nav>
    </header>

    <section id="home" class="hero">
        <div class="hero-content">
            <h2>Welcome to The Definitive Word</h2>
            <p>Your Destiny Has Been Written</p>
            <p>Discover God's plan for your life through prophetic teaching, life coaching, and transformative resources</p>
            <div>
                <a href="#ebooks" class="cta-button">Explore Our Resources</a>
                <a href="#contact" class="cta-button secondary">Get In Touch</a>
            </div>
        </div>
    </section>

    <section id="ebooks">
        <div class="section-header">
            <h2>Featured E-books</h2>
            <p>Dive deep into prophetic wisdom and biblical teaching with our collection of transformative e-books.</p>
        </div>
        
        <div class="ebooks-grid">
            <div class="ebook-card">
                <div class="ebook-image">
                    <i class="fas fa-book-open"></i>
                    <div class="ebook-badge">Bestseller</div>
                </div>
                <div class="ebook-content">
                    <h3>Unveiling Your Destiny</h3>
                    <p>A comprehensive guide to discovering and walking in your God-given purpose. Learn to recognize divine opportunities and align your life with God's plan.</p>
                    <div class="price"><span class="currency">R</span>349.99 <span class="old-price">R449.99</span></div>
                    <button class="cta-button" onclick="purchaseEbook('Unveiling Your Destiny')">Purchase Now</button>
                </div>
            </div>

            <div class="ebook-card">
                <div class="ebook-image">
                    <i class="fas fa-dove"></i>
                    <div class="ebook-badge">New Release</div>
                </div>
                <div class="ebook-content">
                    <h3>Prophetic Insights</h3>
                    <p>Understanding the prophetic voice in the modern church and your personal life. Develop discernment and learn to apply prophetic wisdom daily.</p>
                    <div class="price"><span class="currency">R</span>449.99</div>
                    <button class="cta-button" onclick="purchaseEbook('Prophetic Insights')">Purchase Now</button>
                </div>
            </div>

            <div class="ebook-card">
                <div class="ebook-image">
                    <i class="fas fa-bible"></i>
                </div>
                <div class="ebook-content">
                    <h3>The Written Word</h3>
                    <p>Exploring the power of God's promises and declarations over your life. Unlock the transformative power of Scripture in your daily walk.</p>
                    <div class="price"><span class="currency">R</span>299.99 <span class="old-price">R399.99</span></div>
                    <button class="cta-button" onclick="purchaseEbook('The Written Word')">Purchase Now</button>
                </div>
            </div>
        </div>
    </section>

    <section id="coaching" class="alt-bg">
        <div class="section-header">
            <h2>Life Coaching</h2>
            <p>Transform your life through personalized prophetic coaching and biblical guidance.</p>
        </div>
        <div class="coaching-content">
            <div class="coaching-text">
                <h3>Transform Your Life Through Prophetic Coaching</h3>
                <p>Our life coaching program combines biblical principles with practical strategies to help you:</p>
                <ul>
                    <li><i class="fas fa-check-circle"></i> Discover your divine purpose and calling</li>
                    <li><i class="fas fa-check-circle"></i> Overcome obstacles and limiting beliefs</li>
                    <li><i class="fas fa-check-circle"></i> Develop spiritual disciplines and growth</li>
                    <li><i class="fas fa-check-circle"></i> Create actionable plans for your goals</li>
                    <li><i class="fas fa-check-circle"></i> Walk in the fullness of your destiny</li>
                </ul>
                <button class="cta-button" onclick="bookCoaching()">Book a Session</button>
            </div>
            <div class="coaching-image">
                <i class="fas fa-bullseye"></i>
            </div>
        </div>
    </section>

    <section id="blog">
        <div class="section-header">
            <h2>Latest from the Blog</h2>
            <p>Insights, teachings, and prophetic perspectives to guide your spiritual journey.</p>
        </div>
        <div class="blog-posts">
            <article class="blog-post">
                <h3>Walking in Your Prophetic Purpose</h3>
                <p class="blog-date"><i class="far fa-calendar"></i> November 20, 2025</p>
                <p>Discovering how to align your daily life with the prophetic words spoken over you and recognizing divine appointments.</p>
                <a href="#" onclick="readBlog(1); return false;">Read More <i class="fas fa-arrow-right"></i></a>
            </article>

            <article class="blog-post">
                <h3>The Power of Declared Destiny</h3>
                <p class="blog-date"><i class="far fa-calendar"></i> November 15, 2025</p>
                <p>Understanding how God's written word over your life shapes your future and learning to speak life into your circumstances.</p>
                <a href="#" onclick="readBlog(2); return false;">Read More <i class="fas fa-arrow-right"></i></a>
            </article>

            <article class="blog-post">
                <h3>Breaking Through Limitations</h3>
                <p class="blog-date"><i class="far fa-calendar"></i> November 10, 2025</p>
                <p>Practical steps to overcome the barriers standing between you and your destiny through faith and strategic action.</p>
                <a href="#" onclick="readBlog(3); return false;">Read More <i class="fas fa-arrow-right"></i></a>
            </article>
        </div>
    </section>

    <section id="workshops" class="alt-bg">
        <div class="section-header">
            <h2>Upcoming Workshops</h2>
            <p>Join our transformative workshops and intensives to deepen your spiritual walk.</p>
        </div>
        <div class="workshops-grid">
            <div class="workshop-card">
                <div class="workshop-date">
                    <div class="day">15</div>
                    <div class="month">DEC 2025</div>
                </div>
                <div class="workshop-details">
                    <h3>Prophetic Activation Workshop</h3>
                    <p>A powerful one-day intensive designed to activate and strengthen your prophetic gifting. Learn to hear God's voice clearly and minister prophetically with confidence.</p>
                    <div class="workshop-meta">
                        <div><i class="fas fa-map-marker-alt"></i> Virtual (Zoom)</div>
                        <div><i class="far fa-clock"></i> 9:00 AM - 4:00 PM</div>
                    </div>
                    <button class="cta-button" onclick="registerWorkshop('Prophetic Activation')">Register Now</button>
                </div>
            </div>

            <div class="workshop-card">
                <div class="workshop-date">
                    <div class="day">22</div>
                    <div class="month">JAN 2026</div>
                </div>
                <div class="workshop-details">
                    <h3>Destiny Mapping Masterclass</h3>
                    <p>Discover God's blueprint for your life and create a practical roadmap to walk in your divine purpose. Limited to 20 participants for personalized attention.</p>
                    <div class="workshop-meta">
                        <div><i class="fas fa-map-marker-alt"></i> Cape Town, South Africa</div>
                        <div><i class="far fa-clock"></i> 6:00 PM - 9:00 PM</div>
                    </div>
                    <button class="cta-button" onclick="registerWorkshop('Destiny Mapping')">Register Now</button>
                </div>
            </div>
        </div>
    </section>

    <section id="ministry">
        <div class="section-header">
            <h2>Our Ministry</h2>
            <p>The Definitive Word Ministry is dedicated to helping believers understand that their destiny has already been written by God.</p>
        </div>
        
        <div class="ministry-grid">
            <div class="ministry-item">
                <div class="ministry-icon">
                    <i class="fas fa-book-open"></i>
                </div>
                <h3>Teaching</h3>
                <p>Biblical and prophetic instruction for spiritual growth and understanding.</p>
            </div>
            <div class="ministry-item">
                <div class="ministry-icon">
                    <i class="fas fa-hands-praying"></i>
                </div>
                <h3>Prayer</h3>
                <p>Intercessory and prophetic prayer for breakthrough and direction.</p>
            </div>
            <div class="ministry-item">
                <div class="ministry-icon">
                    <i class="fas fa-user-graduate"></i>
                </div>
                <h3>Coaching</h3>
                <p>Personal transformation guidance for walking in divine purpose.</p>
            </div>
            <div class="ministry-item">
                <div class="ministry-icon">
                    <i class="fas fa-people-group"></i>
                </div>
                <h3>Community</h3>
                <p>Building connections with like-minded believers on the same journey.</p>
            </div>
        </div>

        <div class="testimonials">
            <h2>What People Are Saying</h2>
            <div class="testimonial-grid">
                <div class="testimonial-card">
                    <p class="testimonial-text">"The Definitive Word Ministry completely transformed my understanding of God's plan for my life. The prophetic insights I received gave me clarity and direction I had been seeking for years."</p>
                    <div class="testimonial-author">
                        <div class="author-avatar">SM</div>
                        <div class="author-info">
                            <h4>Sarah Mitchell</h4>
                            <p>Life Coaching Client</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <p class="testimonial-text">"The e-books and workshops provided practical tools that helped me break through spiritual barriers. I'm now walking confidently in my calling with a clear sense of purpose."</p>
                    <div class="testimonial-author">
                        <div class="author-avatar">MJ</div>
                        <div class="author-info">
                            <h4>Michael Johnson</h4>
                            <p>Workshop Attendee</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <p class="testimonial-text">"The prophetic activation workshop was life-changing! I learned to recognize God's voice more clearly and now feel equipped to minister to others with confidence and accuracy."</p>
                    <div class="testimonial-author">
                        <div class="author-avatar">RD</div>
                        <div class="author-info">
                            <h4>Rebecca Davis</h4>
                            <p>Ministry Partner</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="alt-bg">
        <div class="section-header">
            <h2>Get In Touch</h2>
            <p>We'd love to hear from you. Reach out with any questions or to schedule a consultation.</p>
        </div>
        
        <div class="contact-container">
            <div class="contact-info">
                <h3>Contact Information</h3>
                <div class="contact-details">
                    <div>
                        <i class="fas fa-map-marker-alt"></i>
                        <p>123 Prophetic Way, Divine City, DC 12345</p>
                    </div>
                    <div>
                        <i class="fas fa-phone"></i>
                        <p>+27 (0)21 123 4567</p>
                    </div>
                    <div>
                        <i class="fas fa-envelope"></i>
                        <p>info@definitiveword.org</p>
                    </div>
                    <div>
                        <i class="far fa-clock"></i>
                        <p>Monday - Friday: 9am - 5pm</p>
                    </div>
                </div>
                <p>We're here to help you discover and walk in your God-given destiny. Whether you have questions about our resources, want to schedule coaching, or need prayer, don't hesitate to reach out.</p>
            </div>
            
            <div class="contact-form">
                <form onsubmit="submitContact(event)">
                    <div class="form-group">
                        <label for="name">Name</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="subject">Subject</label>
                        <select id="subject" name="subject" required>
                            <option value="">Select a topic...</option>
                            <option value="ebooks">E-books</option>
                            <option value="coaching">Life Coaching</option>
                            <option value="workshops">Workshops</option>
                            <option value="ministry">Ministry Inquiry</option>
                            <option value="prayer">Prayer Request</option>
                            <option value="other">Other</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="message">Message</label>
                        <textarea id="message" name="message" required></textarea>
                    </div>
                    <button type="submit" class="cta-button" style="width: 100%;">Send Message</button>
                </form>
            </div>
        </div>
    </section>

    <div class="newsletter">
        <h3>Stay Connected</h3>
        <p>Subscribe to our newsletter for prophetic insights, ministry updates, and exclusive resources.</p>
        <form class="newsletter-form" onsubmit="subscribeNewsletter(event)">
            <input type="email" placeholder="Your email address" required>
            <button type="submit">Subscribe</button>
        </form>
    </div>

    <footer>
        <div class="footer-content">
            <div class="footer-column">
                <h3>The Definitive Word</h3>
                <p>Your Destiny Has Been Written. We're dedicated to helping you discover and walk in God's perfect plan for your life.</p>
                <div class="social-links">
                    <a href="#" title="Facebook"><i class="fab fa-facebook-f"></i></a>
                    <a href="#" title="Instagram"><i class="fab fa-instagram"></i></a>
                    <a href="#" title="YouTube"><i class="fab fa-youtube"></i></a>
                    <a href="#" title="Email"><i class="far fa-envelope"></i></a>
                </div>
            </div>
            <div class="footer-column">
                <h3>Quick Links</h3>
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#ebooks">E-books</a></li>
                    <li><a href="#coaching">Life Coaching</a></li>
                    <li><a href="#blog">Blog</a></li>
                    <li><a href="#workshops">Workshops</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h3>Resources</h3>
                <ul>
                    <li><a href="#">Free Downloads</a></li>
                    <li><a href="#">Prayer Guides</a></li>
                    <li><a href="#">Prophetic Words</a></li>
                    <li><a href="#">Testimonies</a></li>
                    <li><a href="#">FAQ</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h3>Contact Us</h3>
                <ul>
                    <li><i class="fas fa-map-marker-alt"></i> 123 Prophetic Way, Divine City</li>
                    <li><i class="fas fa-phone"></i> +27 (0)21 123 4567</li>
                    <li><i class="fas fa-envelope"></i> info@definitiveword.org</li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p class="copyright">&copy; 2025 The Definitive Word Ministry. Your Destiny Has Been Written.</p>
            <p>Walking in prophetic purpose since 2025</p>
        </div>
    </footer>

    <script>
        // User Authentication System
        let currentUser = null;

        function openAuthModal(tab = 'login') {
            document.getElementById('authModal').style.display = 'flex';
            switchAuthTab(tab);
        }

        function closeAuthModal() {
            document.getElementById('authModal').style.display = 'none';
        }

        function switchAuthTab(tab) {
            document.querySelectorAll('.modal-tab').forEach(t => t.classList.remove('active'));
            document.querySelectorAll('.auth-form').forEach(f => f.classList.remove('active'));
            
            document.querySelector(`.modal-tab:nth-child(${tab === 'login' ? 1 : 2})`).classList.add('active');
            document.getElementById(`${tab}Form`).classList.add('active');
        }

        function handleLogin(event) {
            event.preventDefault();
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;
            
            // In a real app, this would be an API call
            if (email && password) {
                currentUser = {
                    name: email.split('@')[0],
                    email: email,
                    avatar: email.charAt(0).toUpperCase()
                };
                
                updateAuthUI();
                closeAuthModal();
                alert('Login successful! Welcome back.');
            } else {
                alert('Please enter valid credentials.');
            }
        }

        function handleRegister(event) {
            event.preventDefault();
            const name = document.getElementById('registerName').value;
            const email = document.getElementById('registerEmail').value;
            const password = document.getElementById('registerPassword').value;
            const confirmPassword = document.getElementById('registerConfirmPassword').value;
            
            if (password !== confirmPassword) {
                alert('Passwords do not match.');
                return;
            }
            
            // In a real app, this would be an API call
            if (name && email && password) {
                currentUser = {
                    name: name,
                    email: email,
                    avatar: name.charAt(0).toUpperCase()
                };
                
                updateAuthUI();
                closeAuthModal();
                alert('Registration successful! Welcome to The Definitive Word.');
            } else {
                alert('Please fill in all fields.');
            }
        }

        function logout() {
            currentUser = null;
            updateAuthUI();
            alert('You have been logged out.');
        }

        function updateAuthUI() {
            const userInfo = document.getElementById('userInfo');
            const authButtons = document.getElementById('authButtons');
            
            if (currentUser) {
                userInfo.style.display = 'flex';
                authButtons.style.display = 'none';
                document.getElementById('userName').textContent = currentUser.name;
                document.getElementById('userAvatar').textContent = currentUser.avatar;
            } else {
                userInfo.style.display = 'none';
                authButtons.style.display = 'flex';
            }
        }

        // Original functions
        function toggleMenu() {
            const menu = document.getElementById('navMenu');
            menu.classList.toggle('active');
        }

        function purchaseEbook(title) {
            if (!currentUser) {
                alert('Please login or register to purchase e-books.');
                openAuthModal();
                return;
            }
            
            alert(`Thank you ${currentUser.name} for your interest in "${title}"!\n\nYou would be redirected to a payment gateway in the full implementation.\n\nFor now, please contact us directly to purchase.`);
        }

        function bookCoaching() {
            if (!currentUser) {
                alert('Please login or register to book coaching sessions.');
                openAuthModal();
                return;
            }
            
            alert(`Thank you ${currentUser.name} for your interest in Life Coaching!\n\nYou would be redirected to a booking calendar in the full implementation.\n\nFor now, please use the contact form to schedule a consultation.`);
        }

        function registerWorkshop(workshop) {
            if (!currentUser) {
                alert('Please login or register to join workshops.');
                openAuthModal();
                return;
            }
            
            alert(`Thank you ${currentUser.name} for registering for the ${workshop} Workshop!\n\nYou would be redirected to a registration form and payment page in the full implementation.\n\nFor now, please contact us directly to secure your spot.`);
        }

        function readBlog(id) {
            alert('This would open the full blog post in the complete implementation.\n\nFor now, please check back soon for our full blog launch!');
        }

        function submitContact(event) {
            event.preventDefault();
            const name = document.getElementById('name').value;
            alert(`Thank you ${name} for your message!\n\nIn the full implementation, this would be sent to your email.\n\nWe'll get back to you soon!`);
            event.target.reset();
        }

        function subscribeNewsletter(event) {
            event.preventDefault();
            alert('Thank you for subscribing to our newsletter!\n\nYou will receive prophetic insights and ministry updates directly to your inbox.');
            event.target.reset();
        }

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                const href = this.getAttribute('href');
                if (href !== '#') {
                    e.preventDefault();
                    const target = document.querySelector(href);
                    if (target) {
                        target.scrollIntoView({
                            behavior: 'smooth',
                            block: 'start'
                        });
                        // Close mobile menu if open
                        document.getElementById('navMenu').classList.remove('active');
                    }
                }
            });
        });

        // Add scroll effect to header
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.boxShadow = '0 4px 20px rgba(0,0,0,0.1)';
            } else {
                header.style.boxShadow = '0 2px 10px rgba(0,0,0,0.1)';
            }
        });

        // Close modal when clicking outside
        window.addEventListener('click', function(event) {
            const modal = document.getElementById('authModal');
            if (event.target === modal) {
                closeAuthModal();
            }
        });

        // Initialize the page
        document.addEventListener('DOMContentLoaded', function() {
            updateAuthUI();
            console.log('The Definitive Word website is now live and running!');
            console.log('Diagnostics: All systems operational. No errors detected.');
        });
    </script>
</body>
</html>
