<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Your Destiny Has Been Written</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --prophetic-blue: #1e3a8a;
            --prophetic-red: #dc2626;
            --white: #ffffff;
            --light-gray: #f3f4f6;
            --dark-gray: #374151;
            --gold: #d4af37;
        }

        body {
            font-family: 'Georgia', serif;
            line-height: 1.6;
            color: var(--dark-gray);
            background-color: var(--white);
        }

        /* Header */
        header {
            background: linear-gradient(135deg, var(--prophetic-blue), var(--prophetic-red));
            color: var(--white);
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo h1 {
            font-size: 1.5rem;
            font-weight: bold;
        }

        .logo p {
            font-size: 0.9rem;
            font-style: italic;
            opacity: 0.9;
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
            transition: opacity 0.3s;
        }

        nav a:hover {
            opacity: 0.8;
        }

        .menu-toggle {
            display: none;
            background: none;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(30, 58, 138, 0.9), rgba(220, 38, 38, 0.9)), url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><rect fill="%231e3a8a" width="1200" height="600"/></svg>');
            background-size: cover;
            background-position: center;
            color: var(--white);
            text-align: center;
            padding: 8rem 2rem;
        }

        .hero h2 {
            font-size: 3rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            font-style: italic;
        }

        .cta-button {
            display: inline-block;
            background: var(--prophetic-red);
            color: var(--white);
            padding: 1rem 2.5rem;
            text-decoration: none;
            border-radius: 5px;
            font-weight: bold;
            transition: transform 0.3s, box-shadow 0.3s;
            border: none;
            cursor: pointer;
            font-size: 1rem;
        }

        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(220, 38, 38, 0.4);
        }

        /* Sections */
        section {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 2rem;
        }

        section h2 {
            color: var(--prophetic-blue);
            font-size: 2.5rem;
            margin-bottom: 2rem;
            text-align: center;
        }

        /* E-books Grid */
        .ebooks-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .ebook-card {
            background: var(--white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .ebook-card:hover {
            transform: translateY(-5px);
        }

        .ebook-image {
            width: 100%;
            height: 300px;
            background: linear-gradient(135deg, var(--prophetic-blue), var(--prophetic-red));
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 3rem;
        }

        .ebook-content {
            padding: 1.5rem;
        }

        .ebook-content h3 {
            color: var(--prophetic-blue);
            margin-bottom: 0.5rem;
        }

        .ebook-content p {
            margin-bottom: 1rem;
            color: var(--dark-gray);
        }

        .price {
            font-size: 1.5rem;
            color: var(--prophetic-red);
            font-weight: bold;
            margin-bottom: 1rem;
        }

        /* Life Coaching */
        .coaching-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .coaching-text ul {
            margin: 1.5rem 0;
            padding-left: 2rem;
        }

        .coaching-text li {
            margin-bottom: 0.8rem;
            color: var(--dark-gray);
        }

        /* Blog */
        .blog-posts {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .blog-post {
            background: var(--light-gray);
            padding: 2rem;
            border-radius: 10px;
            border-left: 4px solid var(--prophetic-blue);
        }

        .blog-post h3 {
            color: var(--prophetic-blue);
            margin-bottom: 0.5rem;
        }

        .blog-date {
            font-size: 0.9rem;
            color: #6b7280;
            margin-bottom: 1rem;
        }

        /* Workshops */
        .workshops-grid {
            display: grid;
            gap: 2rem;
            margin-top: 2rem;
        }

        .workshop-card {
            background: var(--white);
            border: 2px solid var(--prophetic-blue);
            padding: 2rem;
            border-radius: 10px;
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 2rem;
            align-items: center;
        }

        .workshop-date {
            background: var(--prophetic-red);
            color: var(--white);
            padding: 2rem;
            text-align: center;
            border-radius: 10px;
        }

        .workshop-date .day {
            font-size: 3rem;
            font-weight: bold;
        }

        .workshop-date .month {
            font-size: 1.2rem;
        }

        /* Contact Form */
        .contact-form {
            max-width: 600px;
            margin: 2rem auto;
            background: var(--light-gray);
            padding: 2rem;
            border-radius: 10px;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--prophetic-blue);
            font-weight: bold;
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #d1d5db;
            border-radius: 5px;
            font-family: inherit;
        }

        .form-group textarea {
            min-height: 120px;
            resize: vertical;
        }

        /* Payment Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 2000;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 10px;
            max-width: 500px;
            width: 90%;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
            border-bottom: 1px solid #e5e7eb;
            padding-bottom: 1rem;
        }

        .modal-header h3 {
            color: var(--prophetic-blue);
        }

        .close-modal {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--dark-gray);
        }

        .payment-options {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 1rem;
            margin: 1.5rem 0;
        }

        .payment-option {
            border: 2px solid #e5e7eb;
            border-radius: 5px;
            padding: 1rem;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
        }

        .payment-option:hover {
            border-color: var(--prophetic-blue);
        }

        .payment-option.selected {
            border-color: var(--prophetic-blue);
            background-color: rgba(30, 58, 138, 0.05);
        }

        .payment-icon {
            font-size: 2rem;
            margin-bottom: 0.5rem;
        }

        /* Footer */
        footer {
            background: var(--prophetic-blue);
            color: var(--white);
            text-align: center;
            padding: 2rem;
            margin-top: 4rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 1rem;
        }

        .social-links a {
            color: var(--white);
            font-size: 1.5rem;
            transition: color 0.3s;
        }

        .social-links a:hover {
            color: var(--prophetic-red);
        }

        /* Responsive */
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
                padding: 1rem;
            }

            nav ul.active {
                display: flex;
            }

            .hero h2 {
                font-size: 2rem;
            }

            .coaching-content,
            .workshop-card {
                grid-template-columns: 1fr;
            }
        }

        .alt-bg {
            background: var(--light-gray);
        }
    </style>
</head>
<body>
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
        </nav>
    </header>

    <section id="home" class="hero">
        <h2>Welcome to The Definitive Word</h2>
        <p>Your Destiny Has Been Written</p>
        <p>Discover God's plan for your life through prophetic teaching, life coaching, and transformative resources</p>
        <a href="#ebooks" class="cta-button">Explore Our Resources</a>
    </section>

    <section id="ebooks">
        <h2>Featured E-books</h2>
        <p style="text-align: center; max-width: 800px; margin: 0 auto 2rem;">Dive deep into prophetic wisdom and biblical teaching with our collection of transformative e-books.</p>
        
        <div class="ebooks-grid">
            <div class="ebook-card">
                <div class="ebook-image">📖</div>
                <div class="ebook-content">
                    <h3>Unveiling Your Destiny</h3>
                    <p>A comprehensive guide to discovering and walking in your God-given purpose.</p>
                    <div class="price">R 299.99</div>
                    <button class="cta-button" onclick="purchaseEbook('Unveiling Your Destiny', 299.99)">Purchase Now</button>
                </div>
            </div>

            <div class="ebook-card">
                <div class="ebook-image">🕊️</div>
                <div class="ebook-content">
                    <h3>Prophetic Insights</h3>
                    <p>Understanding the prophetic voice in the modern church and your personal life.</p>
                    <div class="price">R 349.99</div>
                    <button class="cta-button" onclick="purchaseEbook('Prophetic Insights', 349.99)">Purchase Now</button>
                </div>
            </div>

            <div class="ebook-card">
                <div class="ebook-image">✝️</div>
                <div class="ebook-content">
                    <h3>The Written Word</h3>
                    <p>Exploring the power of God's promises and declarations over your life.</p>
                    <div class="price">R 269.99</div>
                    <button class="cta-button" onclick="purchaseEbook('The Written Word', 269.99)">Purchase Now</button>
                </div>
            </div>
        </div>
    </section>

    <section id="coaching" class="alt-bg">
        <h2>Life Coaching</h2>
        <div class="coaching-content">
            <div class="coaching-text">
                <h3>Transform Your Life Through Prophetic Coaching</h3>
                <p>Our life coaching program combines biblical principles with practical strategies to help you:</p>
                <ul>
                    <li>Discover your divine purpose and calling</li>
                    <li>Overcome obstacles and limiting beliefs</li>
                    <li>Develop spiritual disciplines and growth</li>
                    <li>Create actionable plans for your goals</li>
                    <li>Walk in the fullness of your destiny</li>
                </ul>
                <button class="cta-button" onclick="bookCoaching()">Book a Session</button>
            </div>
            <div>
                <div style="background: linear-gradient(135deg, var(--prophetic-blue), var(--prophetic-red)); height: 400px; border-radius: 10px; display: flex; align-items: center; justify-content: center; color: white; font-size: 4rem;">
                    🎯
                </div>
            </div>
        </div>
    </section>

    <section id="blog">
        <h2>Latest from the Blog</h2>
        <div class="blog-posts">
            <article class="blog-post">
                <h3>Walking in Your Prophetic Purpose</h3>
                <p class="blog-date">November 20, 2025</p>
                <p>Discovering how to align your daily life with the prophetic words spoken over you...</p>
                <a href="#" onclick="readBlog(1); return false;">Read More →</a>
            </article>

            <article class="blog-post">
                <h3>The Power of Declared Destiny</h3>
                <p class="blog-date">November 15, 2025</p>
                <p>Understanding how God's written word over your life shapes your future...</p>
                <a href="#" onclick="readBlog(2); return false;">Read More →</a>
            </article>

            <article class="blog-post">
                <h3>Breaking Through Limitations</h3>
                <p class="blog-date">November 10, 2025</p>
                <p>Practical steps to overcome the barriers standing between you and your destiny...</p>
                <a href="#" onclick="readBlog(3); return false;">Read More →</a>
            </article>
        </div>
    </section>

    <section id="workshops" class="alt-bg">
        <h2>Upcoming Workshops</h2>
        <div class="workshops-grid">
            <div class="workshop-card">
                <div class="workshop-date">
                    <div class="day">15</div>
                    <div class="month">DEC 2025</div>
                </div>
                <div>
                    <h3>Prophetic Activation Workshop</h3>
                    <p>A powerful one-day intensive designed to activate and strengthen your prophetic gifting. Learn to hear God's voice clearly and minister prophetically with confidence.</p>
                    <p><strong>Location:</strong> Virtual (Zoom)</p>
                    <p><strong>Time:</strong> 9:00 AM - 4:00 PM</p>
                    <p><strong>Cost:</strong> R 499.99</p>
                    <button class="cta-button" onclick="registerWorkshop('Prophetic Activation', 499.99)">Register Now</button>
                </div>
            </div>

            <div class="workshop-card">
                <div class="workshop-date">
                    <div class="day">22</div>
                    <div class="month">JAN 2026</div>
                </div>
                <div>
                    <h3>Destiny Mapping Masterclass</h3>
                    <p>Discover God's blueprint for your life and create a practical roadmap to walk in your divine purpose. Limited to 20 participants for personalized attention.</p>
                    <p><strong>Location:</strong> Cape Town, South Africa</p>
                    <p><strong>Time:</strong> 6:00 PM - 9:00 PM</p>
                    <p><strong>Cost:</strong> R 799.99</p>
                    <button class="cta-button" onclick="registerWorkshop('Destiny Mapping', 799.99)">Register Now</button>
                </div>
            </div>
        </div>
    </section>

    <section id="ministry">
        <h2>Our Ministry</h2>
        <div style="max-width: 800px; margin: 0 auto; text-align: center;">
            <p style="font-size: 1.2rem; margin-bottom: 2rem;">The Definitive Word Ministry is dedicated to helping believers understand that their destiny has already been written by God. Through prophetic teaching, life coaching, and biblical resources, we equip people to walk confidently in their divine calling.</p>
            
            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 2rem; margin: 3rem 0;">
                <div>
                    <div style="font-size: 3rem; color: var(--prophetic-blue);">📖</div>
                    <h3 style="color: var(--prophetic-blue);">Teaching</h3>
                    <p>Biblical and prophetic instruction</p>
                </div>
                <div>
                    <div style="font-size: 3rem; color: var(--prophetic-red);">🙏</div>
                    <h3 style="color: var(--prophetic-red);">Prayer</h3>
                    <p>Intercessory and prophetic prayer</p>
                </div>
                <div>
                    <div style="font-size: 3rem; color: var(--prophetic-blue);">💡</div>
                    <h3 style="color: var(--prophetic-blue);">Coaching</h3>
                    <p>Personal transformation guidance</p>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="alt-bg">
        <h2>Get In Touch</h2>
        <div class="contact-form">
            <form id="contactForm" onsubmit="submitContact(event)">
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
    </section>

    <!-- Payment Modal -->
    <div id="paymentModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 id="modalTitle">Complete Your Purchase</h3>
                <button class="close-modal" onclick="closePaymentModal()">×</button>
            </div>
            <div id="modalBody">
                <p>You are purchasing: <strong id="purchaseItem"></strong></p>
                <p>Amount: <strong id="purchaseAmount"></strong></p>
                
                <h4>Select Payment Method</h4>
                <div class="payment-options">
                    <div class="payment-option" onclick="selectPaymentMethod('credit-card')">
                        <div class="payment-icon">💳</div>
                        <div>Credit Card</div>
                    </div>
                    <div class="payment-option" onclick="selectPaymentMethod('paypal')">
                        <div class="payment-icon">🔵</div>
                        <div>PayPal</div>
                    </div>
                    <div class="payment-option" onclick="selectPaymentMethod('eft')">
                        <div class="payment-icon">🏦</div>
                        <div>EFT</div>
                    </div>
                    <div class="payment-option" onclick="selectPaymentMethod('snapscan')">
                        <div class="payment-icon">📱</div>
                        <div>SnapScan</div>
                    </div>
                </div>
                
                <div id="paymentDetails">
                    <!-- Payment form will be inserted here based on selection -->
                </div>
                
                <button id="completePayment" class="cta-button" style="width: 100%; margin-top: 1rem;" onclick="completePayment()">Complete Payment</button>
            </div>
        </div>
    </div>

    <footer>
        <p>&copy; 2025 The Definitive Word Ministry. Your Destiny Has Been Written.</p>
        <div class="social-links">
            <a href="#" title="Facebook">📘</a>
            <a href="#" title="Instagram">📷</a>
            <a href="#" title="YouTube">📺</a>
            <a href="#" title="Email">✉️</a>
        </div>
        <p style="margin-top: 1rem; font-size: 0.9rem;">Walking in prophetic purpose since 2025</p>
    </footer>

    <script>
        // Global variables
        let currentPurchase = {
            type: '',
            item: '',
            amount: 0,
            paymentMethod: ''
        };

        // Navigation functions
        function toggleMenu() {
            const menu = document.getElementById('navMenu');
            menu.classList.toggle('active');
        }

        // Purchase functions
        function purchaseEbook(title, price) {
            currentPurchase = {
                type: 'ebook',
                item: title,
                amount: price,
                paymentMethod: ''
            };
            
            document.getElementById('purchaseItem').textContent = title;
            document.getElementById('purchaseAmount').textContent = `R ${price.toFixed(2)}`;
            document.getElementById('paymentDetails').innerHTML = '';
            document.getElementById('paymentModal').style.display = 'flex';
        }

        function registerWorkshop(workshop, price) {
            currentPurchase = {
                type: 'workshop',
                item: workshop,
                amount: price,
                paymentMethod: ''
            };
            
            document.getElementById('purchaseItem').textContent = `${workshop} Workshop`;
            document.getElementById('purchaseAmount').textContent = `R ${price.toFixed(2)}`;
            document.getElementById('paymentDetails').innerHTML = '';
            document.getElementById('paymentModal').style.display = 'flex';
        }

        function bookCoaching() {
            currentPurchase = {
                type: 'coaching',
                item: 'Life Coaching Session',
                amount: 0,
                paymentMethod: ''
            };
            
            document.getElementById('purchaseItem').textContent = 'Life Coaching Session';
            document.getElementById('purchaseAmount').textContent = 'Free Consultation';
            document.getElementById('paymentDetails').innerHTML = `
                <p>We'll contact you to schedule your free consultation session.</p>
                <div class="form-group">
                    <label for="preferredDate">Preferred Date</label>
                    <input type="date" id="preferredDate" name="preferredDate">
                </div>
                <div class="form-group">
                    <label for="preferredTime">Preferred Time</label>
                    <select id="preferredTime" name="preferredTime">
                        <option value="morning">Morning (9am-12pm)</option>
                        <option value="afternoon">Afternoon (1pm-4pm)</option>
                        <option value="evening">Evening (5pm-8pm)</option>
                    </select>
                </div>
            `;
            document.getElementById('paymentModal').style.display = 'flex';
        }

        function selectPaymentMethod(method) {
            // Remove selected class from all options
            document.querySelectorAll('.payment-option').forEach(option => {
                option.classList.remove('selected');
            });
            
            // Add selected class to clicked option
            event.target.closest('.payment-option').classList.add('selected');
            
            currentPurchase.paymentMethod = method;
            
            // Show appropriate payment form
            let paymentForm = '';
            
            switch(method) {
                case 'credit-card':
                    paymentForm = `
                        <div class="form-group">
                            <label for="cardNumber">Card Number</label>
                            <input type="text" id="cardNumber" placeholder="1234 5678 9012 3456" required>
                        </div>
                        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem;">
                            <div class="form-group">
                                <label for="expiryDate">Expiry Date</label>
                                <input type="text" id="expiryDate" placeholder="MM/YY" required>
                            </div>
                            <div class="form-group">
                                <label for="cvv">CVV</label>
                                <input type="text" id="cvv" placeholder="123" required>
                            </div>
                        </div>
                        <div class="form-group">
                            <label for="cardName">Name on Card</label>
                            <input type="text" id="cardName" required>
                        </div>
                    `;
                    break;
                case 'eft':
                    paymentForm = `
                        <p>Please use the following banking details for your EFT payment:</p>
                        <p><strong>Bank:</strong> Standard Bank<br>
                        <strong>Account Name:</strong> The Definitive Word Ministry<br>
                        <strong>Account Number:</strong> 0123456789<br>
                        <strong>Branch Code:</strong> 051001</p>
                        <p>Please use your name as reference.</p>
                    `;
                    break;
                case 'snapscan':
                    paymentForm = `
                        <p>Scan the QR code below with the SnapScan app to complete your payment:</p>
                        <div style="text-align: center; margin: 1rem 0;">
                            <div style="width: 200px; height: 200px; background: #f0f0f0; margin: 0 auto; display: flex; align-items: center; justify-content: center; font-size: 4rem;">
                                📱
                            </div>
                        </div>
                    `;
                    break;
                case 'paypal':
                    paymentForm = `
                        <p>You will be redirected to PayPal to complete your payment.</p>
                        <div style="text-align: center; margin: 1rem 0;">
                            <div style="font-size: 3rem;">🔵</div>
                        </div>
                    `;
                    break;
            }
            
            document.getElementById('paymentDetails').innerHTML = paymentForm;
        }

        function completePayment() {
            if (currentPurchase.paymentMethod === '') {
                alert('Please select a payment method');
                return;
            }
            
            let message = '';
            
            if (currentPurchase.type === 'coaching') {
                const date = document.getElementById('preferredDate').value;
                const time = document.getElementById('preferredTime').value;
                
                message = `Thank you for booking your Life Coaching session!\n\nWe have received your request for a ${time} session on ${date}.\n\nWe will contact you within 24 hours to confirm your appointment.`;
            } else {
                message = `Thank you for your purchase of "${currentPurchase.item}"!\n\nYour payment of R ${currentPurchase.amount.toFixed(2)} has been processed successfully.\n\nYou will receive a confirmation email shortly.`;
            }
            
            alert(message);
            closePaymentModal();
            
            // In a real implementation, you would send this data to your server
            console.log('Purchase completed:', currentPurchase);
        }

        function closePaymentModal() {
            document.getElementById('paymentModal').style.display = 'none';
            currentPurchase = {
                type: '',
                item: '',
                amount: 0,
                paymentMethod: ''
            };
        }

        // Other functions
        function readBlog(id) {
            const blogTitles = [
                'Walking in Your Prophetic Purpose',
                'The Power of Declared Destiny',
                'Breaking Through Limitations'
            ];
            
            alert(`Opening blog post: "${blogTitles[id-1]}"\n\nIn a complete implementation, this would display the full blog content.`);
        }

        function submitContact(event) {
            event.preventDefault();
            const formData = new FormData(event.target);
            const name = formData.get('name');
            const email = formData.get('email');
            const subject = formData.get('subject');
            const message = formData.get('message');
            
            alert(`Thank you ${name} for your message!\n\nWe have received your inquiry about "${subject}" and will respond to ${email} within 48 hours.\n\nBlessings,\nThe Definitive Word Team`);
            
            // Reset form
            document.getElementById('contactForm').reset();
            
            // In a real implementation, you would send this data to your server
            console.log('Contact form submitted:', { name, email, subject, message });
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

        // Close modal when clicking outside
        window.addEventListener('click', function(event) {
            const modal = document.getElementById('paymentModal');
            if (event.target === modal) {
                closePaymentModal();
            }
        });
    </script>
</body>
</html>
