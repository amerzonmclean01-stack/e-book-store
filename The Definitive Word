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
            --success: #10b981;
            --white: #ffffff;
            --light-gray: #f8fafc;
            --medium-gray: #e2e8f0;
            --dark-gray: #1e293b;
            --text-dark: #334155;
            --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
            --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
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
            transition: var(--transition);
        }

        .header-scrolled {
            padding: 0.5rem 0;
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
            cursor: pointer;
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
            transition: var(--transition);
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
            transition: var(--transition);
        }

        .menu-toggle:hover {
            color: var(--gold);
        }

        /* User Authentication & Cart */
        .header-right {
            display: flex;
            align-items: center;
            gap: 1.5rem;
        }

        .cart-icon {
            position: relative;
            cursor: pointer;
            color: var(--white);
            font-size: 1.3rem;
            transition: var(--transition);
        }

        .cart-icon:hover {
            color: var(--gold);
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: var(--prophetic-red);
            color: white;
            font-size: 0.7rem;
            padding: 2px 6px;
            border-radius: 50%;
            min-width: 18px;
            text-align: center;
        }

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
            transition: var(--transition);
            font-weight: 500;
        }

        .auth-button:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-2px);
        }

        .user-info {
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }

        .user-avatar {
            width: 36px;
            height: 36px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--gold), #b8860b);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--dark-gray);
            font-weight: bold;
            cursor: pointer;
            transition: var(--transition);
            border: 2px solid transparent;
        }

        .user-avatar:hover {
            border-color: var(--white);
            transform: scale(1.05);
        }

        /* Dashboard Modal */
        .dashboard-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 3000;
            backdrop-filter: blur(4px);
        }

        .dashboard-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: var(--white);
            border-radius: 16px;
            width: 90%;
            max-width: 500px;
            max-height: 80vh;
            overflow-y: auto;
            box-shadow: var(--shadow-lg);
            animation: modalSlideIn 0.3s ease-out;
        }

        @keyframes modalSlideIn {
            from {
                opacity: 0;
                transform: translate(-50%, -60%);
            }
            to {
                opacity: 1;
                transform: translate(-50%, -50%);
            }
        }

        .dashboard-header {
            background: linear-gradient(135deg, var(--prophetic-blue), #152c6e);
            color: var(--white);
            padding: 1.5rem;
            border-radius: 16px 16px 0 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .dashboard-header h3 {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .close-dashboard {
            background: none;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
            transition: var(--transition);
        }

        .close-dashboard:hover {
            color: var(--gold);
        }

        .dashboard-body {
            padding: 1.5rem;
        }

        .dashboard-section {
            margin-bottom: 1.5rem;
            padding: 1rem;
            background: var(--light-gray);
            border-radius: 8px;
        }

        .dashboard-section h4 {
            color: var(--prophetic-blue);
            margin-bottom: 0.5rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .purchases-list {
            list-style: none;
        }

        .purchases-list li {
            padding: 0.5rem 0;
            border-bottom: 1px solid var(--medium-gray);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .purchases-list li:last-child {
            border-bottom: none;
        }

        .download-btn {
            background: var(--prophetic-blue);
            color: white;
            border: none;
            padding: 0.25rem 0.75rem;
            border-radius: 4px;
            cursor: pointer;
            transition: var(--transition);
            font-size: 0.8rem;
        }

        .download-btn:hover {
            background: var(--prophetic-red);
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
            backdrop-filter: blur(4px);
        }

        .modal-content {
            background: var(--white);
            border-radius: 16px;
            width: 90%;
            max-width: 450px;
            padding: 2rem;
            box-shadow: var(--shadow-lg);
            position: relative;
            animation: modalSlideIn 0.3s ease-out;
        }

        .close-modal {
            position: absolute;
            top: 1rem;
            right: 1.5rem;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--text-dark);
            transition: var(--transition);
        }

        .close-modal:hover {
            color: var(--prophetic-red);
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
            transition: var(--transition);
        }

        .modal-tab.active {
            color: var(--prophetic-blue);
            border-bottom: 3px solid var(--prophetic-blue);
        }

        .modal-tab:hover {
            color: var(--prophetic-red);
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
            overflow: hidden;
        }

        .hero:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url("data:image/svg+xml,%3Csvg width='100' height='100' viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M11 18c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm48 25c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm-43-7c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm63 31c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM34 90c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm56-76c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM12 86c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm28-65c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm23-11c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-6 60c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm29 22c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zM32 63c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm57-13c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-9-21c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM60 91c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM35 41c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM12 60c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2z' fill='%23ffffff' fill-opacity='0.05' fill-rule='evenodd'/%3E%3C/svg%3E");
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }

        .hero h2 {
            font-size: 3.2rem;
            margin-bottom: 1.5rem;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.3);
            font-weight: 700;
            animation: fadeInUp 1s ease-out;
        }

        .hero p {
            font-size: 1.4rem;
            margin-bottom: 2.5rem;
            font-style: italic;
            line-height: 1.8;
            animation: fadeInUp 1s ease-out 0.2s both;
        }

        .hero-buttons {
            animation: fadeInUp 1s ease-out 0.4s both;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(135deg, var(--prophetic-red), #b91c1c);
            color: var(--white);
            padding: 1rem 2.5rem;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            font-size: 1.1rem;
            box-shadow: var(--shadow);
            letter-spacing: 0.5px;
            position: relative;
            overflow: hidden;
        }

        .cta-button:after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,255,255,0.1), transparent);
            transform: translateX(-100%);
            transition: transform 0.6s;
        }

        .cta-button:hover:after {
            transform: translateX(100%);
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

        .cta-button.small {
            padding: 0.5rem 1.5rem;
            font-size: 0.9rem;
        }

        .cta-button.outline {
            background: transparent;
            border: 2px solid var(--prophetic-blue);
            color: var(--prophetic-blue);
        }

        .cta-button.outline:hover {
            background: var(--prophetic-blue);
            color: white;
        }

        /* Sections */
        section {
            max-width: 1200px;
            margin: 0 auto;
            padding: 5rem 2rem;
            scroll-margin-top: 80px;
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
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2.5rem;
            margin-top: 2rem;
        }

        .ebook-card {
            background: var(--white);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
            display: flex;
            flex-direction: column;
            height: 100%;
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
            z-index: 2;
        }

        .ebook-content {
            padding: 1.8rem;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .ebook-content h3 {
            color: var(--prophetic-blue);
            margin-bottom: 0.8rem;
            font-size: 1.4rem;
            min-height: 3.5rem;
        }

        .ebook-content p {
            margin-bottom: 1.5rem;
            color: var(--text-dark);
            line-height: 1.7;
            flex-grow: 1;
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

        .ebook-actions {
            display: flex;
            gap: 0.5rem;
            margin-top: auto;
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
            flex-shrink: 0;
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
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 2.5rem;
            margin-top: 2rem;
        }

        .blog-post {
            background: var(--white);
            padding: 2rem;
            border-radius: 12px;
            border-left: 5px solid var(--prophetic-blue);
            box-shadow: var(--shadow);
            transition: var(--transition);
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
            transition: var(--transition);
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
            transition: var(--transition);
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
            flex-wrap: wrap;
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
            transition: var(--transition);
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
            transition: var(--transition);
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

        /* Cart Modal */
        .cart-modal {
            display: none;
            position: fixed;
            top: 0;
            right: 0;
            width: 100%;
            max-width: 400px;
            height: 100%;
            background: var(--white);
            box-shadow: var(--shadow-lg);
            z-index: 2500;
            overflow-y: auto;
            animation: slideIn 0.3s ease-out;
        }

        @keyframes slideIn {
            from { transform: translateX(100%); }
            to { transform: translateX(0); }
        }

        .cart-header {
            background: linear-gradient(135deg, var(--prophetic-blue), #152c6e);
            color: var(--white);
            padding: 1.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .cart-items {
            padding: 1.5rem;
        }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
            border-bottom: 1px solid var(--medium-gray);
        }

        .cart-item:last-child {
            border-bottom: none;
        }

        .cart-item-info h4 {
            color: var(--prophetic-blue);
            margin-bottom: 0.5rem;
        }

        .cart-item-price {
            color: var(--prophetic-red);
            font-weight: 600;
        }

        .cart-total {
            padding: 1.5rem;
            border-top: 2px solid var(--medium-gray);
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--prophetic-blue);
        }

        .cart-actions {
            padding: 1.5rem;
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .empty-cart {
            text-align: center;
            padding: 3rem 1.5rem;
            color: var(--text-dark);
        }

        /* Toast Notifications */
        .toast {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            padding: 1rem 1.5rem;
            background: var(--success);
            color: white;
            border-radius: 8px;
            box-shadow: var(--shadow-lg);
            z-index: 4000;
            display: flex;
            align-items: center;
            gap: 0.75rem;
            transform: translateY(100px);
            opacity: 0;
            transition: var(--transition);
        }

        .toast.show {
            transform: translateY(0);
            opacity: 1;
        }

        .toast.error {
            background: var(--prophetic-red);
        }

        .toast.warning {
            background: var(--gold);
            color: var(--dark-gray);
        }

        /* Loading Overlay */
        .loading-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: 5000;
            align-items: center;
            justify-content: center;
            backdrop-filter: blur(4px);
        }

        .spinner {
            width: 50px;
            height: 50px;
            border: 5px solid rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            border-top-color: var(--gold);
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
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
            transition: var(--transition);
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
            transition: var(--transition);
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
            transition: var(--transition);
            font-weight: 600;
        }

        .newsletter-form button:hover {
            background: #152c6e;
        }

        /* Progress Bar */
        .progress-bar {
            position: fixed;
            top: 0;
            left: 0;
            width: 0;
            height: 3px;
            background: linear-gradient(to right, var(--prophetic-blue), var(--prophetic-red));
            z-index: 9999;
            transition: width 0.3s ease;
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
                z-index: 1000;
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

            .header-right {
                gap: 1rem;
            }

            .cart-modal {
                max-width: 100%;
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

            .workshop-card {
                padding: 1.5rem;
                grid-template-columns: 1fr;
                gap: 1.5rem;
            }

            .ebook-actions {
                flex-direction: column;
            }

            .ebook-actions button {
                width: 100%;
            }
        }

        .alt-bg {
            background: var(--white);
        }

        /* Animation Classes */
        .fade-in {
            animation: fadeIn 0.6s ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
    </style>
</head>
<body>
    <!-- Loading Overlay -->
    <div id="loadingOverlay" class="loading-overlay">
        <div class="spinner"></div>
    </div>

    <!-- Toast Notification -->
    <div id="toast" class="toast">
        <i class="fas fa-check-circle"></i>
        <span id="toastMessage">Action completed successfully!</span>
    </div>

    <!-- Progress Bar -->
    <div class="progress-bar"></div>

    <!-- Cart Modal -->
    <div id="cartModal" class="cart-modal">
        <div class="cart-header">
            <h3><i class="fas fa-shopping-cart"></i> Your Cart</h3>
            <button class="close-modal" onclick="closeCart()">&times;</button>
        </div>
        <div id="cartItems" class="cart-items">
            <!-- Cart items will be populated here -->
        </div>
        <div id="cartEmpty" class="empty-cart" style="display: none;">
            <i class="fas fa-shopping-cart fa-3x" style="margin-bottom: 1rem; opacity: 0.3;"></i>
            <p>Your cart is empty</p>
            <button class="cta-button small" onclick="closeCart()">Continue Shopping</button>
        </div>
        <div id="cartTotal" class="cart-total" style="display: none;">
            <span>Total:</span>
            <span id="cartTotalAmount">R0.00</span>
        </div>
        <div id="cartActions" class="cart-actions" style="display: none;">
            <button class="cta-button" onclick="checkout()">Proceed to Checkout</button>
            <button class="cta-button secondary" onclick="clearCart()">Clear Cart</button>
        </div>
    </div>

    <!-- Dashboard Modal -->
    <div id="dashboardModal" class="dashboard-modal">
        <div class="dashboard-content">
            <div class="dashboard-header">
                <h3><i class="fas fa-user-circle"></i> User Dashboard</h3>
                <button class="close-dashboard" onclick="closeDashboard()">&times;</button>
            </div>
            <div class="dashboard-body">
                <div class="dashboard-section">
                    <h4><i class="fas fa-user"></i> Profile Information</h4>
                    <p><strong>Name:</strong> <span id="dashboardName">-</span></p>
                    <p><strong>Email:</strong> <span id="dashboardEmail">-</span></p>
                    <p><strong>Member Since:</strong> <span id="dashboardJoinDate">-</span></p>
                </div>
                <div class="dashboard-section">
                    <h4><i class="fas fa-book"></i> My Purchases</h4>
                    <ul id="purchasesList" class="purchases-list">
                        <!-- Purchases will be populated here -->
                    </ul>
                </div>
                <div class="dashboard-section">
                    <h4><i class="fas fa-calendar-alt"></i> Upcoming Sessions</h4>
                    <ul id="sessionsList" class="purchases-list">
                        <!-- Sessions will be populated here -->
                    </ul>
                </div>
                <div class="dashboard-section">
                    <h4><i class="fas fa-cog"></i> Account Settings</h4>
                    <button class="cta-button small outline" onclick="changePassword()">Change Password</button>
                    <button class="cta-button small" onclick="logout()" style="margin-top: 0.5rem;">Logout</button>
                </div>
            </div>
        </div>
    </div>

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
                <p style="text-align: center; margin-top: 1rem; font-size: 0.9rem;">
                    Demo: Use any email/password to login
                </p>
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
                    <label for="registerPassword">Password (min. 6 characters)</label>
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
            <div class="logo" onclick="scrollToTop()">
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
            <div class="header-right">
                <div class="cart-icon" onclick="openCart()">
                    <i class="fas fa-shopping-cart"></i>
                    <span id="cartCount" class="cart-count">0</span>
                </div>
                <div class="auth-section">
                    <div id="userInfo" class="user-info" style="display: none;">
                        <div class="user-avatar" id="userAvatar" onclick="openDashboard()">U</div>
                        <span id="userName">User</span>
                        <button class="auth-button" onclick="logout()">Logout</button>
                    </div>
                    <div id="authButtons">
                        <button class="auth-button" onclick="openAuthModal()">Login</button>
                        <button class="auth-button" onclick="openAuthModal('register')">Register</button>
                    </div>
                </div>
            </div>
        </nav>
    </header>

    <section id="home" class="hero">
        <div class="hero-content">
            <h2>Welcome to The Definitive Word</h2>
            <p>Your Destiny Has Been Written</p>
            <p>Discover God's plan for your life through prophetic teaching, life coaching, and transformative resources</p>
            <div class="hero-buttons">
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
                    <div class="ebook-actions">
                        <button class="cta-button small" onclick="addToCart(1, 'Unveiling Your Destiny', 349.99)">Add to Cart</button>
                        <button class="cta-button small outline" onclick="showPreview(1)">Preview</button>
                    </div>
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
                    <div class="ebook-actions">
                        <button class="cta-button small" onclick="addToCart(2, 'Prophetic Insights', 449.99)">Add to Cart</button>
                        <button class="cta-button small outline" onclick="showPreview(2)">Preview</button>
                    </div>
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
                    <div class="ebook-actions">
                        <button class="cta-button small" onclick="addToCart(3, 'The Written Word', 299.99)">Add to Cart</button>
                        <button class="cta-button small outline" onclick="showPreview(3)">Preview</button>
                    </div>
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
                        <div><i class="fas fa-tag"></i> R599.99</div>
                    </div>
                    <div class="ebook-actions">
                        <button class="cta-button small" onclick="addToCart(4, 'Prophetic Activation Workshop', 599.99)">Register Now</button>
                        <button class="cta-button small outline" onclick="showWorkshopDetails(4)">Details</button>
                    </div>
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
                        <div><i class="fas fa-tag"></i> R799.99</div>
                    </div>
                    <div class="ebook-actions">
                        <button class="cta-button small" onclick="addToCart(5, 'Destiny Mapping Masterclass', 799.99)">Register Now</button>
                        <button class="cta-button small outline" onclick="showWorkshopDetails(5)">Details</button>
                    </div>
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
            <input type="email" id="newsletterEmail" placeholder="Your email address" required>
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
                    <li><a href="#" onclick="showToast('Free downloads coming soon!', 'info')">Free Downloads</a></li>
                    <li><a href="#" onclick="showToast('Prayer guides available in the dashboard', 'info')">Prayer Guides</a></li>
                    <li><a href="#" onclick="showToast('Monthly prophetic words sent to subscribers', 'info')">Prophetic Words</a></li>
                    <li><a href="#" onclick="showToast('Read testimonies in our blog section', 'info')">Testimonies</a></li>
                    <li><a href="#" onclick="showToast('FAQ section under development', 'info')">FAQ</a></li>
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
        // ==================== SYSTEM INITIALIZATION ====================
        class ECommerceSystem {
            constructor() {
                this.cart = JSON.parse(localStorage.getItem('definitiveWordCart')) || [];
                this.currentUser = JSON.parse(localStorage.getItem('definitiveWordUser')) || null;
                this.purchases = JSON.parse(localStorage.getItem('definitiveWordPurchases')) || [];
                this.sessions = JSON.parse(localStorage.getItem('definitiveWordSessions')) || [];
                this.newsletterSubscribers = JSON.parse(localStorage.getItem('definitiveWordNewsletter')) || [];
                this.ebooks = {
                    1: { id: 1, title: "Unveiling Your Destiny", price: 349.99, format: "PDF/EPUB" },
                    2: { id: 2, title: "Prophetic Insights", price: 449.99, format: "PDF/EPUB" },
                    3: { id: 3, title: "The Written Word", price: 299.99, format: "PDF/EPUB" },
                    4: { id: 4, title: "Prophetic Activation Workshop", price: 599.99, type: "workshop" },
                    5: { id: 5, title: "Destiny Mapping Masterclass", price: 799.99, type: "workshop" }
                };
                this.init();
            }

            init() {
                this.updateCartUI();
                this.updateAuthUI();
                this.setupEventListeners();
                console.log('E-Commerce System Initialized');
            }

            // ==================== CART MANAGEMENT ====================
            addToCart(id, title, price) {
                if (!this.currentUser) {
                    this.showToast('Please login to add items to cart', 'warning');
                    openAuthModal();
                    return;
                }

                const existingItem = this.cart.find(item => item.id === id);
                if (existingItem) {
                    existingItem.quantity++;
                } else {
                    this.cart.push({ id, title, price, quantity: 1 });
                }

                this.saveCart();
                this.updateCartUI();
                this.showToast(`"${title}" added to cart`, 'success');
            }

            removeFromCart(id) {
                this.cart = this.cart.filter(item => item.id !== id);
                this.saveCart();
                this.updateCartUI();
                this.showToast('Item removed from cart', 'success');
            }

            updateQuantity(id, quantity) {
                const item = this.cart.find(item => item.id === id);
                if (item) {
                    if (quantity <= 0) {
                        this.removeFromCart(id);
                    } else {
                        item.quantity = quantity;
                        this.saveCart();
                        this.updateCartUI();
                    }
                }
            }

            clearCart() {
                this.cart = [];
                this.saveCart();
                this.updateCartUI();
                this.showToast('Cart cleared', 'success');
            }

            getCartTotal() {
                return this.cart.reduce((total, item) => total + (item.price * item.quantity), 0);
            }

            saveCart() {
                localStorage.setItem('definitiveWordCart', JSON.stringify(this.cart));
            }

            // ==================== USER AUTHENTICATION ====================
            login(email, password) {
                // Simulate API call
                this.showLoading();
                setTimeout(() => {
                    this.currentUser = {
                        id: Date.now(),
                        name: email.split('@')[0],
                        email: email,
                        avatar: email.charAt(0).toUpperCase(),
                        joinDate: new Date().toLocaleDateString()
                    };
                    
                    localStorage.setItem('definitiveWordUser', JSON.stringify(this.currentUser));
                    this.updateAuthUI();
                    this.hideLoading();
                    this.showToast('Login successful! Welcome back.', 'success');
                }, 1000);
            }

            register(name, email, password) {
                // Simulate API call
                this.showLoading();
                setTimeout(() => {
                    this.currentUser = {
                        id: Date.now(),
                        name: name,
                        email: email,
                        avatar: name.charAt(0).toUpperCase(),
                        joinDate: new Date().toLocaleDateString()
                    };
                    
                    localStorage.setItem('definitiveWordUser', JSON.stringify(this.currentUser));
                    this.updateAuthUI();
                    this.hideLoading();
                    this.showToast('Registration successful! Welcome to The Definitive Word.', 'success');
                }, 1000);
            }

            logout() {
                this.currentUser = null;
                localStorage.removeItem('definitiveWordUser');
                this.updateAuthUI();
                this.showToast('You have been logged out.', 'info');
            }

            // ==================== PURCHASE MANAGEMENT ====================
            purchaseCart() {
                if (this.cart.length === 0) {
                    this.showToast('Your cart is empty', 'warning');
                    return;
                }

                this.showLoading();
                setTimeout(() => {
                    // Record purchases
                    this.cart.forEach(item => {
                        this.purchases.push({
                            ...item,
                            purchaseDate: new Date().toISOString(),
                            downloadLink: `https://definitiveword.org/downloads/${item.id}`,
                            status: 'completed'
                        });
                    });

                    // Record workshop registrations
                    this.cart.forEach(item => {
                        if (this.ebooks[item.id]?.type === 'workshop') {
                            this.sessions.push({
                                id: item.id,
                                title: item.title,
                                date: item.id === 4 ? 'December 15, 2025' : 'January 22, 2026',
                                time: item.id === 4 ? '9:00 AM - 4:00 PM' : '6:00 PM - 9:00 PM',
                                location: item.id === 4 ? 'Virtual (Zoom)' : 'Cape Town, South Africa'
                            });
                        }
                    });

                    localStorage.setItem('definitiveWordPurchases', JSON.stringify(this.purchases));
                    localStorage.setItem('definitiveWordSessions', JSON.stringify(this.sessions));

                    this.cart = [];
                    this.saveCart();
                    this.updateCartUI();
                    
                    this.hideLoading();
                    this.showToast('Purchase successful! Check your dashboard for downloads.', 'success');
                    closeCart();
                }, 1500);
            }

            // ==================== UI UPDATES ====================
            updateCartUI() {
                const cartCount = document.getElementById('cartCount');
                const totalItems = this.cart.reduce((sum, item) => sum + item.quantity, 0);
                cartCount.textContent = totalItems;
                cartCount.style.display = totalItems > 0 ? 'flex' : 'none';

                if (document.getElementById('cartItems')) {
                    this.renderCart();
                }
            }

            updateAuthUI() {
                const userInfo = document.getElementById('userInfo');
                const authButtons = document.getElementById('authButtons');
                
                if (this.currentUser) {
                    userInfo.style.display = 'flex';
                    authButtons.style.display = 'none';
                    document.getElementById('userName').textContent = this.currentUser.name;
                    document.getElementById('userAvatar').textContent = this.currentUser.avatar;
                } else {
                    userInfo.style.display = 'none';
                    authButtons.style.display = 'flex';
                }
            }

            renderCart() {
                const cartItems = document.getElementById('cartItems');
                const cartEmpty = document.getElementById('cartEmpty');
                const cartTotal = document.getElementById('cartTotal');
                const cartActions = document.getElementById('cartActions');
                const cartTotalAmount = document.getElementById('cartTotalAmount');

                if (this.cart.length === 0) {
                    cartEmpty.style.display = 'block';
                    cartTotal.style.display = 'none';
                    cartActions.style.display = 'none';
                    cartItems.innerHTML = '';
                    return;
                }

                cartEmpty.style.display = 'none';
                cartTotal.style.display = 'flex';
                cartActions.style.display = 'flex';

                cartItems.innerHTML = this.cart.map(item => `
                    <div class="cart-item">
                        <div class="cart-item-info">
                            <h4>${item.title}</h4>
                            <div class="cart-item-price">R${item.price.toFixed(2)} × ${item.quantity}</div>
                        </div>
                        <div>
                            <button onclick="ecommerce.updateQuantity(${item.id}, ${item.quantity - 1})" style="background: none; border: none; color: var(--prophetic-red); cursor: pointer; font-size: 1.2rem;">-</button>
                            <span style="margin: 0 0.5rem;">${item.quantity}</span>
                            <button onclick="ecommerce.updateQuantity(${item.id}, ${item.quantity + 1})" style="background: none; border: none; color: var(--success); cursor: pointer; font-size: 1.2rem;">+</button>
                        </div>
                    </div>
                `).join('');

                cartTotalAmount.textContent = `R${this.getCartTotal().toFixed(2)}`;
            }

            updateDashboard() {
                if (!this.currentUser) return;

                document.getElementById('dashboardName').textContent = this.currentUser.name;
                document.getElementById('dashboardEmail').textContent = this.currentUser.email;
                document.getElementById('dashboardJoinDate').textContent = this.currentUser.joinDate;

                const purchasesList = document.getElementById('purchasesList');
                purchasesList.innerHTML = this.purchases.length === 0 
                    ? '<li>No purchases yet</li>'
                    : this.purchases.map(purchase => `
                        <li>
                            <div>
                                <strong>${purchase.title}</strong><br>
                                <small>Purchased: ${new Date(purchase.purchaseDate).toLocaleDateString()}</small>
                            </div>
                            <button class="download-btn" onclick="ecommerce.downloadItem(${purchase.id})">
                                <i class="fas fa-download"></i> Download
                            </button>
                        </li>
                    `).join('');

                const sessionsList = document.getElementById('sessionsList');
                sessionsList.innerHTML = this.sessions.length === 0
                    ? '<li>No upcoming sessions</li>'
                    : this.sessions.map(session => `
                        <li>
                            <div>
                                <strong>${session.title}</strong><br>
                                <small>${session.date} • ${session.time}</small>
                            </div>
                            <span style="color: var(--success); font-size: 0.9rem;">
                                <i class="fas fa-check-circle"></i> Registered
                            </span>
                        </li>
                    `).join('');
            }

            // ==================== UTILITIES ====================
            showToast(message, type = 'success') {
                const toast = document.getElementById('toast');
                const toastMessage = document.getElementById('toastMessage');
                
                toastMessage.textContent = message;
                toast.className = `toast ${type}`;
                toast.classList.add('show');

                // Update icon based on type
                const icon = toast.querySelector('i');
                if (type === 'success') {
                    icon.className = 'fas fa-check-circle';
                } else if (type === 'error') {
                    icon.className = 'fas fa-exclamation-circle';
                } else if (type === 'warning') {
                    icon.className = 'fas fa-exclamation-triangle';
                } else {
                    icon.className = 'fas fa-info-circle';
                }

                setTimeout(() => {
                    toast.classList.remove('show');
                }, 3000);
            }

            showLoading() {
                document.getElementById('loadingOverlay').style.display = 'flex';
            }

            hideLoading() {
                document.getElementById('loadingOverlay').style.display = 'none';
            }

            downloadItem(id) {
                this.showToast(`Starting download of "${this.ebooks[id]?.title}"`, 'success');
                // In production, this would trigger actual file download
                setTimeout(() => {
                    this.showToast('Download complete! Check your downloads folder.', 'success');
                }, 1000);
            }

            setupEventListeners() {
                // Close modals on ESC key
                document.addEventListener('keydown', (e) => {
                    if (e.key === 'Escape') {
                        closeCart();
                        closeAuthModal();
                        closeDashboard();
                    }
                });

                // Prevent body scroll when modal is open
                const modals = ['cartModal', 'authModal', 'dashboardModal'];
                modals.forEach(modalId => {
                    const modal = document.getElementById(modalId);
                    if (modal) {
                        modal.addEventListener('shown', () => {
                            document.body.style.overflow = 'hidden';
                        });
                        modal.addEventListener('hidden', () => {
                            document.body.style.overflow = 'auto';
                        });
                    }
                });
            }
        }

        // ==================== GLOBAL INSTANCE ====================
        const ecommerce = new ECommerceSystem();

        // ==================== DOM FUNCTIONS ====================
        function toggleMenu() {
            const menu = document.getElementById('navMenu');
            menu.classList.toggle('active');
        }

        function scrollToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // ==================== MODAL FUNCTIONS ====================
        function openCart() {
            document.getElementById('cartModal').style.display = 'block';
            ecommerce.renderCart();
        }

        function closeCart() {
            document.getElementById('cartModal').style.display = 'none';
        }

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

        function openDashboard() {
            if (!ecommerce.currentUser) {
                openAuthModal();
                return;
            }
            ecommerce.updateDashboard();
            document.getElementById('dashboardModal').style.display = 'block';
        }

        function closeDashboard() {
            document.getElementById('dashboardModal').style.display = 'none';
        }

        // ==================== FORM HANDLERS ====================
        function handleLogin(event) {
            event.preventDefault();
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;
            ecommerce.login(email, password);
            closeAuthModal();
        }

        function handleRegister(event) {
            event.preventDefault();
            const name = document.getElementById('registerName').value;
            const email = document.getElementById('registerEmail').value;
            const password = document.getElementById('registerPassword').value;
            const confirmPassword = document.getElementById('registerConfirmPassword').value;

            if (password !== confirmPassword) {
                ecommerce.showToast('Passwords do not match', 'error');
                return;
            }

            ecommerce.register(name, email, password);
            closeAuthModal();
        }

        // ==================== ACTION FUNCTIONS ====================
        function addToCart(id, title, price) {
            ecommerce.addToCart(id, title, price);
        }

        function checkout() {
            ecommerce.purchaseCart();
        }

        function bookCoaching() {
            if (!ecommerce.currentUser) {
                ecommerce.showToast('Please login to book coaching', 'warning');
                openAuthModal();
                return;
            }

            const name = prompt('Please enter your name for the coaching session:');
            if (name) {
                const date = prompt('Preferred date (e.g., December 20, 2025):');
                const time = prompt('Preferred time (e.g., 2:00 PM):');
                
                if (date && time) {
                    ecommerce.sessions.push({
                        id: Date.now(),
                        title: 'Personal Prophetic Coaching',
                        date: date,
                        time: time,
                        location: 'Virtual (Zoom)',
                        type: 'coaching'
                    });
                    localStorage.setItem('definitiveWordSessions', JSON.stringify(ecommerce.sessions));
                    ecommerce.showToast('Coaching session booked successfully!', 'success');
                }
            }
        }

        function showPreview(id) {
            const ebook = ecommerce.ebooks[id];
            if (ebook) {
                ecommerce.showToast(`Preview available for "${ebook.title}"`, 'info');
                // In production, this would open a PDF preview
            }
        }

        function showWorkshopDetails(id) {
            const workshop = ecommerce.ebooks[id];
            if (workshop) {
                const details = `
                    <strong>${workshop.title}</strong><br><br>
                    <strong>Description:</strong><br>
                    ${id === 4 ? 'A powerful one-day intensive designed to activate and strengthen your prophetic gifting.' : 'Discover God\'s blueprint for your life and create a practical roadmap to walk in your divine purpose.'}
                    <br><br>
                    <strong>Includes:</strong><br>
                    • Live teaching sessions<br>
                    • Interactive workshops<br>
                    • Q&A sessions<br>
                    • Digital workbook<br>
                    • Certificate of completion<br><br>
                    <strong>Investment:</strong> R${workshop.price.toFixed(2)}
                `;
                alert(details);
            }
        }

        function readBlog(id) {
            const blogs = {
                1: {
                    title: "Walking in Your Prophetic Purpose",
                    content: "This blog post explores how to align your daily life with the prophetic words spoken over you..."
                },
                2: {
                    title: "The Power of Declared Destiny",
                    content: "Understanding how God's written word over your life shapes your future..."
                },
                3: {
                    title: "Breaking Through Limitations",
                    content: "Practical steps to overcome barriers through faith and strategic action..."
                }
            };
            ecommerce.showToast(`Opening blog: "${blogs[id].title}"`, 'info');
            // In production, this would navigate to the full blog post
        }

        function submitContact(event) {
            event.preventDefault();
            const name = document.getElementById('name').value;
            ecommerce.showToast(`Thank you ${name}! Your message has been sent.`, 'success');
            event.target.reset();
        }

        function subscribeNewsletter(event) {
            event.preventDefault();
            const email = document.getElementById('newsletterEmail').value;
            
            if (!ecommerce.newsletterSubscribers.includes(email)) {
                ecommerce.newsletterSubscribers.push(email);
                localStorage.setItem('definitiveWordNewsletter', JSON.stringify(ecommerce.newsletterSubscribers));
                ecommerce.showToast('Thank you for subscribing!', 'success');
            } else {
                ecommerce.showToast('You are already subscribed!', 'info');
            }
            
            event.target.reset();
        }

        function changePassword() {
            const newPassword = prompt('Enter new password (min. 6 characters):');
            if (newPassword && newPassword.length >= 6) {
                ecommerce.showToast('Password updated successfully!', 'success');
            }
        }

        function logout() {
            ecommerce.logout();
            closeDashboard();
        }

        function showToast(message, type = 'info') {
            ecommerce.showToast(message, type);
        }

        // ==================== SCROLL EFFECTS ====================
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            const progressBar = document.querySelector('.progress-bar');
            
            // Header shadow
            if (window.scrollY > 100) {
                header.classList.add('header-scrolled');
            } else {
                header.classList.remove('header-scrolled');
            }

            // Progress bar
            const winScroll = document.body.scrollTop || document.documentElement.scrollTop;
            const height = document.documentElement.scrollHeight - document.documentElement.clientHeight;
            const scrolled = (winScroll / height) * 100;
            progressBar.style.width = scrolled + "%";

            // Close mobile menu on scroll
            document.getElementById('navMenu').classList.remove('active');
        });

        // Smooth scrolling for navigation
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

        // Close modals when clicking outside
        window.addEventListener('click', function(event) {
            const authModal = document.getElementById('authModal');
            const dashboardModal = document.getElementById('dashboardModal');
            
            if (event.target === authModal) {
                closeAuthModal();
            }
            if (event.target === dashboardModal) {
                closeDashboard();
            }
        });

        // Initialize on page load
        document.addEventListener('DOMContentLoaded', function() {
            console.log('The Definitive Word website fully loaded and operational!');
            console.log('E-Commerce System Status: ACTIVE');
            console.log('User Authentication: READY');
            console.log('Cart System: READY');
            console.log('Dashboard System: READY');
            
            // Animate sections on scroll
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };

            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('fade-in');
                    }
                });
            }, observerOptions);

            document.querySelectorAll('section').forEach(section => {
                observer.observe(section);
            });
        });
    </script>
</body>
</html>
