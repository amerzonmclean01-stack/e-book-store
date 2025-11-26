<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Ebook Store</title>
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f9fafb;
            line-height: 1.6;
        }

        .app {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        .main-content {
            flex: 1;
        }

        /* Navigation */
        nav {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .nav-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 80px;
        }

        .logo {
            display: flex;
            align-items: center;
            cursor: pointer;
        }

        .logo-icon {
            font-size: 2rem;
            margin-right: 12px;
        }

        .logo-text h1 {
            font-size: 1.5rem;
            font-weight: bold;
            color: #1f2937;
        }

        .logo-text .tagline {
            font-size: 0.8rem;
            color: #dc2626;
            font-style: italic;
        }

        .nav-links {
            display: none;
            gap: 2rem;
            align-items: center;
        }

        @media (min-width: 768px) {
            .nav-links {
                display: flex;
            }
        }

        .nav-link {
            color: #374151;
            font-weight: 500;
            background: none;
            border: none;
            cursor: pointer;
            font-size: 1rem;
            transition: color 0.3s;
            padding: 0.5rem 1rem;
            border-radius: 6px;
        }

        .nav-link:hover {
            color: #1d4ed8;
            background-color: #f3f4f6;
        }

        .nav-link.active {
            color: #1d4ed8;
            background-color: #dbeafe;
            font-weight: 600;
        }

        .nav-actions {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .cart-button {
            position: relative;
            background: none;
            border: none;
            cursor: pointer;
            font-size: 1.5rem;
            padding: 0.5rem;
            border-radius: 6px;
            transition: background-color 0.3s;
        }

        .cart-button:hover {
            background-color: #f3f4f6;
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: #dc2626;
            color: white;
            font-size: 0.8rem;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .user-section {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .mobile-menu-button {
            background: none;
            border: none;
            cursor: pointer;
            font-size: 1.5rem;
            padding: 0.5rem;
            border-radius: 6px;
            transition: background-color 0.3s;
        }

        .mobile-menu-button:hover {
            background-color: #f3f4f6;
        }

        @media (min-width: 768px) {
            .mobile-menu-button {
                display: none;
            }
        }

        .mobile-menu {
            background-color: white;
            border-top: 1px solid #e5e7eb;
            padding: 1rem;
        }

        .mobile-menu-link {
            display: block;
            width: 100%;
            text-align: left;
            color: #374151;
            background: none;
            border: none;
            cursor: pointer;
            padding: 0.75rem 1rem;
            font-size: 1rem;
            border-radius: 6px;
            transition: background-color 0.3s;
        }

        .mobile-menu-link:hover {
            background-color: #f3f4f6;
        }

        .mobile-menu-link.active {
            color: #1d4ed8;
            background-color: #dbeafe;
            font-weight: 600;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #1d4ed8, #1e40af);
            color: white;
            padding: 6rem 1rem;
            text-align: center;
        }

        .hero h1 {
            font-size: 3rem;
            font-weight: bold;
            margin-bottom: 1rem;
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
        }

        .hero-tagline {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            color: #fecaca;
            font-style: italic;
            font-weight: 600;
        }

        .hero-subtitle {
            font-size: 1.25rem;
            margin-bottom: 2rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 0.75rem 2rem;
            border-radius: 8px;
            font-weight: bold;
            border: none;
            cursor: pointer;
            font-size: 1rem;
            transition: all 0.3s;
        }

        .btn-primary {
            background-color: #dc2626;
            color: white;
        }

        .btn-primary:hover {
            background-color: #b91c1c;
            transform: translateY(-2px);
        }

        .btn-secondary {
            background-color: white;
            color: #1d4ed8;
        }

        .btn-secondary:hover {
            background-color: #f3f4f6;
            transform: translateY(-2px);
        }

        .btn-success {
            background-color: #059669;
            color: white;
        }

        .btn-success:hover {
            background-color: #047857;
        }

        .btn-warning {
            background-color: #d97706;
            color: white;
        }

        .btn-warning:hover {
            background-color: #b45309;
        }

        .btn-danger {
            background-color: #dc2626;
            color: white;
        }

        .btn-danger:hover {
            background-color: #b91c1c;
        }

        /* Quick Admin Panel */
        .quick-admin {
            background: linear-gradient(135deg, #1d4ed8, #1e40af);
            color: white;
            padding: 1rem;
            margin-bottom: 2rem;
            border-radius: 8px;
        }

        .quick-admin-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .quick-admin-btn {
            background: rgba(255,255,255,0.2);
            color: white;
            border: 1px solid rgba(255,255,255,0.3);
            padding: 0.5rem 1rem;
            border-radius: 6px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .quick-admin-btn:hover {
            background: rgba(255,255,255,0.3);
            transform: translateY(-2px);
        }

        /* Simple Add Form */
        .simple-add-form {
            background: white;
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            margin-bottom: 2rem;
            max-width: 500px;
            margin-left: auto;
            margin-right: auto;
        }

        .simple-form-group {
            margin-bottom: 1rem;
        }

        .simple-form-input {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid #d1d5db;
            border-radius: 6px;
            font-size: 1rem;
        }

        .simple-form-input:focus {
            outline: none;
            border-color: #1d4ed8;
            box-shadow: 0 0 0 3px rgba(29, 78, 216, 0.1);
        }

        .simple-form-actions {
            display: flex;
            gap: 1rem;
            justify-content: center;
        }

        /* Delete Confirmation */
        .delete-confirm {
            background: #fee2e2;
            border: 1px solid #fecaca;
            padding: 1rem;
            border-radius: 6px;
            margin: 1rem 0;
            text-align: center;
        }

        /* Features Grid */
        .features {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 1rem;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }

        .feature-card {
            text-align: center;
            padding: 2rem;
            border: 2px solid;
            border-radius: 8px;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }

        .feature-card.blue {
            border-color: #1d4ed8;
        }

        .feature-card.red {
            border-color: #dc2626;
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .feature-title {
            font-size: 1.25rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
            color: #1f2937;
        }

        .feature-desc {
            color: #6b7280;
        }

        /* Featured Books */
        .featured-books {
            background: linear-gradient(to right, #dbeafe, #fecaca);
            padding: 3rem 1rem;
            border-radius: 12px;
        }

        .section-title {
            font-size: 2rem;
            font-weight: bold;
            text-align: center;
            margin-bottom: 2rem;
            color: #1f2937;
        }

        .books-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.5rem;
        }

        .book-card {
            background-color: white;
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            position: relative;
        }

        .book-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
        }

        .book-icon {
            font-size: 4rem;
            text-align: center;
            margin-bottom: 1rem;
        }

        .book-title {
            font-weight: bold;
            font-size: 1.125rem;
            margin-bottom: 0.5rem;
            color: #1f2937;
        }

        .book-desc {
            color: #6b7280;
            font-size: 0.875rem;
            margin-bottom: 1rem;
        }

        .book-price {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .price {
            font-size: 1.5rem;
            font-weight: bold;
            color: #1d4ed8;
        }

        .currency-selector {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 1rem;
            justify-content: center;
        }

        .currency-flag {
            font-size: 1.2rem;
        }

        /* Store Page */
        .store-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem 1rem;
        }

        .page-title {
            font-size: 2.5rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
            color: #1f2937;
            text-align: center;
        }

        .page-subtitle {
            color: #6b7280;
            margin-bottom: 2rem;
            text-align: center;
        }

        .search-container {
            position: relative;
            margin-bottom: 2rem;
            max-width: 500px;
            margin-left: auto;
            margin-right: auto;
        }

        .search-icon {
            position: absolute;
            left: 12px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 1.2rem;
            color: #6b7280;
        }

        .search-input {
            width: 100%;
            padding: 12px 12px 12px 40px;
            border: 2px solid #d1d5db;
            border-radius: 8px;
            font-size: 1rem;
            outline: none;
            transition: border-color 0.3s;
        }

        .search-input:focus {
            border-color: #1d4ed8;
        }

        /* Modal */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: rgba(0,0,0,0.5);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            padding: 1rem;
        }

        .modal {
            background-color: white;
            padding: 2rem;
            border-radius: 12px;
            width: 90%;
            max-width: 450px;
            position: relative;
            max-height: 80vh;
            overflow: auto;
            box-shadow: 0 20px 25px -5px rgba(0,0,0,0.1);
        }

        .modal-close {
            position: absolute;
            top: 1rem;
            right: 1rem;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: #6b7280;
            padding: 0.25rem;
            border-radius: 4px;
            transition: background-color 0.3s;
        }

        .modal-close:hover {
            background-color: #f3f4f6;
        }

        .modal-title {
            font-size: 1.5rem;
            font-weight: bold;
            margin-bottom: 1.5rem;
            text-align: center;
            color: #1f2937;
        }

        .error-message {
            background-color: #fee2e2;
            border: 1px solid #ef4444;
            color: #dc2626;
            padding: 0.75rem;
            border-radius: 6px;
            margin-bottom: 1rem;
            text-align: center;
        }

        .success-message {
            background-color: #d1fae5;
            border: 1px solid #10b981;
            color: #059669;
            padding: 0.75rem;
            border-radius: 6px;
            margin-bottom: 1rem;
            text-align: center;
        }

        .form-footer {
            text-align: center;
            margin-top: 1.5rem;
            padding-top: 1rem;
            border-top: 1px solid #e5e7eb;
        }

        .form-link {
            background: none;
            border: none;
            color: #1d4ed8;
            cursor: pointer;
            text-decoration: underline;
            font-size: 0.9rem;
        }

        .form-link:hover {
            color: #1e40af;
        }

        /* Cart */
        .cart-container {
            max-width: 800px;
            margin: 0 auto;
            padding: 2rem 1rem;
        }

        .cart-empty {
            text-align: center;
            padding: 4rem;
        }

        .cart-empty-icon {
            font-size: 4rem;
            margin-bottom: 1rem;
        }

        .cart-items {
            display: flex;
            flex-direction: column;
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: white;
            padding: 1rem;
            border-radius: 8px;
            border: 2px solid #e5e7eb;
        }

        .cart-item-info {
            display: flex;
            align-items: center;
        }

        .cart-item-icon {
            font-size: 2.5rem;
            margin-right: 1rem;
        }

        .cart-item-details h3 {
            font-weight: bold;
            color: #1f2937;
        }

        .cart-item-details p {
            font-size: 0.875rem;
            color: #6b7280;
        }

        .cart-item-actions {
            display: flex;
            align-items: center;
            gap: 1.5rem;
        }

        .cart-total {
            background: linear-gradient(to right, #dbeafe, #fecaca);
            padding: 1.5rem;
            border-radius: 8px;
        }

        .total-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
        }

        .total-label {
            font-size: 1.5rem;
            font-weight: bold;
            color: #1f2937;
        }

        .total-amount {
            font-size: 2rem;
            font-weight: bold;
            color: #1d4ed8;
        }

        .checkout-btn {
            width: 100%;
            background-color: #dc2626;
            color: white;
            font-weight: bold;
            padding: 1rem;
            border-radius: 8px;
            border: none;
            cursor: pointer;
            font-size: 1.125rem;
            transition: background-color 0.3s;
        }

        .checkout-btn:hover:not(:disabled) {
            background-color: #b91c1c;
        }

        .checkout-btn:disabled {
            background-color: #9ca3af;
            cursor: not-allowed;
        }

        .secure-text {
            text-align: center;
            font-size: 0.875rem;
            color: #6b7280;
            margin-top: 0.5rem;
        }

        /* Footer */
        footer {
            background: linear-gradient(135deg, #1e40af, #1d4ed8);
            color: white;
            padding: 3rem 1rem;
            margin-top: auto;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            text-align: center;
        }

        .footer-title {
            font-size: 1.5rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
        }

        .footer-tagline {
            color: #fecaca;
            font-style: italic;
            margin-bottom: 1rem;
        }

        .footer-copyright {
            font-size: 0.875rem;
            opacity: 0.8;
        }

        /* Utility Classes */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 1rem;
        }

        .text-center {
            text-align: center;
        }

        .hidden {
            display: none;
        }

        .admin-badge {
            background: #dc2626;
            color: white;
            padding: 0.25rem 0.5rem;
            border-radius: 4px;
            font-size: 0.75rem;
            margin-left: 0.5rem;
        }

        .login-tabs {
            display: flex;
            border-bottom: 1px solid #e5e7eb;
            margin-bottom: 1.5rem;
        }

        .login-tab {
            flex: 1;
            padding: 1rem;
            background: none;
            border: none;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s;
            border-bottom: 2px solid transparent;
        }

        .login-tab.active {
            color: #1d4ed8;
            border-bottom-color: #1d4ed8;
            background-color: #f8fafc;
        }

        .login-tab:hover:not(.active) {
            background-color: #f3f4f6;
        }

        @media (min-width: 768px) {
            .md\:flex {
                display: flex;
            }
        }
    </style>
</head>
<body>
    <div id="root"></div>

    <script type="text/babel">
        const { useState, useEffect } = React;

        // Currency conversion rates (simplified)
        const exchangeRates = {
            USD: 1,
            EUR: 0.85,
            GBP: 0.73,
            NGN: 410,
            CAD: 1.25,
            AUD: 1.35,
            JPY: 110,
            ZAR: 18.50
        };

        const currencySymbols = {
            USD: '$',
            EUR: '€',
            GBP: '£',
            NGN: '₦',
            CAD: 'C$',
            AUD: 'A$',
            JPY: '¥',
            ZAR: 'R'
        };

        const currencyFlags = {
            USD: '🇺🇸',
            EUR: '🇪🇺',
            GBP: '🇬🇧',
            NGN: '🇳🇬',
            CAD: '🇨🇦',
            AUD: '🇦🇺',
            JPY: '🇯🇵',
            ZAR: '🇿🇦'
        };

        // Mock backend data
        const mockBackend = {
            users: [
                { id: 1, name: 'John Doe', email: 'john@example.com', password: 'password123', role: 'user' },
                { id: 2, name: 'Admin', email: 'admin', password: 'admin', role: 'admin' }
            ],
            ebooks: [
                { 
                    id: 1, 
                    title: "Walking in Divine Purpose", 
                    price: 19.99, 
                    category: "Ministry", 
                    image: "📖", 
                    description: "Discover your calling and walk in your God-given destiny.",
                    author: "Dr. Michael Johnson",
                    isFeatured: true
                },
                { 
                    id: 2, 
                    title: "Prophetic Insights Vol 1", 
                    price: 24.99, 
                    category: "Prophecy", 
                    image: "✨", 
                    description: "Unlock the mysteries of prophetic revelation.",
                    author: "Sarah Williams",
                    isFeatured: true
                }
            ],
            workshops: [
                { 
                    id: 1, 
                    title: "Prophetic Activation Workshop", 
                    date: "Dec 5, 2025", 
                    price: 49.99,
                    description: "Learn to hear God's voice and operate in prophetic gifts.",
                    instructor: "Sarah Williams",
                    duration: "3 hours"
                }
            ]
        };

        function EbookStore() {
            const [cart, setCart] = useState([]);
            const [currentPage, setCurrentPage] = useState('home');
            const [mobileMenuOpen, setMobileMenuOpen] = useState(false);
            const [user, setUser] = useState(null);
            const [loginModalOpen, setLoginModalOpen] = useState(false);
            const [isLogin, setIsLogin] = useState(true);
            const [loading, setLoading] = useState(false);
            const [searchQuery, setSearchQuery] = useState('');
            const [currency, setCurrency] = useState('USD');
            const [paymentModalOpen, setPaymentModalOpen] = useState(false);
            const [selectedPaymentMethod, setSelectedPaymentMethod] = useState('');
            const [ebooks, setEbooks] = useState(mockBackend.ebooks);
            const [workshops, setWorkshops] = useState(mockBackend.workshops);
            const [successMessage, setSuccessMessage] = useState('');
            const [showAddForm, setShowAddForm] = useState(false);
            const [itemToDelete, setItemToDelete] = useState(null);
            const [simpleFormData, setSimpleFormData] = useState({
                title: '',
                price: '',
                type: 'ebook'
            });

            // Load user from localStorage
            useEffect(() => {
                const savedUser = localStorage.getItem('ebookStoreUser');
                if (savedUser) {
                    setUser(JSON.parse(savedUser));
                }
            }, []);

            // Currency conversion function
            const convertPrice = (price) => {
                return (price * exchangeRates[currency]).toFixed(2);
            };

            // SUPER SIMPLE ADMIN LOGIN
            const quickAdminLogin = () => {
                const adminUser = { id: 2, name: 'Admin', email: 'admin', role: 'admin' };
                setUser(adminUser);
                localStorage.setItem('ebookStoreUser', JSON.stringify(adminUser));
                setSuccessMessage('Welcome Admin! You can now manage the store.');
                setTimeout(() => setSuccessMessage(''), 3000);
            };

            const handleLogin = async (e) => {
                if (e) e.preventDefault();
                setLoading(true);

                const user = mockBackend.users.find(u => 
                    u.email === e.target.email.value && u.password === e.target.password.value
                );

                setTimeout(() => {
                    if (user) {
                        const { password, ...userWithoutPassword } = user;
                        setUser(userWithoutPassword);
                        localStorage.setItem('ebookStoreUser', JSON.stringify(userWithoutPassword));
                        setLoginModalOpen(false);
                        setSuccessMessage(`Welcome ${user.name}!`);
                        setTimeout(() => setSuccessMessage(''), 3000);
                    } else {
                        setSuccessMessage('Invalid login. Try email: "admin" & password: "admin" for admin access.');
                        setTimeout(() => setSuccessMessage(''), 5000);
                    }
                    setLoading(false);
                }, 500);
            };

            const handleLogout = () => {
                setUser(null);
                localStorage.removeItem('ebookStoreUser');
                setCart([]);
                setSuccessMessage('You have been logged out.');
                setTimeout(() => setSuccessMessage(''), 3000);
            };

            const addToCart = (product) => {
                setCart([...cart, { ...product, cartId: Date.now() }]);
                setSuccessMessage(`${product.title} added to cart!`);
                setTimeout(() => setSuccessMessage(''), 2000);
            };

            const removeFromCart = (cartId) => {
                const item = cart.find(item => item.cartId === cartId);
                setCart(cart.filter(item => item.cartId !== cartId));
                setSuccessMessage(`${item.title} removed from cart.`);
                setTimeout(() => setSuccessMessage(''), 2000);
            };

            const getTotal = () => {
                return cart.reduce((sum, item) => sum + item.price, 0).toFixed(2);
            };

            const handleCheckout = () => {
                if (!user) {
                    setLoginModalOpen(true);
                    return;
                }
                setPaymentModalOpen(true);
            };

            const processPayment = () => {
                setLoading(true);
                setTimeout(() => {
                    setSuccessMessage('Payment successful! Thank you for your order!');
                    setCart([]);
                    setPaymentModalOpen(false);
                    setLoading(false);
                    setTimeout(() => setSuccessMessage(''), 5000);
                }, 2000);
            };

            // SUPER SIMPLE ADD ITEM FUNCTION
            const quickAddItem = () => {
                if (!simpleFormData.title || !simpleFormData.price) {
                    setSuccessMessage('Please enter both title and price');
                    setTimeout(() => setSuccessMessage(''), 3000);
                    return;
                }

                const newItem = {
                    id: Date.now(),
                    title: simpleFormData.title,
                    price: parseFloat(simpleFormData.price),
                    category: 'Ministry',
                    image: simpleFormData.type === 'ebook' ? '📖' : '🎓',
                    description: 'New item added by admin',
                    author: 'Admin',
                    isFeatured: false
                };

                if (simpleFormData.type === 'ebook') {
                    setEbooks([...ebooks, newItem]);
                    setSuccessMessage('Ebook added successfully!');
                } else {
                    setWorkshops([...workshops, { ...newItem, date: 'Soon', duration: '2 hours', instructor: 'Admin' }]);
                    setSuccessMessage('Workshop added successfully!');
                }

                setSimpleFormData({ title: '', price: '', type: 'ebook' });
                setShowAddForm(false);
                setTimeout(() => setSuccessMessage(''), 3000);
            };

            // SIMPLE DELETE FUNCTION
            const quickDeleteItem = (id, type) => {
                if (type === 'ebook') {
                    setEbooks(ebooks.filter(ebook => ebook.id !== id));
                    setSuccessMessage('Item deleted successfully!');
                } else {
                    setWorkshops(workshops.filter(workshop => workshop.id !== id));
                    setSuccessMessage('Item deleted successfully!');
                }
                setItemToDelete(null);
                setTimeout(() => setSuccessMessage(''), 3000);
            };

            const filteredEbooks = ebooks.filter(ebook =>
                ebook.title.toLowerCase().includes(searchQuery.toLowerCase()) ||
                ebook.author.toLowerCase().includes(searchQuery.toLowerCase()) ||
                ebook.description.toLowerCase().includes(searchQuery.toLowerCase())
            );

            const featuredEbooks = ebooks.filter(ebook => ebook.isFeatured);

            // Currency Selector Component
            const CurrencySelector = () => {
                return React.createElement('div', { className: 'currency-selector' },
                    React.createElement('span', { style: {fontSize: '0.9rem', fontWeight: '500'} }, 'Currency:'),
                    React.createElement('select', {
                        value: currency,
                        onChange: (e) => setCurrency(e.target.value),
                        style: { 
                            padding: '0.4rem', 
                            border: '1px solid #d1d5db', 
                            borderRadius: '4px',
                            fontSize: '0.9rem'
                        }
                    },
                        Object.entries(currencyFlags).map(([code, flag]) =>
                            React.createElement('option', { key: code, value: code },
                                `${flag} ${code}`
                            )
                        )
                    )
                );
            };

            // Quick Admin Panel Component
            const QuickAdminPanel = () => {
                if (!user || user.role !== 'admin') return null;

                return React.createElement('div', { className: 'quick-admin' },
                    React.createElement('h3', { style: {textAlign: 'center', marginBottom: '1rem', color: 'white'} }, 'Admin Controls'),
                    React.createElement('div', { className: 'quick-admin-buttons' },
                        React.createElement('button', {
                            className: 'quick-admin-btn',
                            onClick: () => setShowAddForm(!showAddForm)
                        }, showAddForm ? 'Cancel Add' : '➕ Add Item'),
                        
                        React.createElement('button', {
                            className: 'quick-admin-btn',
                            onClick: () => {
                                setEbooks(mockBackend.ebooks);
                                setWorkshops(mockBackend.workshops);
                                setSuccessMessage('Store reset to original items!');
                                setTimeout(() => setSuccessMessage(''), 3000);
                            }
                        }, '🔄 Reset Store'),
                        
                        React.createElement('button', {
                            className: 'quick-admin-btn',
                            onClick: handleLogout
                        }, '🚪 Logout')
                    ),

                    showAddForm && React.createElement('div', { className: 'simple-add-form' },
                        React.createElement('h4', { style: {textAlign: 'center', marginBottom: '1rem', color: '#1f2937'} }, 'Add New Item'),
                        React.createElement('div', { className: 'simple-form-group' },
                            React.createElement('select', {
                                className: 'simple-form-input',
                                value: simpleFormData.type,
                                onChange: (e) => setSimpleFormData({...simpleFormData, type: e.target.value})
                            },
                                React.createElement('option', { value: 'ebook' }, 'Ebook'),
                                React.createElement('option', { value: 'workshop' }, 'Workshop')
                            )
                        ),
                        React.createElement('div', { className: 'simple-form-group' },
                            React.createElement('input', {
                                type: 'text',
                                className: 'simple-form-input',
                                placeholder: 'Item Title',
                                value: simpleFormData.title,
                                onChange: (e) => setSimpleFormData({...simpleFormData, title: e.target.value})
                            })
                        ),
                        React.createElement('div', { className: 'simple-form-group' },
                            React.createElement('input', {
                                type: 'number',
                                className: 'simple-form-input',
                                placeholder: 'Price (USD)',
                                value: simpleFormData.price,
                                onChange: (e) => setSimpleFormData({...simpleFormData, price: e.target.value})
                            })
                        ),
                        React.createElement('div', { className: 'simple-form-actions' },
                            React.createElement('button', {
                                className: 'btn btn-success',
                                onClick: quickAddItem
                            }, 'Add Item'),
                            React.createElement('button', {
                                className: 'btn btn-secondary',
                                onClick: () => setShowAddForm(false)
                            }, 'Cancel')
                        )
                    )
                );
            };

            // Delete Confirmation Component
            const DeleteConfirmation = ({ item, type, onConfirm, onCancel }) => {
                if (!item) return null;

                return React.createElement('div', { className: 'delete-confirm' },
                    React.createElement('p', { style: {fontWeight: 'bold', marginBottom: '0.5rem'} }, 
                        `Delete "${item.title}"?`
                    ),
                    React.createElement('p', { style: {marginBottom: '1rem', fontSize: '0.9rem', color: '#6b7280'} }, 
                        'This action cannot be undone.'
                    ),
                    React.createElement('div', { style: {display: 'flex', gap: '1rem', justifyContent: 'center'} },
                        React.createElement('button', {
                            className: 'btn btn-danger',
                            onClick: () => onConfirm(item.id, type)
                        }, 'Yes, Delete'),
                        React.createElement('button', {
                            className: 'btn btn-secondary',
                            onClick: onCancel
                        }, 'Cancel')
                    )
                );
            };

            // Navigation Component
            const NavBar = () => {
                const isActive = (page) => currentPage === page;

                return React.createElement('nav', null,
                    React.createElement('div', { className: 'nav-container' },
                        React.createElement('div', { className: 'nav-content' },
                            React.createElement('div', {
                                className: 'logo',
                                onClick: () => setCurrentPage('home')
                            },
                                React.createElement('div', { className: 'logo-icon' }, '📚'),
                                React.createElement('div', { className: 'logo-text' },
                                    React.createElement('h1', null, 'The Definitive Word'),
                                    React.createElement('div', { className: 'tagline' }, 'Christian Ebook Store')
                                )
                            ),

                            React.createElement('div', { className: 'nav-links' },
                                React.createElement('button', {
                                    className: `nav-link ${isActive('home') ? 'active' : ''}`,
                                    onClick: () => setCurrentPage('home')
                                }, 'Home'),
                                React.createElement('button', {
                                    className: `nav-link ${isActive('store') ? 'active' : ''}`,
                                    onClick: () => setCurrentPage('store')
                                }, 'Ebooks'),
                                React.createElement('button', {
                                    className: `nav-link ${isActive('workshops') ? 'active' : ''}`,
                                    onClick: () => setCurrentPage('workshops')
                                }, 'Workshops'),
                                React.createElement('button', {
                                    className: `nav-link ${isActive('cart') ? 'active' : ''}`,
                                    onClick: () => setCurrentPage('cart')
                                }, `Cart (${cart.length})`)
                            ),

                            React.createElement('div', { className: 'nav-actions' },
                                React.createElement(CurrencySelector),
                                
                                React.createElement('button', {
                                    className: 'cart-button',
                                    onClick: () => setCurrentPage('cart')
                                },
                                    React.createElement('span', null, '🛒'),
                                    cart.length > 0 && React.createElement('span', { className: 'cart-count' }, cart.length)
                                ),

                                React.createElement('div', { className: 'user-section' },
                                    user ? React.createElement('div', { style: {display: 'flex', alignItems: 'center', gap: '0.5rem'} },
                                        React.createElement('span', { style: {fontSize: '0.9rem'} }, user.name),
                                        user.role === 'admin' && React.createElement('span', { className: 'admin-badge' }, 'Admin'),
                                        React.createElement('button', {
                                            className: 'nav-link',
                                            onClick: handleLogout
                                        }, 'Logout')
                                    ) : React.createElement('button', {
                                        className: 'nav-link',
                                        onClick: () => setLoginModalOpen(true)
                                    }, 'Login')
                                ),

                                React.createElement('button', {
                                    className: 'mobile-menu-button',
                                    onClick: () => setMobileMenuOpen(!mobileMenuOpen)
                                }, '☰')
                            )
                        ),

                        mobileMenuOpen && React.createElement('div', { className: 'mobile-menu' },
                            React.createElement('button', {
                                className: `mobile-menu-link ${isActive('home') ? 'active' : ''}`,
                                onClick: () => { setCurrentPage('home'); setMobileMenuOpen(false); }
                            }, 'Home'),
                            React.createElement('button', {
                                className: `mobile-menu-link ${isActive('store') ? 'active' : ''}`,
                                onClick: () => { setCurrentPage('store'); setMobileMenuOpen(false); }
                            }, 'Ebooks'),
                            React.createElement('button', {
                                className: `mobile-menu-link ${isActive('workshops') ? 'active' : ''}`,
                                onClick: () => { setCurrentPage('workshops'); setMobileMenuOpen(false); }
                            }, 'Workshops'),
                            React.createElement('button', {
                                className: `mobile-menu-link ${isActive('cart') ? 'active' : ''}`,
                                onClick: () => { setCurrentPage('cart'); setMobileMenuOpen(false); }
                            }, `Cart (${cart.length})`),
                            !user && React.createElement('button', {
                                className: 'mobile-menu-link',
                                onClick: () => { setLoginModalOpen(true); setMobileMenuOpen(false); }
                            }, 'Login')
                        )
                    )
                );
            };

            // Login Modal Component
            const LoginModal = () => {
                if (!loginModalOpen) return null;

                return React.createElement('div', { className: 'modal-overlay' },
                    React.createElement('div', { className: 'modal' },
                        React.createElement('button', {
                            className: 'modal-close',
                            onClick: () => setLoginModalOpen(false)
                        }, '×'),

                        React.createElement('h2', { className: 'modal-title' }, isLogin ? 'Login' : 'Create Account'),

                        React.createElement('div', { className: 'login-tabs' },
                            React.createElement('button', {
                                className: `login-tab ${isLogin ? 'active' : ''}`,
                                onClick: () => setIsLogin(true)
                            }, 'Login'),
                            React.createElement('button', {
                                className: `login-tab ${!isLogin ? 'active' : ''}`,
                                onClick: () => setIsLogin(false)
                            }, 'Sign Up')
                        ),

                        React.createElement('form', { onSubmit: handleLogin },
                            React.createElement('div', { className: 'simple-form-group' },
                                React.createElement('input', {
                                    type: 'email',
                                    name: 'email',
                                    className: 'simple-form-input',
                                    placeholder: 'Email',
                                    required: true,
                                    defaultValue: isLogin ? 'admin' : ''
                                })
                            ),
                            React.createElement('div', { className: 'simple-form-group' },
                                React.createElement('input', {
                                    type: 'password',
                                    name: 'password',
                                    className: 'simple-form-input',
                                    placeholder: 'Password',
                                    required: true,
                                    defaultValue: isLogin ? 'admin' : ''
                                })
                            ),
                            !isLogin && React.createElement('div', { className: 'simple-form-group' },
                                React.createElement('input', {
                                    type: 'text',
                                    name: 'name',
                                    className: 'simple-form-input',
                                    placeholder: 'Full Name',
                                    required: true
                                })
                            ),

                            React.createElement('button', {
                                type: 'submit',
                                className: 'btn btn-primary',
                                style: {width: '100%', marginBottom: '1rem'},
                                disabled: loading
                            }, loading ? 'Loading...' : (isLogin ? 'Login' : 'Create Account')),

                            isLogin && React.createElement('div', { className: 'form-footer' },
                                React.createElement('p', { style: {fontSize: '0.9rem', color: '#6b7280'} },
                                    'Demo: Use ',
                                    React.createElement('button', {
                                        type: 'button',
                                        className: 'form-link',
                                        onClick: quickAdminLogin
                                    }, 'Quick Admin Login'),
                                    ' for instant admin access'
                                )
                            )
                        )
                    )
                );
            };

            // Payment Modal Component
            const PaymentModal = () => {
                if (!paymentModalOpen) return null;

                return React.createElement('div', { className: 'modal-overlay' },
                    React.createElement('div', { className: 'modal' },
                        React.createElement('button', {
                            className: 'modal-close',
                            onClick: () => setPaymentModalOpen(false)
                        }, '×'),

                        React.createElement('h2', { className: 'modal-title' }, 'Complete Your Purchase'),

                        React.createElement('div', { style: {marginBottom: '1.5rem'} },
                            React.createElement('h3', { style: {marginBottom: '1rem', color: '#1f2937'} }, 'Order Summary'),
                            cart.map(item => 
                                React.createElement('div', {
                                    key: item.cartId,
                                    style: {display: 'flex', justifyContent: 'space-between', marginBottom: '0.5rem'}
                                },
                                    React.createElement('span', null, item.title),
                                    React.createElement('span', null, `${currencySymbols[currency]}${convertPrice(item.price)}`)
                                )
                            ),
                            React.createElement('div', {
                                style: {display: 'flex', justifyContent: 'space-between', marginTop: '1rem', paddingTop: '1rem', borderTop: '1px solid #e5e7eb', fontWeight: 'bold'}
                            },
                                React.createElement('span', null, 'Total:'),
                                React.createElement('span', null, `${currencySymbols[currency]}${convertPrice(getTotal())}`)
                            )
                        ),

                        React.createElement('div', { className: 'simple-form-group' },
                            React.createElement('label', { style: {display: 'block', marginBottom: '0.5rem', fontWeight: '500'} }, 'Payment Method'),
                            React.createElement('select', {
                                className: 'simple-form-input',
                                value: selectedPaymentMethod,
                                onChange: (e) => setSelectedPaymentMethod(e.target.value),
                                required: true
                            },
                                React.createElement('option', { value: '' }, 'Select Payment Method'),
                                React.createElement('option', { value: 'card' }, 'Credit/Debit Card'),
                                React.createElement('option', { value: 'paypal' }, 'PayPal'),
                                React.createElement('option', { value: 'transfer' }, 'Bank Transfer')
                            )
                        ),

                        selectedPaymentMethod && React.createElement('div', { style: {marginTop: '1rem'} },
                            React.createElement('p', { style: {fontSize: '0.9rem', color: '#059669', textAlign: 'center'} },
                                'Demo: No real payment will be processed'
                            )
                        ),

                        React.createElement('button', {
                            className: 'btn btn-primary',
                            style: {width: '100%', marginTop: '1.5rem'},
                            onClick: processPayment,
                            disabled: !selectedPaymentMethod || loading
                        }, loading ? 'Processing...' : 'Complete Purchase')
                    )
                );
            };

            // Home Page Component
            const HomePage = () => {
                return React.createElement('div', { className: 'main-content' },
                    React.createElement('section', { className: 'hero' },
                        React.createElement('h1', null, 'The Definitive Word'),
                        React.createElement('div', { className: 'hero-tagline' }, 'Christian Ebook Store'),
                        React.createElement('p', { className: 'hero-subtitle' }, 'Discover transformative Christian ebooks and workshops to deepen your faith and ministry'),
                        React.createElement('div', { className: 'hero-buttons' },
                            React.createElement('button', {
                                className: 'btn btn-primary',
                                onClick: () => setCurrentPage('store')
                            }, 'Browse Ebooks'),
                            React.createElement('button', {
                                className: 'btn btn-secondary',
                                onClick: () => setCurrentPage('workshops')
                            }, 'View Workshops')
                        )
                    ),

                    React.createElement('div', { className: 'container' },
                        React.createElement(QuickAdminPanel),

                        successMessage && React.createElement('div', { className: successMessage.includes('error') ? 'error-message' : 'success-message' },
                            successMessage
                        ),

                        React.createElement('section', { className: 'features' },
                            React.createElement('h2', { className: 'section-title' }, 'Why Choose Our Store?'),
                            React.createElement('div', { className: 'features-grid' },
                                React.createElement('div', { className: 'feature-card blue' },
                                    React.createElement('div', { className: 'feature-icon' }, '🙏'),
                                    React.createElement('h3', { className: 'feature-title' }, 'Faith-Based Content'),
                                    React.createElement('p', { className: 'feature-desc' }, 'Carefully curated Christian resources for spiritual growth')
                                ),
                                React.createElement('div', { className: 'feature-card red' },
                                    React.createElement('div', { className: 'feature-icon' }, '📚'),
                                    React.createElement('h3', { className: 'feature-title' }, 'Instant Access'),
                                    React.createElement('p', { className: 'feature-desc' }, 'Download your ebooks immediately after purchase')
                                ),
                                React.createElement('div', { className: 'feature-card blue' },
                                    React.createElement('div', { className: 'feature-icon' }, '💝'),
                                    React.createElement('h3', { className: 'feature-title' }, 'Ministry Support'),
                                    React.createElement('p', { className: 'feature-desc' }, 'Proceeds support Christian ministry and outreach')
                                )
                            )
                        ),

                        React.createElement('section', { className: 'featured-books' },
                            React.createElement('h2', { className: 'section-title' }, 'Featured Ebooks'),
                            React.createElement('div', { className: 'books-grid' },
                                featuredEbooks.map(ebook =>
                                    React.createElement('div', { key: ebook.id, className: 'book-card' },
                                        React.createElement('div', { className: 'book-icon' }, ebook.image),
                                        React.createElement('h3', { className: 'book-title' }, ebook.title),
                                        React.createElement('p', { className: 'book-desc' }, ebook.description),
                                        React.createElement('p', { style: {fontSize: '0.9rem', color: '#6b7280', marginBottom: '1rem'} }, `by ${ebook.author}`),
                                        React.createElement('div', { className: 'book-price' },
                                            React.createElement('span', { className: 'price' }, 
                                                `${currencySymbols[currency]}${convertPrice(ebook.price)}`
                                            ),
                                            React.createElement('button', {
                                                className: 'btn btn-primary',
                                                onClick: () => addToCart(ebook)
                                            }, 'Add to Cart')
                                        ),
                                        user?.role === 'admin' && React.createElement('button', {
                                            className: 'btn btn-danger',
                                            style: {width: '100%', marginTop: '0.5rem', fontSize: '0.8rem', padding: '0.4rem'},
                                            onClick: () => setItemToDelete({...ebook, type: 'ebook'})
                                        }, 'Delete')
                                    )
                                )
                            )
                        )
                    )
                );
            };

            // Store Page Component
            const StorePage = () => {
                return React.createElement('div', { className: 'store-container' },
                    React.createElement(QuickAdminPanel),

                    successMessage && React.createElement('div', { className: successMessage.includes('error') ? 'error-message' : 'success-message' },
                        successMessage
                    ),

                    React.createElement('h1', { className: 'page-title' }, 'Christian Ebooks'),
                    React.createElement('p', { className: 'page-subtitle' }, 'Transformative resources for your spiritual journey'),

                    React.createElement('div', { className: 'search-container' },
                        React.createElement('span', { className: 'search-icon' }, '🔍'),
                        React.createElement('input', {
                            type: 'text',
                            className: 'search-input',
                            placeholder: 'Search ebooks by title, author, or description...',
                            value: searchQuery,
                            onChange: (e) => setSearchQuery(e.target.value)
                        })
                    ),

                    itemToDelete && React.createElement(DeleteConfirmation, {
                        item: itemToDelete,
                        type: itemToDelete.type,
                        onConfirm: quickDeleteItem,
                        onCancel: () => setItemToDelete(null)
                    }),

                    React.createElement('div', { className: 'books-grid' },
                        filteredEbooks.map(ebook =>
                            React.createElement('div', { key: ebook.id, className: 'book-card' },
                                React.createElement('div', { className: 'book-icon' }, ebook.image),
                                React.createElement('h3', { className: 'book-title' }, ebook.title),
                                React.createElement('p', { className: 'book-desc' }, ebook.description),
                                React.createElement('p', { style: {fontSize: '0.9rem', color: '#6b7280', marginBottom: '0.5rem'} }, `by ${ebook.author}`),
                                React.createElement('p', { style: {fontSize: '0.8rem', color: '#dc2626', marginBottom: '1rem'} }, ebook.category),
                                React.createElement('div', { className: 'book-price' },
                                    React.createElement('span', { className: 'price' }, 
                                        `${currencySymbols[currency]}${convertPrice(ebook.price)}`
                                    ),
                                    React.createElement('button', {
                                        className: 'btn btn-primary',
                                        onClick: () => addToCart(ebook)
                                    }, 'Add to Cart')
                                ),
                                user?.role === 'admin' && React.createElement('button', {
                                    className: 'btn btn-danger',
                                    style: {width: '100%', marginTop: '0.5rem', fontSize: '0.8rem', padding: '0.4rem'},
                                    onClick: () => setItemToDelete({...ebook, type: 'ebook'})
                                }, 'Delete')
                            )
                        )
                    ),

                    filteredEbooks.length === 0 && React.createElement('div', { className: 'text-center', style: {padding: '4rem', color: '#6b7280'} },
                        React.createElement('div', { style: {fontSize: '4rem', marginBottom: '1rem'} }, '📚'),
                        React.createElement('h3', null, 'No ebooks found'),
                        React.createElement('p', null, 'Try adjusting your search terms')
                    )
                );
            };

            // Workshops Page Component
            const WorkshopsPage = () => {
                return React.createElement('div', { className: 'store-container' },
                    React.createElement(QuickAdminPanel),

                    successMessage && React.createElement('div', { className: successMessage.includes('error') ? 'error-message' : 'success-message' },
                        successMessage
                    ),

                    React.createElement('h1', { className: 'page-title' }, 'Christian Workshops'),
                    React.createElement('p', { className: 'page-subtitle' }, 'Live and recorded workshops for deeper learning'),

                    itemToDelete && React.createElement(DeleteConfirmation, {
                        item: itemToDelete,
                        type: itemToDelete.type,
                        onConfirm: quickDeleteItem,
                        onCancel: () => setItemToDelete(null)
                    }),

                    React.createElement('div', { className: 'books-grid' },
                        workshops.map(workshop =>
                            React.createElement('div', { key: workshop.id, className: 'book-card' },
                                React.createElement('div', { className: 'book-icon' }, '🎓'),
                                React.createElement('h3', { className: 'book-title' }, workshop.title),
                                React.createElement('p', { className: 'book-desc' }, workshop.description),
                                React.createElement('div', { style: {marginBottom: '1rem'} },
                                    React.createElement('p', { style: {fontSize: '0.9rem', color: '#6b7280', marginBottom: '0.25rem'} }, 
                                        `Instructor: ${workshop.instructor}`
                                    ),
                                    React.createElement('p', { style: {fontSize: '0.9rem', color: '#6b7280', marginBottom: '0.25rem'} }, 
                                        `Date: ${workshop.date}`
                                    ),
                                    React.createElement('p', { style: {fontSize: '0.9rem', color: '#6b7280'} }, 
                                        `Duration: ${workshop.duration}`
                                    )
                                ),
                                React.createElement('div', { className: 'book-price' },
                                    React.createElement('span', { className: 'price' }, 
                                        `${currencySymbols[currency]}${convertPrice(workshop.price)}`
                                    ),
                                    React.createElement('button', {
                                        className: 'btn btn-primary',
                                        onClick: () => addToCart(workshop)
                                    }, 'Add to Cart')
                                ),
                                user?.role === 'admin' && React.createElement('button', {
                                    className: 'btn btn-danger',
                                    style: {width: '100%', marginTop: '0.5rem', fontSize: '0.8rem', padding: '0.4rem'},
                                    onClick: () => setItemToDelete({...workshop, type: 'workshop'})
                                }, 'Delete')
                            )
                        )
                    ),

                    workshops.length === 0 && React.createElement('div', { className: 'text-center', style: {padding: '4rem', color: '#6b7280'} },
                        React.createElement('div', { style: {fontSize: '4rem', marginBottom: '1rem'} }, '🎓'),
                        React.createElement('h3', null, 'No workshops available'),
                        React.createElement('p', null, 'Check back later for new workshops')
                    )
                );
            };

            // Cart Page Component
            const CartPage = () => {
                if (cart.length === 0) {
                    return React.createElement('div', { className: 'cart-container' },
                        React.createElement('div', { className: 'cart-empty' },
                            React.createElement('div', { className: 'cart-empty-icon' }, '🛒'),
                            React.createElement('h2', null, 'Your cart is empty'),
                            React.createElement('p', { style: {color: '#6b7280', marginBottom: '2rem'} }, 'Browse our ebooks and workshops to add items to your cart'),
                            React.createElement('div', { style: {display: 'flex', gap: '1rem', justifyContent: 'center', flexWrap: 'wrap'} },
                                React.createElement('button', {
                                    className: 'btn btn-primary',
                                    onClick: () => setCurrentPage('store')
                                }, 'Browse Ebooks'),
                                React.createElement('button', {
                                    className: 'btn btn-secondary',
                                    onClick: () => setCurrentPage('workshops')
                                }, 'View Workshops')
                            )
                        )
                    );
                }

                return React.createElement('div', { className: 'cart-container' },
                    React.createElement('h1', { className: 'page-title' }, 'Your Cart'),
                    
                    React.createElement('div', { className: 'cart-items' },
                        cart.map(item =>
                            React.createElement('div', { key: item.cartId, className: 'cart-item' },
                                React.createElement('div', { className: 'cart-item-info' },
                                    React.createElement('div', { className: 'cart-item-icon' }, item.image || '📖'),
                                    React.createElement('div', { className: 'cart-item-details' },
                                        React.createElement('h3', null, item.title),
                                        React.createElement('p', null, item.description || `by ${item.author}`)
                                    )
                                ),
                                React.createElement('div', { className: 'cart-item-actions' },
                                    React.createElement('span', { className: 'price' }, 
                                        `${currencySymbols[currency]}${convertPrice(item.price)}`
                                    ),
                                    React.createElement('button', {
                                        className: 'btn btn-danger',
                                        onClick: () => removeFromCart(item.cartId)
                                    }, 'Remove')
                                )
                            )
                        )
                    ),

                    React.createElement('div', { className: 'cart-total' },
                        React.createElement('div', { className: 'total-row' },
                            React.createElement('span', { className: 'total-label' }, 'Total:'),
                            React.createElement('span', { className: 'total-amount' }, 
                                `${currencySymbols[currency]}${convertPrice(getTotal())}`
                            )
                        ),
                        React.createElement('button', {
                            className: 'checkout-btn',
                            onClick: handleCheckout
                        }, 'Proceed to Checkout'),
                        React.createElement('p', { className: 'secure-text' }, '🔒 Secure checkout • Your payment is safe with us')
                    )
                );
            };

            // Main App Render
            return React.createElement('div', { className: 'app' },
                React.createElement(NavBar),
                
                currentPage === 'home' && React.createElement(HomePage),
                currentPage === 'store' && React.createElement(StorePage),
                currentPage === 'workshops' && React.createElement(WorkshopsPage),
                currentPage === 'cart' && React.createElement(CartPage),

                React.createElement(LoginModal),
                React.createElement(PaymentModal),

                React.createElement('footer', null,
                    React.createElement('div', { className: 'footer-content' },
                        React.createElement('h2', { className: 'footer-title' }, 'The Definitive Word'),
                        React.createElement('p', { className: 'footer-tagline' }, 'Equipping believers through transformative resources'),
                        React.createElement('p', { className: 'footer-copyright' }, 
                            `© ${new Date().getFullYear()} The Definitive Word. All rights reserved.`
                        )
                    )
                )
            );
        }

        // Render the app
        ReactDOM.render(React.createElement(EbookStore), document.getElementById('root'));
    </script>
</body>
</html>
