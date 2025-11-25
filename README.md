// COMPLETE EBOOK STORE - FRONTEND & BACKEND IN ONE FILE
import React, { useState, useEffect } from 'react';

// Mock backend data and functions (in a real app, this would be a separate server)
const mockBackend = {
  users: [
    { id: 1, name: 'John Doe', email: 'john@example.com', password: 'password123' }
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
      pages: 245,
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
      pages: 189,
      isFeatured: true
    },
    { 
      id: 3, 
      title: "Leadership in the Kingdom", 
      price: 29.99, 
      category: "Training", 
      image: "👑", 
      description: "Biblical principles for effective spiritual leadership.",
      author: "Pastor James Miller",
      pages: 312,
      isFeatured: true
    },
    { 
      id: 4, 
      title: "Prayer Warrior's Guide", 
      price: 14.99, 
      category: "Ministry", 
      image: "🙏", 
      description: "Transform your prayer life and see breakthrough.",
      author: "Rebecca Thompson",
      pages: 156,
      isFeatured: false
    },
    { 
      id: 5, 
      title: "Worship in Spirit & Truth", 
      price: 17.99, 
      category: "Worship", 
      image: "🎵", 
      description: "Experience deeper intimacy through worship.",
      author: "David Chen",
      pages: 201,
      isFeatured: false
    },
    { 
      id: 6, 
      title: "Financial Stewardship", 
      price: 21.99, 
      category: "Training", 
      image: "💰", 
      description: "Biblical wisdom for managing God's resources.",
      author: "Dr. Michael Johnson",
      pages: 278,
      isFeatured: false
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
      duration: "3 hours",
      maxParticipants: 50,
      currentParticipants: 23
    },
    { 
      id: 2, 
      title: "Ministry Leadership Training", 
      date: "Dec 12, 2025", 
      price: 79.99,
      description: "Develop leadership skills for effective ministry.",
      instructor: "Pastor James Miller",
      duration: "6 hours",
      maxParticipants: 30,
      currentParticipants: 18
    },
    { 
      id: 3, 
      title: "Biblical Counseling Certification", 
      date: "Jan 10, 2026", 
      price: 199.99,
      description: "Become certified in biblical counseling principles.",
      instructor: "Dr. Michael Johnson",
      duration: "8 weeks",
      maxParticipants: 25,
      currentParticipants: 12
    }
  ],
  blogs: [
    { 
      id: 1,
      title: "5 Keys to Hearing God's Voice", 
      date: "Nov 20, 2025", 
      excerpt: "Learn practical steps to discern divine direction in your daily life...",
      content: "In this comprehensive guide, we explore five essential keys to developing your ability to hear God's voice clearly. From cultivating a quiet heart to testing what you hear, these principles will transform your relationship with God.",
      author: "Sarah Williams",
      category: "Spiritual Growth",
      readTime: "5 min read"
    },
    { 
      id: 2,
      title: "The Power of Prophetic Intercession", 
      date: "Nov 15, 2025", 
      excerpt: "Discover how prayer shapes destinies and nations through prophetic insight...",
      content: "Prophetic intercession goes beyond ordinary prayer. It's about partnering with God's heart for individuals, communities, and nations. Learn how to pray with divine perspective and see breakthrough in impossible situations.",
      author: "Pastor James Miller",
      category: "Prayer",
      readTime: "7 min read"
    },
    { 
      id: 3,
      title: "Your Destiny Awaits", 
      date: "Nov 10, 2025", 
      excerpt: "Understanding the times and seasons of your life and calling...",
      content: "Every believer has a unique destiny designed by God. This article helps you recognize the seasons of your life and understand how God is preparing you for your ultimate purpose and calling.",
      author: "Dr. Michael Johnson",
      category: "Destiny",
      readTime: "6 min read"
    }
  ],

  // Mock API functions
  login: async (email, password) => {
    await new Promise(resolve => setTimeout(resolve, 1000)); // Simulate API delay
    const user = mockBackend.users.find(u => u.email === email && u.password === password);
    if (user) {
      const { password: _, ...userWithoutPassword } = user;
      return { success: true, user: userWithoutPassword, token: 'mock-jwt-token' };
    }
    return { success: false, message: 'Invalid email or password' };
  },

  register: async (name, email, password) => {
    await new Promise(resolve => setTimeout(resolve, 1000));
    const existingUser = mockBackend.users.find(u => u.email === email);
    if (existingUser) {
      return { success: false, message: 'User already exists' };
    }
    const newUser = { id: mockBackend.users.length + 1, name, email, password };
    mockBackend.users.push(newUser);
    const { password: _, ...userWithoutPassword } = newUser;
    return { success: true, user: userWithoutPassword, token: 'mock-jwt-token' };
  },

  processPayment: async (cart, user) => {
    await new Promise(resolve => setTimeout(resolve, 2000)); // Simulate payment processing
    return { success: true, orderId: 'ORD-' + Date.now(), message: 'Payment successful!' };
  },

  getFeaturedEbooks: () => {
    return mockBackend.ebooks.filter(ebook => ebook.isFeatured);
  }
};

// Icons (using simple text icons for compatibility)
const Icons = {
  ShoppingCart: () => <span>🛒</span>,
  Menu: () => <span>☰</span>,
  Close: () => <span>✕</span>,
  Book: () => <span>📚</span>,
  User: () => <span>👤</span>,
  Search: () => <span>🔍</span>,
  Mail: () => <span>✉️</span>,
  Phone: () => <span>📞</span>,
  MapPin: () => <span>📍</span>,
  BookOpen: () => <span>📖</span>,
  Calendar: () => <span>📅</span>,
  Award: () => <span>🏆</span>,
  Login: () => <span>🔑</span>,
  Logout: () => <span>🚪</span>,
  Download: () => <span>📥</span>,
  Clock: () => <span>⏰</span>
};

export default function EbookStore() {
  const [cart, setCart] = useState([]);
  const [currentPage, setCurrentPage] = useState('home');
  const [mobileMenuOpen, setMobileMenuOpen] = useState(false);
  const [user, setUser] = useState(null);
  const [loginModalOpen, setLoginModalOpen] = useState(false);
  const [isLogin, setIsLogin] = useState(true);
  const [loading, setLoading] = useState(false);
  const [searchQuery, setSearchQuery] = useState('');
  const [activeBlog, setActiveBlog] = useState(null);
  const [formData, setFormData] = useState({ name: '', email: '', password: '' });
  const [loginError, setLoginError] = useState('');

  // Load user from localStorage on component mount
  useEffect(() => {
    const savedUser = localStorage.getItem('ebookStoreUser');
    if (savedUser) {
      setUser(JSON.parse(savedUser));
    }
  }, []);

  const handleLogin = async (e) => {
    if (e) e.preventDefault();
    setLoading(true);
    setLoginError('');

    try {
      const result = isLogin 
        ? await mockBackend.login(formData.email, formData.password)
        : await mockBackend.register(formData.name, formData.email, formData.password);

      if (result.success) {
        setUser(result.user);
        localStorage.setItem('ebookStoreUser', JSON.stringify(result.user));
        localStorage.setItem('ebookStoreToken', result.token);
        setLoginModalOpen(false);
        setFormData({ name: '', email: '', password: '' });
      } else {
        setLoginError(result.message);
      }
    } catch (error) {
      setLoginError('An error occurred. Please try again.');
    } finally {
      setLoading(false);
    }
  };

  const handleLogout = () => {
    setUser(null);
    localStorage.removeItem('ebookStoreUser');
    localStorage.removeItem('ebookStoreToken');
    setCart([]);
  };

  const addToCart = (product) => {
    setCart([...cart, { ...product, cartId: Date.now() }]);
  };

  const removeFromCart = (cartId) => {
    setCart(cart.filter(item => item.cartId !== cartId));
  };

  const getTotal = () => {
    return cart.reduce((sum, item) => sum + item.price, 0).toFixed(2);
  };

  const handleCheckout = async () => {
    if (!user) {
      setLoginModalOpen(true);
      return;
    }

    setLoading(true);
    try {
      const result = await mockBackend.processPayment(cart, user);
      if (result.success) {
        alert(`Payment successful! Order ID: ${result.orderId}\n${result.message}`);
        setCart([]);
        setCurrentPage('home');
      }
    } catch (error) {
      alert('Payment failed. Please try again.');
    } finally {
      setLoading(false);
    }
  };

  const filteredEbooks = mockBackend.ebooks.filter(ebook =>
    ebook.title.toLowerCase().includes(searchQuery.toLowerCase()) ||
    ebook.author.toLowerCase().includes(searchQuery.toLowerCase()) ||
    ebook.description.toLowerCase().includes(searchQuery.toLowerCase())
  );

  const featuredEbooks = mockBackend.getFeaturedEbooks();

  // Login Modal Component
  const LoginModal = () => {
    if (!loginModalOpen) return null;

    return (
      <div style={{
        position: 'fixed',
        top: 0,
        left: 0,
        right: 0,
        bottom: 0,
        backgroundColor: 'rgba(0,0,0,0.5)',
        display: 'flex',
        alignItems: 'center',
        justifyContent: 'center',
        zIndex: 1000
      }}>
        <div style={{
          backgroundColor: 'white',
          padding: '2rem',
          borderRadius: '8px',
          width: '90%',
          maxWidth: '400px',
          position: 'relative'
        }}>
          <button 
            onClick={() => setLoginModalOpen(false)}
            style={{
              position: 'absolute',
              top: '1rem',
              right: '1rem',
              background: 'none',
              border: 'none',
              fontSize: '1.5rem',
              cursor: 'pointer'
            }}
          >
            <Icons.Close />
          </button>

          <h2 style={{ fontSize: '1.5rem', fontWeight: 'bold', marginBottom: '1rem' }}>
            {isLogin ? 'Login' : 'Register'}
          </h2>

          {loginError && (
            <div style={{
              backgroundColor: '#fee2e2',
              border: '1px solid #ef4444',
              color: '#dc2626',
              padding: '0.75rem',
              borderRadius: '4px',
              marginBottom: '1rem'
            }}>
              {loginError}
            </div>
          )}

          <form onSubmit={handleLogin}>
            {!isLogin && (
              <div style={{ marginBottom: '1rem' }}>
                <label style={{ display: 'block', fontWeight: 'bold', marginBottom: '0.5rem' }}>
                  Name
                </label>
                <input
                  type="text"
                  value={formData.name}
                  onChange={(e) => setFormData({...formData, name: e.target.value})}
                  style={{
                    width: '100%',
                    padding: '0.5rem',
                    border: '1px solid #d1d5db',
                    borderRadius: '4px'
                  }}
                  required
                />
              </div>
            )}

            <div style={{ marginBottom: '1rem' }}>
              <label style={{ display: 'block', fontWeight: 'bold', marginBottom: '0.5rem' }}>
                Email
              </label>
              <input
                type="email"
                value={formData.email}
                onChange={(e) => setFormData({...formData, email: e.target.value})}
                style={{
                  width: '100%',
                  padding: '0.5rem',
                  border: '1px solid #d1d5db',
                  borderRadius: '4px'
                }}
                required
              />
            </div>

            <div style={{ marginBottom: '1.5rem' }}>
              <label style={{ display: 'block', fontWeight: 'bold', marginBottom: '0.5rem' }}>
                Password
              </label>
              <input
                type="password"
                value={formData.password}
                onChange={(e) => setFormData({...formData, password: e.target.value})}
                style={{
                  width: '100%',
                  padding: '0.5rem',
                  border: '1px solid #d1d5db',
                  borderRadius: '4px'
                }}
                required
              />
            </div>

            <button
              type="submit"
              disabled={loading}
              style={{
                width: '100%',
                backgroundColor: loading ? '#9ca3af' : '#1d4ed8',
                color: 'white',
                fontWeight: 'bold',
                padding: '0.75rem',
                borderRadius: '4px',
                border: 'none',
                cursor: loading ? 'not-allowed' : 'pointer'
              }}
            >
              {loading ? 'Processing...' : (isLogin ? 'Login' : 'Register')}
            </button>
          </form>

          <div style={{ textAlign: 'center', marginTop: '1rem' }}>
            <button
              onClick={() => {
                setIsLogin(!isLogin);
                setLoginError('');
                setFormData({ name: '', email: '', password: '' });
              }}
              style={{
                background: 'none',
                border: 'none',
                color: '#1d4ed8',
                cursor: 'pointer',
                textDecoration: 'underline'
              }}
            >
              {isLogin ? 'Need an account? Register' : 'Have an account? Login'}
            </button>
          </div>
        </div>
      </div>
    );
  };

  // Navigation Component
  const NavBar = () => (
    <nav style={{
      backgroundColor: 'white',
      boxShadow: '0 2px 4px rgba(0,0,0,0.1)',
      position: 'sticky',
      top: 0,
      zIndex: 100
    }}>
      <div style={{ maxWidth: '1200px', margin: '0 auto', padding: '0 1rem' }}>
        <div style={{
          display: 'flex',
          justifyContent: 'space-between',
          alignItems: 'center',
          height: '80px'
        }}>
          <div 
            style={{ display: 'flex', alignItems: 'center', cursor: 'pointer' }}
            onClick={() => setCurrentPage('home')}
          >
            <Icons.Book />
            <div style={{ marginLeft: '0.75rem' }}>
              <h1 style={{ fontSize: '1.25rem', fontWeight: 'bold', color: '#1f2937' }}>
                The Definitive Word
              </h1>
              <p style={{ fontSize: '0.75rem', color: '#dc2626', fontStyle: 'italic' }}>
                Your Destiny Has Been Written
              </p>
            </div>
          </div>
          
          <div style={{ display: 'none', gap: '2rem', alignItems: 'center' }}>
            {['home', 'store', 'workshops', 'blog', 'about'].map((page) => (
              <button
                key={page}
                onClick={() => setCurrentPage(page)}
                style={{
                  color: '#374151',
                  fontWeight: '500',
                  background: 'none',
                  border: 'none',
                  cursor: 'pointer',
                  textTransform: 'capitalize'
                }}
              >
                {page}
              </button>
            ))}
          </div>

          <div style={{ display: 'flex', alignItems: 'center', gap: '1rem' }}>
            <button 
              onClick={() => setCurrentPage('cart')}
              style={{ position: 'relative', background: 'none', border: 'none', cursor: 'pointer' }}
            >
              <Icons.ShoppingCart />
              {cart.length > 0 && (
                <span style={{
                  position: 'absolute',
                  top: '-8px',
                  right: '-8px',
                  backgroundColor: '#dc2626',
                  color: 'white',
                  fontSize: '0.75rem',
                  borderRadius: '50%',
                  width: '20px',
                  height: '20px',
                  display: 'flex',
                  alignItems: 'center',
                  justifyContent: 'center'
                }}>
                  {cart.length}
                </span>
              )}
            </button>
            
            {user ? (
              <div style={{ display: 'flex', alignItems: 'center', gap: '0.5rem' }}>
                <span style={{ color: '#374151' }}>Hello, {user.name}</span>
                <button 
                  onClick={handleLogout}
                  style={{ background: 'none', border: 'none', cursor: 'pointer' }}
                >
                  <Icons.Logout />
                </button>
              </div>
            ) : (
              <button 
                onClick={() => setLoginModalOpen(true)}
                style={{ background: 'none', border: 'none', cursor: 'pointer' }}
              >
                <Icons.Login />
              </button>
            )}
            
            <button 
              onClick={() => setMobileMenuOpen(!mobileMenuOpen)}
              style={{ background: 'none', border: 'none', cursor: 'pointer' }}
            >
              {mobileMenuOpen ? <Icons.Close /> : <Icons.Menu />}
            </button>
          </div>
        </div>
        
        {mobileMenuOpen && (
          <div style={{
            backgroundColor: 'white',
            borderTop: '1px solid #e5e7eb',
            padding: '1rem'
          }}>
            {['home', 'store', 'workshops', 'blog', 'about'].map((page) => (
              <button
                key={page}
                onClick={() => {
                  setCurrentPage(page);
                  setMobileMenuOpen(false);
                }}
                style={{
                  display: 'block',
                  width: '100%',
                  textAlign: 'left',
                  color: '#374151',
                  background: 'none',
                  border: 'none',
                  cursor: 'pointer',
                  padding: '0.5rem 0',
                  textTransform: 'capitalize'
                }}
              >
                {page}
              </button>
            ))}
          </div>
        )}
      </div>
    </nav>
  );

  // Page Components
  const HomePage = () => (
    <div style={{ backgroundColor: 'white' }}>
      <div style={{
        background: 'linear-gradient(to right, #1d4ed8, #1e40af)',
        color: 'white',
        padding: '6rem 1rem',
        textAlign: 'center'
      }}>
        <h1 style={{ fontSize: '3rem', fontWeight: 'bold', marginBottom: '1rem' }}>
          The Definitive Word
        </h1>
        <p style={{ fontSize: '1.5rem', marginBottom: '0.5rem', color: '#fecaca', fontStyle: 'italic', fontWeight: '600' }}>
          Your Destiny Has Been Written
        </p>
        <p style={{ fontSize: '1.25rem', marginBottom: '2rem' }}>
          Empowering believers through prophetic wisdom and biblical teaching
        </p>
        <div style={{ display: 'flex', gap: '1rem', justifyContent: 'center', flexWrap: 'wrap' }}>
          <button 
            onClick={() => setCurrentPage('store')}
            style={{
              backgroundColor: '#dc2626',
              color: 'white',
              fontWeight: 'bold',
              padding: '0.75rem 2rem',
              borderRadius: '8px',
              border: 'none',
              cursor: 'pointer'
            }}
          >
            Browse Store
          </button>
          <button 
            onClick={() => setCurrentPage('workshops')}
            style={{
              backgroundColor: 'white',
              color: '#1d4ed8',
              fontWeight: 'bold',
              padding: '0.75rem 2rem',
              borderRadius: '8px',
              border: 'none',
              cursor: 'pointer'
            }}
          >
            View Workshops
          </button>
        </div>
      </div>

      <div style={{ maxWidth: '1200px', margin: '0 auto', padding: '4rem 1rem' }}>
        <div style={{ display: 'grid', gridTemplateColumns: 'repeat(auto-fit, minmax(250px, 1fr))', gap: '2rem', marginBottom: '4rem' }}>
          {[
            { icon: <Icons.BookOpen />, title: 'Digital Books', desc: 'Access transformative teaching instantly', color: '#1d4ed8' },
            { icon: <Icons.Award />, title: 'Training & Workshops', desc: 'Equip yourself for ministry excellence', color: '#dc2626' },
            { icon: <Icons.Calendar />, title: 'Ministry Resources', desc: 'Tools to strengthen your calling', color: '#1d4ed8' }
          ].map((item, index) => (
            <div key={index} style={{
              textAlign: 'center',
              padding: '1.5rem',
              border: `2px solid ${item.color}`,
              borderRadius: '8px',
              transition: 'box-shadow 0.3s'
            }}>
              <div style={{ fontSize: '3rem', marginBottom: '1rem' }}>{item.icon}</div>
              <h3 style={{ fontSize: '1.25rem', fontWeight: 'bold', marginBottom: '0.5rem' }}>{item.title}</h3>
              <p style={{ color: '#6b7280' }}>{item.desc}</p>
            </div>
          ))}
        </div>

        <div style={{
          background: 'linear-gradient(to right, #dbeafe, #fecaca)',
          padding: '2rem',
          borderRadius: '8px'
        }}>
          <h2 style={{ fontSize: '2rem', fontWeight: 'bold', textAlign: 'center', marginBottom: '2rem' }}>
            Featured Books
          </h2>
          <div style={{ display: 'grid', gridTemplateColumns: 'repeat(auto-fit, minmax(280px, 1fr))', gap: '1.5rem' }}>
            {featuredEbooks.map(book => (
              <div key={book.id} style={{
                backgroundColor: 'white',
                padding: '1.5rem',
                borderRadius: '8px',
                boxShadow: '0 4px 6px rgba(0,0,0,0.1)',
                transition: 'box-shadow 0.3s'
              }}>
                <div style={{ fontSize: '4rem', textAlign: 'center', marginBottom: '1rem' }}>{book.image}</div>
                <h3 style={{ fontWeight: 'bold', fontSize: '1.125rem', marginBottom: '0.5rem' }}>{book.title}</h3>
                <p style={{ color: '#6b7280', fontSize: '0.875rem', marginBottom: '1rem' }}>{book.description}</p>
                <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center' }}>
                  <span style={{ fontSize: '1.5rem', fontWeight: 'bold', color: '#1d4ed8' }}>
                    ${book.price}
                  </span>
                  <button 
                    onClick={() => addToCart(book)}
                    style={{
                      backgroundColor: '#dc2626',
                      color: 'white',
                      padding: '0.5rem 1rem',
                      borderRadius: '8px',
                      border: 'none',
                      cursor: 'pointer'
                    }}
                  >
                    Add to Cart
                  </button>
                </div>
              </div>
            ))}
          </div>
        </div>
      </div>
    </div>
  );

  const StorePage = () => (
    <div style={{ maxWidth: '1200px', margin: '0 auto', padding: '2rem 1rem' }}>
      <div style={{ marginBottom: '2rem' }}>
        <h1 style={{ fontSize: '2.5rem', fontWeight: 'bold', marginBottom: '0.5rem' }}>
          Ebook Store
        </h1>
        <p style={{ color: '#6b7280' }}>
          Transform your life with prophetic wisdom and biblical teaching
        </p>
      </div>

      <div style={{ marginBottom: '2rem' }}>
        <div style={{ position: 'relative' }}>
          <div style={{ position: 'absolute', left: '0.75rem', top: '0.75rem' }}>
            <Icons.Search />
          </div>
          <input 
            type="text" 
            placeholder="Search books..." 
            value={searchQuery}
            onChange={(e) => setSearchQuery(e.target.value)}
            style={{
              width: '100%',
              paddingLeft: '2.5rem',
              paddingRight: '1rem',
              paddingTop: '0.5rem',
              paddingBottom: '0.5rem',
              border: '2px solid #d1d5db',
              borderRadius: '8px',
              outline: 'none'
            }}
          />
        </div>
      </div>

      <div style={{ display: 'grid', gridTemplateColumns: 'repeat(auto-fit, minmax(280px, 1fr))', gap: '1.5rem' }}>
        {filteredEbooks.map(book => (
          <div key={book.id} style={{
            backgroundColor: 'white',
            border: '2px solid #e5e7eb',
            borderRadius: '8px',
            padding: '1.5rem',
            transition: 'all 0.3s'
          }}>
            <div style={{ fontSize: '4rem', textAlign: 'center', marginBottom: '1rem' }}>{book.image}</div>
            <div style={{ fontSize: '0.75rem', color: '#dc2626', fontWeight: '600', marginBottom: '0.5rem' }}>
              {book.category}
            </div>
            <h3 style={{ fontWeight: 'bold', fontSize: '1.25rem', marginBottom: '0.5rem' }}>{book.title}</h3>
            <p style={{ color: '#6b7280', fontSize: '0.875rem', marginBottom: '1rem' }}>{book.description}</p>
            <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center' }}>
              <span style={{ fontSize: '1.5rem', fontWeight: 'bold', color: '#1d4ed8' }}>
                ${book.price}
              </span>
              <button 
                onClick={() => addToCart(book)}
                style={{
                  backgroundColor: '#dc2626',
                  color: 'white',
                  padding: '0.5rem 1.5rem',
                  borderRadius: '8px',
                  border: 'none',
                  cursor: 'pointer',
                  fontWeight: '600'
                }}
              >
                Add to Cart
              </button>
            </div>
          </div>
        ))}
      </div>

      {filteredEbooks.length === 0 && (
        <div style={{ textAlign: 'center', padding: '3rem' }}>
          <p style={{ color: '#6b7280', fontSize: '1.125rem' }}>No books found matching your search.</p>
        </div>
      )}
    </div>
  );

  const WorkshopsPage = () => (
    <div style={{ maxWidth: '1200px', margin: '0 auto', padding: '2rem 1rem' }}>
      <h1 style={{ fontSize: '2.5rem', fontWeight: 'bold', marginBottom: '2rem' }}>
        Workshops & Training
      </h1>
      <div style={{ display: 'flex', flexDirection: 'column', gap: '1.5rem' }}>
        {mockBackend.workshops.map(workshop => (
          <div key={workshop.id} style={{
            backgroundColor: 'white',
            border: '2px solid #1d4ed8',
            borderRadius: '8px',
            padding: '1.5rem'
          }}>
            <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'flex-start' }}>
              <div style={{ flex: 1 }}>
                <h3 style={{ fontSize: '1.5rem', fontWeight: 'bold', marginBottom: '0.5rem' }}>
                  {workshop.title}
                </h3>
                <p style={{ color: '#6b7280', marginBottom: '1rem' }}>
                  <Icons.Calendar /> {workshop.date} • {workshop.duration} • Instructor: {workshop.instructor}
                </p>
                <p style={{ color: '#374151', marginBottom: '1rem' }}>
                  {workshop.description}
                </p>
                <p style={{ color: '#6b7280', fontSize: '0.875rem' }}>
                  {workshop.currentParticipants}/{workshop.maxParticipants} participants registered
                </p>
              </div>
              <div style={{ textAlign: 'right', marginLeft: '1.5rem' }}>
                <div style={{ fontSize: '1.875rem', fontWeight: 'bold', color: '#1d4ed8', marginBottom: '1rem' }}>
                  ${workshop.price}
                </div>
                <button 
                  onClick={() => addToCart(workshop)}
                  style={{
                    backgroundColor: '#dc2626',
                    color: 'white',
                    padding: '0.5rem 1.5rem',
                    borderRadius: '8px',
                    border: 'none',
                    cursor: 'pointer',
                    fontWeight: '600'
                  }}
                >
                  Register Now
                </button>
              </div>
            </div>
          </div>
        ))}
      </div>
    </div>
  );

  const BlogPage = () => (
    <div style={{ maxWidth: '800px', margin: '0 auto', padding: '2rem 1rem' }}>
      <h1 style={{ fontSize: '2.5rem', fontWeight: 'bold', marginBottom: '2rem' }}>
        Ministry Blog
      </h1>
      <div style={{ display: 'flex', flexDirection: 'column', gap: '1.5rem' }}>
        {mockBackend.blogs.map(blog => (
          <div key={blog.id} style={{
            backgroundColor: 'white',
            borderLeft: '4px solid #1d4ed8',
            padding: '1.5rem',
            boxShadow: '0 4px 6px rgba(0,0,0,0.1)',
            cursor: 'pointer'
          }}
          onClick={() => setActiveBlog(blog)}
          >
            <h3 style={{ fontSize: '1.5rem', fontWeight: 'bold', marginBottom: '0.5rem' }}>
              {blog.title}
            </h3>
            <p style={{ fontSize: '0.875rem', color: '#6b7280', marginBottom: '0.5rem' }}>
              {blog.date} • {blog.category} • {blog.readTime}
            </p>
            <p style={{ color: '#374151', marginBottom: '1rem' }}>
              {blog.excerpt}
            </p>
            <button style={{
              color: '#dc2626',
              fontWeight: '600',
              background: 'none',
              border: 'none',
              cursor: 'pointer'
            }}>
              Read More →
            </button>
          </div>
        ))}
      </div>

      {activeBlog && (
        <div style={{
          position: 'fixed',
          top: 0,
          left: 0,
          right: 0,
          bottom: 0,
          backgroundColor: 'rgba(0,0,0,0.5)',
          display: 'flex',
          alignItems: 'center',
          justifyContent: 'center',
          zIndex: 1000,
          padding: '1rem'
        }}>
          <div style={{
            backgroundColor: 'white',
            padding: '2rem',
            borderRadius: '8px',
            maxWidth: '600px',
            maxHeight: '80vh',
            overflow: 'auto',
            position: 'relative'
          }}>
            <button 
              onClick={() => setActiveBlog(null)}
              style={{
                position: 'absolute',
                top: '1rem',
                right: '1rem',
                background: 'none',
                border: 'none',
                fontSize: '1.5rem',
                cursor: 'pointer'
              }}
            >
              <Icons.Close />
            </button>
            <h2 style={{ fontSize: '1.875rem', fontWeight: 'bold', marginBottom: '1rem' }}>
              {activeBlog.title}
            </h2>
            <p style={{ color: '#6b7280', marginBottom: '1rem' }}>
              By {activeBlog.author} • {activeBlog.date} • {activeBlog.readTime}
            </p>
            <div style={{ lineHeight: '1.6' }}>
              <p style={{ marginBottom: '1rem' }}>{activeBlog.content}</p>
              <p style={{ marginBottom: '1rem' }}>Continue reading for more insights and practical applications...</p>
            </div>
          </div>
        </div>
      )}
    </div>
  );

  const CartPage = () => (
    <div style={{ maxWidth: '800px', margin: '0 auto', padding: '2rem 1rem' }}>
      <h1 style={{ fontSize: '2.5rem', fontWeight: 'bold', marginBottom: '2rem' }}>
        Shopping Cart
      </h1>
      
      {cart.length === 0 ? (
        <div style={{ textAlign: 'center', padding: '4rem' }}>
          <Icons.ShoppingCart />
          <p style={{ fontSize: '1.25rem', color: '#6b7280', margin: '1rem 0' }}>
            Your cart is empty
          </p>
          <button 
            onClick={() => setCurrentPage('store')}
            style={{
              backgroundColor: '#1d4ed8',
              color: 'white',
              padding: '0.75rem 1.5rem',
              borderRadius: '8px',
              border: 'none',
              cursor: 'pointer'
            }}
          >
            Continue Shopping
          </button>
        </div>
      ) : (
        <div>
          <div style={{ display: 'flex', flexDirection: 'column', gap: '1rem', marginBottom: '2rem' }}>
            {cart.map((item) => (
              <div key={item.cartId} style={{
                display: 'flex',
                justifyContent: 'space-between',
                alignItems: 'center',
                backgroundColor: 'white',
                padding: '1rem',
                borderRadius: '8px',
                border: '2px solid #e5e7eb'
              }}>
                <div style={{ display: 'flex', alignItems: 'center' }}>
                  <div style={{ fontSize: '2.5rem', marginRight: '1rem' }}>{item.image}</div>
                  <div>
                    <h3 style={{ fontWeight: 'bold', color: '#1f2937' }}>{item.title}</h3>
                    <p style={{ fontSize: '0.875rem', color: '#6b7280' }}>{item.category}</p>
                  </div>
                </div>
                <div style={{ display: 'flex', alignItems: 'center', gap: '1.5rem' }}>
                  <span style={{ fontSize: '1.25rem', fontWeight: 'bold', color: '#1d4ed8' }}>
                    ${item.price}
                  </span>
                  <button 
                    onClick={() => removeFromCart(item.cartId)}
                    style={{
                      color: '#dc2626',
                      background: 'none',
                      border: 'none',
                      cursor: 'pointer'
                    }}
                  >
                    <Icons.Close />
                  </button>
                </div>
              </div>
            ))}
          </div>

          <div style={{
            background: 'linear-gradient(to right, #dbeafe, #fecaca)',
            padding: '1.5rem',
            borderRadius: '8px'
          }}>
            <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center', marginBottom: '1.5rem' }}>
              <span style={{ fontSize: '1.5rem', fontWeight: 'bold', color: '#1f2937' }}>
                Total:
              </span>
              <span style={{ fontSize: '2rem', fontWeight: 'bold', color: '#1d4ed8' }}>
                ${getTotal()}
              </span>
            </div>
            <button 
              onClick={handleCheckout}
              disabled={loading}
              style={{
                width: '100%',
                backgroundColor: loading ? '#9ca3af' : '#dc2626',
                color: 'white',
                fontWeight: 'bold',
                padding: '1rem',
                borderRadius: '8px',
                border: 'none',
                cursor: loading ? 'not-allowed' : 'pointer',
                fontSize: '1.125rem'
              }}
            >
              {loading ? 'Processing...' : 'Proceed to Checkout'}
            </button>
            <p style={{ textAlign: 'center', fontSize: '0.875rem', color: '#6b7280', marginTop: '0.5rem' }}>
              Secure payment processing
            </p>
          </div>
        </div>
      )}
    </div>
  );

  const AboutPage = () => (
    <div style={{ maxWidth: '800px', margin: '0 auto', padding: '2rem 1rem' }}>
      <h1 style={{ fontSize: '2.5rem', fontWeight: 'bold', marginBottom: '2rem' }}>
        About The Definitive Word
      </h1>
      <div style={{
        background: 'linear-gradient(to right, #dbeafe, #fecaca)',
        padding: '2rem',
        borderRadius: '8px',
        marginBottom: '2rem'
      }}>
        <p style={{ fontSize: '1.125rem', color: '#374151', marginBottom: '1rem' }}>
          The Definitive Word is a prophetic ministry dedicated to empowering believers through biblical teaching, prophetic insights, and practical training. Our mission is to help you discover and walk in your God-given destiny.
        </p>
        <p style={{ fontSize: '1.125rem', color: '#374151' }}>
          Through our ebooks, workshops, and training materials, we provide tools and resources that transform lives and activate callings.
        </p>
      </div>
      
      <div style={{ display: 'flex', flexDirection: 'column', gap: '1rem' }}>
        <div style={{ display: 'flex', alignItems: 'center' }}>
          <Icons.Mail />
          <span style={{ marginLeft: '0.75rem', color: '#374151' }}>contact@thedefinitiveword.com</span>
        </div>
        <div style={{ display: 'flex', alignItems: 'center' }}>
          <Icons.Phone />
          <span style={{ marginLeft: '0.75rem', color: '#374151' }}>+1 (555) 123-4567</span>
        </div>
        <div style={{ display: 'flex', alignItems: 'center' }}>
          <Icons.MapPin />
          <span style={{ marginLeft: '0.75rem', color: '#374151' }}>Your Ministry Location</span>
        </div>
      </div>
    </div>
  );

  return (
    <div style={{ minHeight: '100vh', backgroundColor: '#f9fafb' }}>
      <NavBar />
      
      {currentPage === 'home' && <HomePage />}
      {currentPage === 'store' && <StorePage />}
      {currentPage === 'workshops' && <WorkshopsPage />}
      {currentPage === 'blog' && <BlogPage />}
      {currentPage === 'cart' && <CartPage />}
      {currentPage === 'about' && <AboutPage />}

      <LoginModal />

      <footer style={{
        background: 'linear-gradient(to right, #1e40af, #1d4ed8)',
        color: 'white',
        padding: '2rem 1rem',
        marginTop: '4rem'
      }}>
        <div style={{ maxWidth: '1200px', margin: '0 auto', textAlign: 'center' }}>
          <h3 style={{ fontSize: '1.5rem', fontWeight: 'bold', marginBottom: '0.5rem' }}>
            The Definitive Word
          </h3>
          <p style={{ color: '#fecaca', fontStyle: 'italic', marginBottom: '1rem' }}>
            Your Destiny Has Been Written
          </p>
          <p style={{ fontSize: '0.875rem' }}>
            © 2025 The Definitive Word. All rights reserved.
          </p>
        </div>
      </footer>
    </div>
  );
}
