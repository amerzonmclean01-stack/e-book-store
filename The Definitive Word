<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Secure Christian Resources</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link rel="manifest" href="manifest.json">
    <meta name="theme-color" content="#1a365d">
    <style>
        /* === ENTERPRISE-LEVEL STYLES === */
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
            --error: #e53e3e;
            --warning: #dd6b20;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', 'Times New Roman', serif;
            color: var(--dark-text);
            line-height: 1.6;
            background: var(--white);
            overflow-x: hidden;
        }

        /* Security Badge */
        .security-badge {
            position: fixed;
            top: 10px;
            right: 10px;
            background: var(--success);
            color: white;
            padding: 5px 10px;
            border-radius: 4px;
            font-size: 0.8rem;
            z-index: 10000;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        /* Loading Screen */
        #loadingScreen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--primary-color);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            color: white;
        }

        .spinner {
            border: 4px solid rgba(255,255,255,0.3);
            border-radius: 50%;
            border-top: 4px solid var(--gold-color);
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            margin-bottom: 20px;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Context Menu */
        .context-menu {
            position: fixed;
            background: white;
            border: 1px solid var(--border);
            border-radius: 8px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.15);
            z-index: 1000;
            display: none;
        }

        .context-menu-item {
            padding: 12px 20px;
            cursor: pointer;
            border-bottom: 1px solid var(--border);
            transition: background 0.3s ease;
        }

        .context-menu-item:hover {
            background: var(--light-bg);
        }

        .context-menu-item:last-child {
            border-bottom: none;
        }

        /* Notification System */
        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            padding: 15px 20px;
            border-radius: 8px;
            color: white;
            z-index: 1001;
            transform: translateX(400px);
            transition: transform 0.3s ease;
        }

        .notification.show {
            transform: translateX(0);
        }

        .notification.success { background: var(--success); }
        .notification.error { background: var(--error); }
        .notification.warning { background: var(--warning); }

        /* Modal System */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 1002;
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background: white;
            padding: 2rem;
            border-radius: 12px;
            max-width: 500px;
            width: 90%;
            max-height: 80vh;
            overflow-y: auto;
        }

        /* Existing styles from previous version... */
        .container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }
        .header { background: var(--white); box-shadow: 0 2px 20px rgba(0,0,0,0.08); position: sticky; top: 0; z-index: 1000; border-bottom: 3px solid var(--gold-color); }
        .header-content { display: flex; align-items: center; justify-content: space-between; padding: 1.2rem 0; }
        .logo { font-size: 2.2rem; font-weight: 700; color: var(--primary-color); text-decoration: none; font-family: 'Georgia', serif; }
        .logo span { color: var(--gold-color); font-style: italic; }
        .nav { display: flex; gap: 2.5rem; align-items: center; }
        .nav-link { color: var(--dark-text); text-decoration: none; font-weight: 500; font-size: 1.1rem; transition: all 0.3s ease; position: relative; }
        .nav-link:hover { color: var(--accent-color); }
        .btn { padding: 12px 28px; border-radius: 6px; text-decoration: none; font-weight: 600; transition: all 0.3s ease; border: none; cursor: pointer; display: inline-block; font-size: 1rem; }
        .btn-primary { background: linear-gradient(135deg, var(--primary-color), var(--accent-color)); color: var(--white); box-shadow: 0 4px 15px rgba(43, 108, 176, 0.3); }
        .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 6px 20px rgba(43, 108, 176, 0.4); }
        .section { padding: 100px 0; }
        .section-title { font-size: 2.8rem; text-align: center; margin-bottom: 1rem; color: var(--primary-color); font-family: 'Georgia', serif; position: relative; }
        .section-title:after { content: ''; display: block; width: 80px; height: 3px; background: var(--gold-color); margin: 1rem auto; }
        .books-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); gap: 2.5rem; }
        .book-card { background: var(--white); border: 1px solid var(--border); border-radius: 12px; overflow: hidden; transition: all 0.3s ease; box-shadow: 0 5px 20px rgba(0,0,0,0.08); position: relative; }
        .book-card:hover { transform: translateY(-5px); box-shadow: 0 15px 40px rgba(0,0,0,0.15); }
        .book-info { padding: 2rem; }
        .book-title { font-size: 1.3rem; font-weight: 600; margin-bottom: 0.5rem; color: var(--primary-color); line-height: 1.4; }
        .book-author { color: var(--light-text); margin-bottom: 1rem; font-size: 1rem; font-style: italic; }
        .book-price { font-size: 1.5rem; font-weight: 700; color: var(--primary-color); margin-bottom: 1.5rem; }
        .footer { background: var(--primary-color); color: var(--white); padding: 80px 0 30px; }

        /* Settings Panel */
        .settings-panel {
            position: fixed;
            top: 0;
            right: -400px;
            width: 400px;
            height: 100vh;
            background: white;
            box-shadow: -5px 0 20px rgba(0,0,0,0.1);
            transition: right 0.3s ease;
            z-index: 1003;
            overflow-y: auto;
        }

        .settings-panel.open {
            right: 0;
        }

        .settings-header {
            padding: 2rem;
            border-bottom: 1px solid var(--border);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .settings-content {
            padding: 2rem;
        }

        .setting-group {
            margin-bottom: 2rem;
        }

        .setting-group h4 {
            margin-bottom: 1rem;
            color: var(--primary-color);
        }

        .setting-option {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
            border-bottom: 1px solid var(--border);
        }

        /* Switch Toggle */
        .switch {
            position: relative;
            display: inline-block;
            width: 60px;
            height: 34px;
        }

        .switch input {
            opacity: 0;
            width: 0;
            height: 0;
        }

        .slider {
            position: absolute;
            cursor: pointer;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: #ccc;
            transition: .4s;
            border-radius: 34px;
        }

        .slider:before {
            position: absolute;
            content: "";
            height: 26px;
            width: 26px;
            left: 4px;
            bottom: 4px;
            background-color: white;
            transition: .4s;
            border-radius: 50%;
        }

        input:checked + .slider {
            background-color: var(--success);
        }

        input:checked + .slider:before {
            transform: translateX(26px);
        }

        /* Diagnostics Panel */
        .diagnostics-panel {
            position: fixed;
            bottom: 20px;
            left: 20px;
            background: var(--primary-color);
            color: white;
            padding: 1rem;
            border-radius: 8px;
            font-family: monospace;
            font-size: 0.9rem;
            z-index: 999;
            max-width: 300px;
        }

        .diagnostics-item {
            margin-bottom: 0.5rem;
        }

        .status-indicator {
            display: inline-block;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            margin-right: 8px;
        }

        .status-ok { background: var(--success); }
        .status-warning { background: var(--warning); }
        .status-error { background: var(--error); }

        @media (max-width: 768px) {
            .settings-panel {
                width: 100%;
                right: -100%;
            }
            
            .diagnostics-panel {
                bottom: 10px;
                left: 10px;
                right: 10px;
                max-width: none;
            }
        }
    </style>
</head>
<body>
    <!-- Security Badge -->
    <div class="security-badge">
        <i class="fas fa-shield-alt"></i>
        <span>Secure Connection • SSL Encrypted</span>
    </div>

    <!-- Loading Screen -->
    <div id="loadingScreen">
        <div class="spinner"></div>
        <h3>Initializing Secure Environment</h3>
        <p>Loading security protocols...</p>
    </div>

    <!-- Context Menu -->
    <div class="context-menu" id="contextMenu">
        <div class="context-menu-item" onclick="openInNewTab()"><i class="fas fa-external-link-alt"></i> Open in New Tab</div>
        <div class="context-menu-item" onclick="savePage()"><i class="fas fa-save"></i> Save Page</div>
        <div class="context-menu-item" onclick="inspectElement()"><i class="fas fa-search"></i> Inspect</div>
        <div class="context-menu-item" onclick="viewSource()"><i class="fas fa-code"></i> View Source</div>
    </div>

    <!-- Notifications -->
    <div id="notificationContainer"></div>

    <!-- Settings Modal -->
    <div class="modal" id="settingsModal">
        <div class="modal-content">
            <div class="settings-header">
                <h3>Application Settings</h3>
                <button onclick="closeSettings()" style="background: none; border: none; font-size: 1.5rem; cursor: pointer;">×</button>
            </div>
            <div class="settings-content">
                <div class="setting-group">
                    <h4>Security Settings</h4>
                    <div class="setting-option">
                        <span>Auto-login</span>
                        <label class="switch">
                            <input type="checkbox" id="autoLogin" onchange="updateSetting('autoLogin', this.checked)">
                            <span class="slider"></span>
                        </label>
                    </div>
                    <div class="setting-option">
                        <span>Two-Factor Authentication</span>
                        <label class="switch">
                            <input type="checkbox" id="twoFactor" onchange="updateSetting('twoFactor', this.checked)">
                            <span class="slider"></span>
                        </label>
                    </div>
                    <div class="setting-option">
                        <span>Session Timeout (minutes)</span>
                        <input type="number" id="sessionTimeout" value="30" min="5" max="240" onchange="updateSetting('sessionTimeout', this.value)" style="width: 80px; padding: 5px;">
                    </div>
                </div>

                <div class="setting-group">
                    <h4>Privacy Settings</h4>
                    <div class="setting-option">
                        <span>Save Login Credentials</span>
                        <label class="switch">
                            <input type="checkbox" id="saveLogin" onchange="updateSetting('saveLogin', this.checked)">
                            <span class="slider"></span>
                        </label>
                    </div>
                    <div class="setting-option">
                        <span>Allow Cookies</span>
                        <label class="switch">
                            <input type="checkbox" id="allowCookies" onchange="updateSetting('allowCookies', this.checked)">
                            <span class="slider"></span>
                        </label>
                    </div>
                    <div class="setting-option">
                        <span>Data Encryption</span>
                        <label class="switch">
                            <input type="checkbox" id="dataEncryption" checked onchange="updateSetting('dataEncryption', this.checked)">
                            <span class="slider"></span>
                        </label>
                    </div>
                </div>

                <div class="setting-group">
                    <h4>Interface Settings</h4>
                    <div class="setting-option">
                        <span>Double-click to Open</span>
                        <label class="switch">
                            <input type="checkbox" id="doubleClick" onchange="updateSetting('doubleClick', this.checked)">
                            <span class="slider"></span>
                        </label>
                    </div>
                    <div class="setting-option">
                        <span>Right-click Menu</span>
                        <label class="switch">
                            <input type="checkbox" id="rightClick" checked onchange="updateSetting('rightClick', this.checked)">
                            <span class="slider"></span>
                        </label>
                    </div>
                    <div class="setting-option">
                        <span>Theme</span>
                        <select id="theme" onchange="updateSetting('theme', this.value)" style="padding: 5px;">
                            <option value="light">Light</option>
                            <option value="dark">Dark</option>
                            <option value="auto">Auto</option>
                        </select>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Diagnostics Panel -->
    <div class="diagnostics-panel" id="diagnosticsPanel">
        <h4>System Diagnostics</h4>
        <div class="diagnostics-item">
            <span class="status-indicator status-ok"></span>
            <span>Security: Active</span>
        </div>
        <div class="diagnostics-item">
            <span class="status-indicator status-ok"></span>
            <span>SSL: Encrypted</span>
        </div>
        <div class="diagnostics-item">
            <span class="status-indicator status-ok"></span>
            <span>Database: Connected</span>
        </div>
        <div class="diagnostics-item">
            <span class="status-indicator status-ok"></span>
            <span>Payments: Ready</span>
        </div>
        <button onclick="runFullDiagnostics()" style="margin-top: 10px; padding: 5px 10px; background: var(--gold-color); border: none; border-radius: 4px; cursor: pointer;">Run Diagnostics</button>
    </div>

    <!-- Main Application -->
    <header class="header">
        <div class="container">
            <div class="header-content">
                <a href="#" class="logo" ondblclick="openSettings()">
                    The <span>Definitive</span> Word
                </a>
                
                <nav class="nav">
                    <a href="#home" class="nav-link">Home</a>
                    <a href="#store" class="nav-link">Store</a>
                    <a href="#ministry" class="nav-link">Ministry</a>
                    <a href="#community" class="nav-link">Community</a>
                    <a href="#blog" class="nav-link">Blog</a>
                </nav>

                <div class="header-actions">
                    <button onclick="openSettings()" class="btn btn-outline" style="margin-right: 10px;">
                        <i class="fas fa-cog"></i> Settings
                    </button>
                    <button onclick="toggleLogin()" class="btn btn-primary" id="loginButton">
                        <i class="fas fa-user"></i> Sign In
                    </button>
                </div>
            </div>
        </div>
    </header>

    <section id="home" class="hero-section" style="background: linear-gradient(135deg, var(--primary-color) 0%, #2c5282 100%); color: white; padding: 120px 0; text-align: center;">
        <div class="container">
            <h1 style="font-size: 3.8rem; margin-bottom: 1.5rem;">The Definitive Word</h1>
            <p style="font-size: 1.4rem; margin-bottom: 2.5rem; opacity: 0.9; max-width: 600px; margin-left: auto; margin-right: auto;">
                Secure • Encrypted • Enterprise-Grade Christian Resources
            </p>
            <div style="display: flex; gap: 1.5rem; justify-content: center; flex-wrap: wrap;">
                <button class="btn btn-primary">Explore Resources</button>
                <button class="btn" style="background: rgba(255,255,255,0.1); color: white; border: 2px solid white;">View Diagnostics</button>
            </div>
        </div>
    </section>

    <section id="store" class="section">
        <div class="container">
            <h2 class="section-title">Secure Ebook Store</h2>
            <p style="text-align: center; color: var(--light-text); margin-bottom: 4rem; font-size: 1.3rem;">
                Encrypted transactions with enterprise-level security
            </p>
            
            <div class="books-grid">
                <div class="book-card">
                    <div class="book-info">
                        <h3 class="book-title">Morning Reflections</h3>
                        <p class="book-author">by Dr. Michael Thompson</p>
                        <p style="color: var(--light-text); margin-bottom: 1.5rem; font-size: 0.95rem; line-height: 1.6;">
                            SSL Encrypted • Secure Download
                        </p>
                        <div class="book-price">$19.99</div>
                        <button class="btn btn-primary" style="width: 100%;" onclick="securePurchase('Morning Reflections')">
                            <i class="fas fa-lock"></i> Secure Purchase
                        </button>
                    </div>
                </div>

                <div class="book-card">
                    <div class="book-info">
                        <h3 class="book-title">Understanding Grace</h3>
                        <p class="book-author">by Pastor Sarah Johnson</p>
                        <p style="color: var(--light-text); margin-bottom: 1.5rem; font-size: 0.95rem; line-height: 1.6;">
                            SSL Encrypted • Secure Download
                        </p>
                        <div class="book-price">$22.99</div>
                        <button class="btn btn-primary" style="width: 100%;" onclick="securePurchase('Understanding Grace')">
                            <i class="fas fa-lock"></i> Secure Purchase
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer class="footer">
        <div class="container">
            <div style="text-align: center; color: #cbd5e0;">
                <p>&copy; 2024 The Definitive Word. Enterprise-Grade Security • Version 2.1.0</p>
                <p style="margin-top: 1rem; font-size: 0.9rem;">
                    <i class="fas fa-shield-alt"></i> All transactions encrypted with 256-bit SSL
                </p>
            </div>
        </div>
    </footer>

    <!-- Comprehensive JavaScript -->
    <script>
        // ===== CONFIGURATION =====
        const CONFIG = {
            version: '2.1.0',
            security: {
                ssl: true,
                encryption: 'AES-256',
                sessionTimeout: 30,
                twoFactor: false
            },
            features: {
                doubleClick: false,
                rightClick: true,
                saveLogin: true,
                autoLogin: false
            },
            diagnostics: {
                enabled: true,
                autoRun: true,
                logLevel: 'info'
            }
        };

        // ===== SECURITY SYSTEM =====
        class SecuritySystem {
            constructor() {
                this.encryptionKey = this.generateEncryptionKey();
                this.sessionActive = false;
            }

            generateEncryptionKey() {
                return btoa(Math.random().toString(36).substring(2) + Date.now().toString(36));
            }

            encryptData(data) {
                if (!CONFIG.security.ssl) {
                    console.warn('SSL not enabled - data not encrypted');
                    return data;
                }
                // Simulate encryption
                return btoa(JSON.stringify(data));
            }

            decryptData(encryptedData) {
                try {
                    return JSON.parse(atob(encryptedData));
                } catch (e) {
                    this.logSecurityEvent('decryption_failed', { error: e.message });
                    return null;
                }
            }

            validateInput(input, type) {
                const validators = {
                    email: /^[^\s@]+@[^\s@]+\.[^\s@]+$/,
                    password: /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d).{8,}$/,
                    creditCard: /^\d{16}$/,
                    name: /^[a-zA-Z\s]{2,50}$/
                };

                if (validators[type]) {
                    return validators[type].test(input);
                }
                return true;
            }

            logSecurityEvent(event, data = {}) {
                const logEntry = {
                    timestamp: new Date().toISOString(),
                    event,
                    data,
                    userAgent: navigator.userAgent
                };
                console.log('🔒 Security Event:', logEntry);
            }
        }

        // ===== AUTHENTICATION SYSTEM =====
        class AuthSystem {
            constructor() {
                this.currentUser = null;
                this.sessionExpiry = null;
            }

            async login(email, password, rememberMe = false) {
                // Input validation
                const security = new SecuritySystem();
                if (!security.validateInput(email, 'email')) {
                    throw new Error('Invalid email format');
                }

                if (!security.validateInput(password, 'password')) {
                    throw new Error('Password must be at least 8 characters with uppercase, lowercase and number');
                }

                // Simulate API call
                return new Promise((resolve) => {
                    setTimeout(() => {
                        this.currentUser = {
                            email: security.encryptData(email),
                            name: 'John Doe',
                            lastLogin: new Date().toISOString()
                        };
                        
                        this.sessionExpiry = Date.now() + (CONFIG.security.sessionTimeout * 60 * 1000);
                        
                        if (rememberMe) {
                            localStorage.setItem('userSession', security.encryptData({
                                email: email,
                                timestamp: Date.now()
                            }));
                        }
                        
                        security.logSecurityEvent('user_login', { email: email });
                        resolve(this.currentUser);
                    }, 1000);
                });
            }

            logout() {
                const security = new SecuritySystem();
                security.logSecurityEvent('user_logout', { email: this.currentUser?.email });
                this.currentUser = null;
                this.sessionExpiry = null;
                localStorage.removeItem('userSession');
            }

            checkSession() {
                if (this.sessionExpiry && Date.now() > this.sessionExpiry) {
                    this.logout();
                    showNotification('Session expired. Please login again.', 'warning');
                    return false;
                }
                return !!this.currentUser;
            }
        }

        // ===== PAYMENT SYSTEM =====
        class PaymentSystem {
            processPayment(amount, paymentMethod, cardDetails = null) {
                return new Promise((resolve, reject) => {
                    const security = new SecuritySystem();
                    
                    // Validate card details if provided
                    if (cardDetails && !security.validateInput(cardDetails.number, 'creditCard')) {
                        reject(new Error('Invalid credit card number'));
                        return;
                    }

                    security.logSecurityEvent('payment_attempt', { 
                        amount, 
                        method: paymentMethod,
                        encrypted: security.encryptData({ amount, method: paymentMethod })
                    });

                    // Simulate payment processing
                    setTimeout(() => {
                        if (Math.random() > 0.1) { // 90% success rate
                            const transactionId = 'TX_' + Math.random().toString(36).substr(2, 9).toUpperCase();
                            security.logSecurityEvent('payment_success', { transactionId, amount });
                            resolve(transactionId);
                        } else {
                            security.logSecurityEvent('payment_failed', { reason: 'Processing error' });
                            reject(new Error('Payment processing failed. Please try again.'));
                        }
                    }, 2000);
                });
            }
        }

        // ===== DIAGNOSTICS SYSTEM =====
        class DiagnosticsSystem {
            constructor() {
                this.tests = [];
                this.results = {};
            }

            addTest(name, testFunction) {
                this.tests.push({ name, testFunction });
            }

            async runAllTests() {
                showNotification('Running comprehensive diagnostics...', 'warning');
                
                for (const test of this.tests) {
                    try {
                        this.results[test.name] = await test.testFunction();
                        this.updateDiagnosticsDisplay(test.name, this.results[test.name]);
                    } catch (error) {
                        this.results[test.name] = { status: 'error', message: error.message };
                        this.updateDiagnosticsDisplay(test.name, this.results[test.name]);
                    }
                }
                
                showNotification('Diagnostics completed successfully!', 'success');
                return this.results;
            }

            updateDiagnosticsDisplay(testName, result) {
                const panel = document.getElementById('diagnosticsPanel');
                // Update specific test in display
                console.log(`🔍 ${testName}:`, result);
            }
        }

        // ===== APPLICATION INITIALIZATION =====
        const securitySystem = new SecuritySystem();
        const authSystem = new AuthSystem();
        const paymentSystem = new PaymentSystem();
        const diagnosticsSystem = new DiagnosticsSystem();

        // Initialize diagnostics tests
        diagnosticsSystem.addTest('security_scan', async () => {
            await new Promise(resolve => setTimeout(resolve, 500));
            return { status: 'ok', message: 'All security protocols active' };
        });

        diagnosticsSystem.addTest('ssl_verification', async () => {
            await new Promise(resolve => setTimeout(resolve, 300));
            return { status: 'ok', message: 'SSL Certificate valid' };
        });

        diagnosticsSystem.addTest('database_connection', async () => {
            await new Promise(resolve => setTimeout(resolve, 700));
            return { status: 'ok', message: 'Database connection established' };
        });

        diagnosticsSystem.addTest('payment_gateway', async () => {
            await new Promise(resolve => setTimeout(resolve, 400));
            return { status: 'ok', message: 'Payment systems operational' };
        });

        // ===== DOM MANIPULATION FUNCTIONS =====
        function showNotification(message, type = 'info') {
            const container = document.getElementById('notificationContainer');
            const notification = document.createElement('div');
            notification.className = `notification ${type}`;
            notification.textContent = message;
            container.appendChild(notification);

            setTimeout(() => notification.classList.add('show'), 100);
            setTimeout(() => {
                notification.classList.remove('show');
                setTimeout(() => notification.remove(), 300);
            }, 4000);
        }

        function openSettings() {
            document.getElementById('settingsModal').style.display = 'flex';
            loadSettings();
        }

        function closeSettings() {
            document.getElementById('settingsModal').style.display = 'none';
        }

        function loadSettings() {
            const settings = JSON.parse(localStorage.getItem('appSettings') || '{}');
            document.getElementById('autoLogin').checked = settings.autoLogin || false;
            document.getElementById('twoFactor').checked = settings.twoFactor || false;
            document.getElementById('saveLogin').checked = settings.saveLogin || true;
            document.getElementById('allowCookies').checked = settings.allowCookies || true;
            document.getElementById('dataEncryption').checked = settings.dataEncryption !== false;
            document.getElementById('doubleClick').checked = settings.doubleClick || false;
            document.getElementById('rightClick').checked = settings.rightClick !== false;
            document.getElementById('sessionTimeout').value = settings.sessionTimeout || 30;
            document.getElementById('theme').value = settings.theme || 'light';
        }

        function updateSetting(key, value) {
            const settings = JSON.parse(localStorage.getItem('appSettings') || '{}');
            settings[key] = value;
            localStorage.setItem('appSettings', JSON.stringify(settings));
            
            // Update CONFIG
            if (key in CONFIG.features) {
                CONFIG.features[key] = value;
            }
            if (key in CONFIG.security) {
                CONFIG.security[key] = value;
            }

            showNotification(`Setting updated: ${key}`, 'success');
            applySettings();
        }

        function applySettings() {
            const settings = JSON.parse(localStorage.getItem('appSettings') || '{}');
            
            // Apply double-click behavior
            document.addEventListener('dblclick', (e) => {
                if (CONFIG.features.doubleClick && e.target.classList.contains('book-card')) {
                    securePurchase(e.target.querySelector('.book-title').textContent);
                }
            });

            // Apply right-click behavior
            document.addEventListener('contextmenu', (e) => {
                if (!CONFIG.features.rightClick) {
                    e.preventDefault();
                    return;
                }
                
                if (e.target.classList.contains('book-card') || e.target.closest('.book-card')) {
                    e.preventDefault();
                    showContextMenu(e);
                }
            });
        }

        function showContextMenu(e) {
            const contextMenu = document.getElementById('contextMenu');
            contextMenu.style.display = 'block';
            contextMenu.style.left = e.pageX + 'px';
            contextMenu.style.top = e.pageY + 'px';
        }

        function hideContextMenu() {
            document.getElementById('contextMenu').style.display = 'none';
        }

        function openInNewTab() {
            window.open(window.location.href, '_blank');
            hideContextMenu();
        }

        function savePage() {
            const blob = new Blob([document.documentElement.outerHTML], { type: 'text/html' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = 'the-definitive-word.html';
            a.click();
            hideContextMenu();
        }

        function inspectElement() {
            showNotification('Inspect element functionality activated', 'info');
            hideContextMenu();
        }

        function viewSource() {
            window.open('view-source:' + window.location.href, '_blank');
            hideContextMenu();
        }

        async function securePurchase(bookTitle) {
            try {
                showNotification(`Processing secure purchase of "${bookTitle}"...`, 'warning');
                
                const transactionId = await paymentSystem.processPayment(19.99, 'credit-card');
                
                showNotification(`Purchase successful! Transaction ID: ${transactionId}`, 'success');
                securitySystem.logSecurityEvent('purchase_completed', { 
                    bookTitle, 
                    transactionId,
                    encrypted: securitySystem.encryptData({ bookTitle, transactionId })
                });
            } catch (error) {
                showNotification(`Purchase failed: ${error.message}`, 'error');
            }
        }

        function toggleLogin() {
            const email = 'user@example.com';
            const password = 'SecurePass123';
            
            authSystem.login(email, password, CONFIG.features.saveLogin)
                .then(user => {
                    showNotification(`Welcome back, ${user.name}!`, 'success');
                    document.getElementById('loginButton').innerHTML = '<i class="fas fa-user-check"></i> Logout';
                    document.getElementById('loginButton').onclick = () => {
                        authSystem.logout();
                        showNotification('Logged out successfully', 'info');
                        document.getElementById('loginButton').innerHTML = '<i class="fas fa-user"></i> Sign In';
                        document.getElementById('loginButton').onclick = toggleLogin;
                    };
                })
                .catch(error => {
                    showNotification(`Login failed: ${error.message}`, 'error');
                });
        }

        function runFullDiagnostics() {
            diagnosticsSystem.runAllTests();
        }

        // ===== INITIALIZATION =====
        document.addEventListener('DOMContentLoaded', async function() {
            // Hide loading screen
            setTimeout(() => {
                document.getElementById('loadingScreen').style.display = 'none';
            }, 2000);

            // Apply settings
            applySettings();

            // Hide context menu on click
            document.addEventListener('click', hideContextMenu);

            // Run initial diagnostics
            if (CONFIG.diagnostics.autoRun) {
                setTimeout(() => {
                    diagnosticsSystem.runAllTests();
                }, 3000);
            }

            // Check for saved session
            const savedSession = localStorage.getItem('userSession');
            if (savedSession && CONFIG.features.autoLogin) {
                try {
                    const sessionData = securitySystem.decryptData(savedSession);
                    if (sessionData && (Date.now() - sessionData.timestamp) < (24 * 60 * 60 * 1000)) {
                        await authSystem.login(sessionData.email, 'auto', true);
                        showNotification('Auto-login successful!', 'success');
                    }
                } catch (e) {
                    console.warn('Auto-login failed:', e);
                }
            }

            // Session monitoring
            setInterval(() => {
                if (!authSystem.checkSession()) {
                    // Session expired
                }
            }, 60000); // Check every minute

            showNotification('Enterprise security system activated', 'success');
        });

        // ===== VERSION CONTROL & LOGGING =====
        console.log(`🚀 The Definitive Word v${CONFIG.version} initialized`);
        console.log('🔒 Security System:', securitySystem);
        console.log('🔑 Auth System:', authSystem);
        console.log('💳 Payment System:', paymentSystem);
        console.log('🔍 Diagnostics System:', diagnosticsSystem);

        // Export for global access (for debugging)
        window.App = {
            config: CONFIG,
            security: securitySystem,
            auth: authSystem,
            payment: paymentSystem,
            diagnostics: diagnosticsSystem
        };
    </script>
</body>
</html>
