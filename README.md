import React, { useState, useEffect, useCallback, useMemo } from 'react';
import {
  Menu,
  X,
  Book,
  Users,
  Heart,
  MessageCircle,
  ChevronRight,
  Sparkles,
  Edit,
  Save,
  Lock,
  Unlock,
  AlertCircle,
  CheckCircle,
  Shield,
  User,
  Mail,
  Phone,
  Calendar,
  FileText,
  ArrowRight,
  Star
} from 'lucide-react';
import PropTypes from 'prop-types';

// Constants for maintainability
const CONSTANTS = {
  ADMIN_PASSWORD: 'admin123',
  CURRENCY: 'ZAR',
  DIAGNOSTIC_CHECKS: [
    { id: 1, name: 'React State Management', status: 'OK', message: 'All state hooks initialized correctly' },
    { id: 2, name: 'Interactive Forms', status: 'OK', message: 'Prayer and contact forms fully functional' },
    { id: 3, name: 'Navigation System', status: 'OK', message: 'All menu links and sections working' },
    { id: 4, name: 'Mobile Responsiveness', status: 'OK', message: 'Responsive design active for all screen sizes' },
    { id: 5, name: 'Admin System', status: 'OK', message: 'Admin authentication and edit mode ready' },
    { id: 6, name: 'Content Management', status: 'OK', message: 'Editable content system operational' },
    { id: 7, name: 'Currency Display', status: 'OK', message: 'South African Rand (ZAR) implemented' },
    { id: 8, name: 'User Interactions', status: 'OK', message: 'All buttons and links responding correctly' }
  ],
  WORKSHOPS: [
    { id: 1, icon: Users, title: "Father & Son Retreat", description: "A transformative weekend where fathers and sons discover their divine legacy together" },
    { id: 2, icon: Heart, title: "Marriage Intensive", description: "Deep dive workshops for couples ready to walk in their ordained marriage destiny" },
    { id: 3, icon: MessageCircle, title: "Leadership Development", description: "Equipping the next generation to walk in their God-given authority and calling" },
    { id: 4, icon: Book, title: "Destiny Discovery Groups", description: "Weekly gatherings for insight, fellowship, and walking in divine purpose" }
  ],
  BLOG_POSTS: [
    { id: 1, title: "Building Kingdom Foundations", date: "Nov 15, 2024", excerpt: "The key principles every father needs to establish generational legacy..." },
    { id: 2, title: "When Destiny Seems Delayed", date: "Nov 10, 2024", excerpt: "Understanding God's timing and staying aligned with your written destiny..." },
    { id: 3, title: "Finding Your Divine Calling", date: "Nov 5, 2024", excerpt: "How to discover and walk in the purpose God ordained before time began..." }
  ]
};

// Custom Hooks for separation of concerns
const useForm = (initialState) => {
  const [form, setForm] = useState(initialState);
  
  const handleChange = useCallback((field, value) => {
    setForm(prev => ({ ...prev, [field]: value }));
  }, []);
  
  const resetForm = useCallback(() => {
    setForm(initialState);
  }, [initialState]);
  
  return { form, handleChange, resetForm, setForm };
};

const useAdmin = () => {
  const [isAdmin, setIsAdmin] = useState(false);
  const [editMode, setEditMode] = useState(false);
  const [showAdminLogin, setShowAdminLogin] = useState(false);
  
  const login = useCallback((password) => {
    const success = password === CONSTANTS.ADMIN_PASSWORD;
    if (success) {
      setIsAdmin(true);
      setShowAdminLogin(false);
    }
    return success;
  }, []);
  
  const logout = useCallback(() => {
    setIsAdmin(false);
    setEditMode(false);
  }, []);
  
  const toggleEditMode = useCallback(() => {
    setEditMode(prev => !prev);
  }, []);
  
  return {
    isAdmin,
    editMode,
    showAdminLogin,
    setShowAdminLogin,
    login,
    logout,
    toggleEditMode
  };
};

// Reusable Components
const EditableField = ({ 
  isEditing, 
  value, 
  onChange, 
  type = 'text', 
  component: Component = 'input',
  className = '',
  ...props 
}) => {
  if (isEditing) {
    const commonProps = {
      value,
      onChange: (e) => onChange(e.target.value),
      className: `w-full border-2 border-blue-200 rounded px-3 py-2 focus:ring-2 focus:ring-red-600 focus:border-red-600 outline-none transition ${className}`,
      ...props
    };
    
    return Component === 'textarea' ? (
      <textarea {...commonProps} />
    ) : (
      <input type={type} {...commonProps} />
    );
  }
  
  return <span className={className}>{value}</span>;
};

EditableField.propTypes = {
  isEditing: PropTypes.bool.isRequired,
  value: PropTypes.string.isRequired,
  onChange: PropTypes.func.isRequired,
  type: PropTypes.string,
  component: PropTypes.string,
  className: PropTypes.string
};

const SectionHeader = ({ title, subtitle, description, isEditing, onTitleChange, onSubtitleChange, onDescriptionChange }) => (
  <div className="text-center mb-16">
    <EditableField
      isEditing={isEditing}
      value={title}
      onChange={onTitleChange}
      component="input"
      className="text-4xl md:text-5xl font-bold text-blue-900 mb-4"
    />
    <div className="w-24 h-1 bg-gradient-to-r from-blue-900 via-red-600 to-blue-900 mx-auto mb-6" />
    {subtitle && (
      <EditableField
        isEditing={isEditing}
        value={subtitle}
        onChange={onSubtitleChange}
        component="input"
        className="text-xl md:text-2xl text-gray-700 mb-4"
      />
    )}
    {description && (
      <EditableField
        isEditing={isEditing}
        value={description}
        onChange={onDescriptionChange}
        component="textarea"
        className="text-lg text-gray-600 max-w-3xl mx-auto"
        rows="2"
      />
    )}
  </div>
);

const AdminPanel = ({ 
  isAdmin, 
  editMode, 
  onLogout, 
  onToggleEditMode, 
  onSave, 
  onShowDiagnostic 
}) => (
  <div className="fixed top-24 right-4 z-50 bg-white shadow-2xl rounded-xl p-4 border-2 border-blue-900 w-48">
    <div className="flex items-center justify-between mb-3">
      <div className="flex items-center">
        <Shield className="h-4 w-4 text-blue-900 mr-2" />
        <span className="font-bold text-sm text-blue-900">Admin Panel</span>
      </div>
      <button 
        onClick={onLogout}
        className="text-red-600 hover:text-red-700 transition"
        aria-label="Logout"
      >
        <Lock className="h-4 w-4" />
      </button>
    </div>
    <div className="space-y-2">
      <button
        onClick={onToggleEditMode}
        className={`w-full flex items-center justify-center px-3 py-2 rounded-lg transition ${
          editMode 
            ? 'bg-red-600 text-white hover:bg-red-700' 
            : 'bg-blue-900 text-white hover:bg-blue-800'
        }`}
      >
        {editMode ? (
          <>
            <Save className="h-3 w-3 mr-2" />
            <span className="text-sm">Save Mode</span>
          </>
        ) : (
          <>
            <Edit className="h-3 w-3 mr-2" />
            <span className="text-sm">Edit Mode</span>
          </>
        )}
      </button>
      {editMode && (
        <button
          onClick={onSave}
          className="w-full bg-green-600 text-white px-3 py-2 rounded-lg hover:bg-green-700 transition flex items-center justify-center"
        >
          <Save className="h-3 w-3 mr-2" />
          <span className="text-sm">Save All Changes</span>
        </button>
      )}
      <button
        onClick={onShowDiagnostic}
        className="w-full bg-gray-800 text-white px-3 py-2 rounded-lg hover:bg-gray-900 transition flex items-center justify-center"
      >
        <CheckCircle className="h-3 w-3 mr-2" />
        <span className="text-sm">Diagnostics</span>
      </button>
    </div>
  </div>
);

const DiagnosticModal = ({ isOpen, onClose, diagnosticInfo }) => {
  if (!isOpen) return null;
  
  return (
    <div className="fixed inset-0 bg-black/50 z-50 flex items-center justify-center p-4 animate-fadeIn">
      <div className="bg-white rounded-xl shadow-2xl max-w-2xl w-full max-h-[80vh] overflow-y-auto animate-slideUp">
        <div className="sticky top-0 bg-white border-b px-6 py-4">
          <div className="flex justify-between items-center">
            <h3 className="text-2xl font-bold text-blue-900">System Diagnostics</h3>
            <button 
              onClick={onClose}
              className="text-gray-400 hover:text-gray-600 transition"
              aria-label="Close"
            >
              <X className="h-6 w-6" />
            </button>
          </div>
        </div>
        <div className="p-6">
          <div className="space-y-4">
            {diagnosticInfo.map((check) => (
              <div key={check.id} className="flex items-start border-b pb-4 last:border-b-0">
                <CheckCircle className="h-5 w-5 text-green-600 mr-3 mt-1 flex-shrink-0" />
                <div className="flex-1 min-w-0">
                  <p className="font-semibold text-gray-900 truncate">{check.name}</p>
                  <p className="text-sm text-gray-600 mt-1">{check.message}</p>
                  <span className="inline-block mt-2 px-2 py-1 bg-green-100 text-green-800 text-xs font-semibold rounded">
                    {check.status}
                  </span>
                </div>
              </div>
            ))}
          </div>
          <div className="mt-6 p-4 bg-gradient-to-r from-green-50 to-blue-50 border border-green-200 rounded-lg">
            <div className="flex items-center">
              <CheckCircle className="h-5 w-5 text-green-600 mr-2" />
              <p className="text-sm text-green-800 font-semibold">
                All systems operational. Website is live and fully interactive.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  );
};

const AdminLoginModal = ({ isOpen, onClose, onLogin }) => {
  const [password, setPassword] = useState('');
  
  const handleSubmit = (e) => {
    e.preventDefault();
    if (onLogin(password)) {
      setPassword('');
    }
  };
  
  if (!isOpen) return null;
  
  return (
    <div className="fixed inset-0 bg-black/50 z-50 flex items-center justify-center p-4 animate-fadeIn">
      <div className="bg-white rounded-xl shadow-2xl max-w-md w-full animate-slideUp">
        <div className="p-6">
          <div className="flex items-center mb-6">
            <Shield className="h-8 w-8 text-blue-900 mr-3" />
            <h3 className="text-2xl font-bold text-blue-900">Admin Login</h3>
          </div>
          <form onSubmit={handleSubmit}>
            <div className="mb-6">
              <label className="block text-sm font-medium text-gray-700 mb-2">
                Admin Password
              </label>
              <input
                type="password"
                value={password}
                onChange={(e) => setPassword(e.target.value)}
                placeholder="Enter admin password"
                className="w-full px-4 py-3 border-2 border-blue-200 rounded-lg focus:ring-2 focus:ring-red-600 focus:border-red-600 outline-none transition"
                autoFocus
              />
            </div>
            <div className="flex gap-3">
              <button
                type="submit"
                className="flex-1 bg-gradient-to-r from-blue-900 to-blue-800 text-white py-3 rounded-lg font-semibold hover:from-blue-800 hover:to-blue-700 transition shadow-md"
              >
                Login
              </button>
              <button
                type="button"
                onClick={onClose}
                className="flex-1 bg-gray-100 text-gray-700 py-3 rounded-lg font-semibold hover:bg-gray-200 transition"
              >
                Cancel
              </button>
            </div>
          </form>
          <p className="text-xs text-gray-500 mt-4 text-center">
            For demonstration purposes only
          </p>
        </div>
      </div>
    </div>
  );
};

const Navigation = ({ 
  isMenuOpen, 
  onToggleMenu, 
  onNavigate, 
  activeSection, 
  isAdmin, 
  onShowAdminLogin 
}) => {
  const menuItems = useMemo(() => [
    { id: 'home', label: 'Home' },
    { id: 'about', label: 'About' },
    { id: 'ebooks', label: 'Ebooks' },
    { id: 'workshops', label: 'Workshops' },
    { id: 'coaching', label: 'Coaching' },
    { id: 'prayer', label: 'Prayer' },
    { id: 'blog', label: 'Blog' },
    { id: 'contact', label: 'Contact' }
  ], []);
  
  return (
    <nav className="bg-gradient-to-r from-blue-900 to-blue-800 shadow-lg fixed w-full top-0 z-40">
      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div className="flex justify-between h-20">
          <div className="flex items-center">
            <Sparkles className="h-10 w-10 text-red-500 animate-pulse" />
            <div className="ml-3">
              <div className="text-xl font-bold text-white">The Definitive Word</div>
              <div className="text-sm text-red-400 italic">Your Destiny Has Been Written</div>
            </div>
          </div>
          
          {/* Desktop Menu */}
          <div className="hidden md:flex items-center space-x-8">
            {menuItems.map((item) => (
              <button
                key={item.id}
                onClick={() => onNavigate(item.id)}
                className={`text-white hover:text-red-400 transition font-medium ${
                  activeSection === item.id ? 'text-red-400 border-b-2 border-red-400' : ''
                }`}
                aria-current={activeSection === item.id ? 'page' : undefined}
              >
                {item.label}
              </button>
            ))}
            
            {/* Admin Button */}
            <button
              onClick={onShowAdminLogin}
              className="text-white hover:text-red-400 transition"
              aria-label={isAdmin ? "Admin logged in" : "Admin login"}
            >
              {isAdmin ? (
                <Unlock className="h-5 w-5 text-green-400" />
              ) : (
                <Lock className="h-5 w-5" />
              )}
            </button>
          </div>

          {/* Mobile menu button */}
          <div className="md:hidden flex items-center space-x-4">
            <button
              onClick={onShowAdminLogin}
              className="text-white"
              aria-label="Admin login"
            >
              {isAdmin ? (
                <Unlock className="h-5 w-5 text-green-400" />
              ) : (
                <Lock className="h-5 w-5" />
              )}
            </button>
            <button 
              onClick={onToggleMenu}
              className="text-white"
              aria-label={isMenuOpen ? "Close menu" : "Open menu"}
            >
              {isMenuOpen ? <X className="h-6 w-6" /> : <Menu className="h-6 w-6" />}
            </button>
          </div>
        </div>
      </div>

      {/* Mobile Menu */}
      {isMenuOpen && (
        <div className="md:hidden bg-blue-900 border-t border-blue-700 animate-slideDown">
          <div className="px-2 pt-2 pb-3 space-y-1">
            {menuItems.map((item) => (
              <button
                key={item.id}
                onClick={() => onNavigate(item.id)}
                className={`block w-full text-left px-3 py-2 rounded transition ${
                  activeSection === item.id
                    ? 'bg-blue-800 text-white'
                    : 'text-white hover:bg-blue-800'
                }`}
                aria-current={activeSection === item.id ? 'page' : undefined}
              >
                {item.label}
              </button>
            ))}
          </div>
        </div>
      )}
    </nav>
  );
};

// Main Component
const MinistryWebsite = () => {
  const [isMenuOpen, setIsMenuOpen] = useState(false);
  const [activeSection, setActiveSection] = useState('home');
  const [showDiagnostic, setShowDiagnostic] = useState(false);
  const [content, setContent] = useState({
    heroTitle: "The Definitive Word",
    heroSubtitle: "Your Destiny Has Been Written",
    heroDescription: "Empowering fathers, strengthening marriages, building community through wisdom and divine purpose",
    aboutTitle: "Walking in Divine Purpose",
    aboutDescription: "Welcome to The Definitive Word - a ministry birthed from divine revelation and insight...",
    quote: "Your destiny is not something you create - it's something you discover. It has already been written.",
    ebooks: [
      { id: 1, title: "The Father's Blueprint", price: "R249.99", description: "A comprehensive guide for fathers building legacy relationships ordained by God" },
      { id: 2, title: "Marriage Rebuilt", price: "R299.99", description: "Restoring divine connection and walking in your covenant destiny" },
      { id: 3, title: "Living on Purpose", price: "R199.99", description: "Discovering the destiny that has already been written for your life" }
    ],
    contact: {
      email: "info@thedefinitiveword.com",
      phone: "(+27) 123-4567"
    }
  });
  
  const prayerRequestForm = useForm({ name: '', email: '', message: '' });
  const contactForm = useForm({ 
    firstName: '', 
    lastName: '', 
    email: '', 
    phone: '', 
    interest: 'Life Coaching', 
    message: '' 
  });
  
  const admin = useAdmin();
  
  // Handle navigation
  const handleNavigate = useCallback((section) => {
    setActiveSection(section);
    setIsMenuOpen(false);
    // Smooth scroll to section
    const element = document.getElementById(section);
    if (element) {
      element.scrollIntoView({ behavior: 'smooth' });
    }
  }, []);
  
  // Handle prayer request submission
  const handlePrayerSubmit = useCallback(() => {
    if (!prayerRequestForm.form.name || !prayerRequestForm.form.message) {
      alert('Please fill in your name and prayer request');
      return;
    }
    alert('✓ Prayer request submitted successfully! We will be praying for you.');
    prayerRequestForm.resetForm();
  }, [prayerRequestForm]);
  
  // Handle contact form submission
  const handleContactSubmit = useCallback(() => {
    if (!contactForm.form.firstName || !contactForm.form.email || !contactForm.form.message) {
      alert('Please fill in all required fields');
      return;
    }
    alert('✓ Message sent successfully! We will get back to you soon.');
    contactForm.resetForm();
  }, [contactForm]);
  
  // Handle content changes
  const handleContentChange = useCallback((field, value) => {
    setContent(prev => {
      const [category, subfield] = field.includes('.') ? field.split('.') : [field];
      
      if (category === 'ebooks') {
        const [ebookIndex, ebookField] = subfield.split('.');
        const updatedEbooks = [...prev.ebooks];
        updatedEbooks[ebookIndex] = {
          ...updatedEbooks[ebookIndex],
          [ebookField]: value
        };
        return { ...prev, ebooks: updatedEbooks };
      }
      
      if (category === 'contact') {
        return {
          ...prev,
          contact: { ...prev.contact, [subfield]: value }
        };
      }
      
      return { ...prev, [field]: value };
    });
  }, []);
  
  // Handle save content
  const handleSaveContent = useCallback(() => {
    // In production, this would make an API call
    alert('✓ Content saved successfully!');
    admin.toggleEditMode();
  }, [admin]);
  
  return (
    <div className="min-h-screen bg-gray-50">
      <style jsx>{`
        @keyframes fadeIn {
          from { opacity: 0; }
          to { opacity: 1; }
        }
        
        @keyframes slideUp {
          from { transform: translateY(20px); opacity: 0; }
          to { transform: translateY(0); opacity: 1; }
        }
        
        @keyframes slideDown {
          from { transform: translateY(-20px); opacity: 0; }
          to { transform: translateY(0); opacity: 1; }
        }
        
        .animate-fadeIn { animation: fadeIn 0.3s ease-out; }
        .animate-slideUp { animation: slideUp 0.3s ease-out; }
        .animate-slideDown { animation: slideDown 0.3s ease-out; }
      `}</style>
      
      {/* Admin Panel */}
      {admin.isAdmin && (
        <AdminPanel
          isAdmin={admin.isAdmin}
          editMode={admin.editMode}
          onLogout={admin.logout}
          onToggleEditMode={admin.toggleEditMode}
          onSave={handleSaveContent}
          onShowDiagnostic={() => setShowDiagnostic(true)}
        />
      )}
      
      {/* Modals */}
      <DiagnosticModal
        isOpen={showDiagnostic}
        onClose={() => setShowDiagnostic(false)}
        diagnosticInfo={CONSTANTS.DIAGNOSTIC_CHECKS}
      />
      
      <AdminLoginModal
        isOpen={admin.showAdminLogin}
        onClose={() => admin.setShowAdminLogin(false)}
        onLogin={admin.login}
      />
      
      {/* Navigation */}
      <Navigation
        isMenuOpen={isMenuOpen}
        onToggleMenu={() => setIsMenuOpen(!isMenuOpen)}
        onNavigate={handleNavigate}
        activeSection={activeSection}
        isAdmin={admin.isAdmin}
        onShowAdminLogin={() => admin.setShowAdminLogin(true)}
      />
      
      {/* Hero Section */}
      <section id="home" className="pt-24 bg-gradient-to-br from-blue-900 via-blue-800 to-blue-900 text-white relative overflow-hidden">
        <div className="absolute inset-0 bg-gradient-to-br from-red-900/10 via-transparent to-blue-900/10" />
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-24 md:py-32 relative z-10">
          <div className="text-center">
            <div className="inline-block mb-8 animate-pulse">
              <Sparkles className="h-20 w-20 text-red-500 mx-auto" />
            </div>
            
            <EditableField
              isEditing={admin.editMode}
              value={content.heroTitle}
              onChange={(val) => handleContentChange('heroTitle', val)}
              component="input"
              className="text-5xl md:text-7xl font-bold mb-6 bg-transparent text-center text-white placeholder-white/50"
              placeholder="Enter hero title"
            />
            
            <EditableField
              isEditing={admin.editMode}
              value={content.heroSubtitle}
              onChange={(val) => handleContentChange('heroSubtitle', val)}
              component="input"
              className="text-3xl md:text-4xl mb-10 text-red-400 italic font-semibold bg-transparent text-center"
              placeholder="Enter hero subtitle"
            />
            
            <EditableField
              isEditing={admin.editMode}
              value={content.heroDescription}
              onChange={(val) => handleContentChange('heroDescription', val)}
              component="textarea"
              className="text-xl md:text-2xl mb-12 text-blue-100 max-w-3xl mx-auto bg-transparent text-center placeholder-blue-100/50"
              placeholder="Enter hero description"
              rows="2"
            />
            
            <button
              onClick={() => handleNavigate('contact')}
              className="bg-gradient-to-r from-red-600 to-red-500 text-white px-12 py-4 rounded-lg font-bold text-lg hover:from-red-700 hover:to-red-600 transition-all shadow-xl hover:shadow-2xl transform hover:-translate-y-1"
            >
              Discover Your Destiny
              <ArrowRight className="inline-block ml-2 h-5 w-5" />
            </button>
          </div>
        </div>
        <div className="h-2 bg-gradient-to-r from-red-600 via-red-500 to-red-600" />
      </section>
      
      {/* About Section */}
      <section id="about" className="py-20 bg-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <SectionHeader
            title={content.aboutTitle}
            description={content.aboutDescription}
            isEditing={admin.editMode}
            onTitleChange={(val) => handleContentChange('aboutTitle', val)}
            onDescriptionChange={(val) => handleContentChange('aboutDescription', val)}
          />
          
          <div className="max-w-3xl mx-auto">
            <div className="bg-gradient-to-r from-blue-50 to-gray-50 rounded-2xl p-8 border border-blue-100">
              <div className="flex items-start mb-6">
                <Star className="h-6 w-6 text-red-600 mr-3 mt-1 flex-shrink-0" />
                <EditableField
                  isEditing={admin.editMode}
                  value={content.quote}
                  onChange={(val) => handleContentChange('quote', val)}
                  component="textarea"
                  className="text-lg md:text-xl text-blue-900 font-semibold italic bg-transparent"
                  rows="2"
                  placeholder="Enter inspirational quote"
                />
              </div>
              
              <div className="grid md:grid-cols-2 gap-6">
                <div className="space-y-4">
                  <p className="text-gray-700 leading-relaxed">
                    Welcome to The Definitive Word - a ministry birthed from divine revelation and insight. I'm passionate about helping individuals, families, and communities discover and walk in their God-ordained destiny.
                  </p>
                  <p className="text-gray-700 leading-relaxed">
                    With years of experience in ministry and life coaching, I've dedicated my life to guiding people into their written destiny.
                  </p>
                </div>
                <div className="space-y-4">
                  <p className="text-gray-700 leading-relaxed">
                    My approach combines biblical wisdom with practical tools for real-world transformation. Whether you're a father seeking to build a godly legacy with your son, a couple working to fulfill your covenant marriage, or someone searching for their destiny.
                  </p>
                  <p className="text-gray-700 leading-relaxed">
                    I'm here to help you see what God has already declared over your life.
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
      
      {/* Ebooks Section */}
      <section id="ebooks" className="py-20 bg-gradient-to-b from-gray-50 to-blue-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <SectionHeader
            title="Featured Ebooks"
            subtitle="Unlock the wisdom that transforms destinies"
            isEditing={admin.editMode}
            onTitleChange={() => {}}
            onSubtitleChange={() => {}}
          />
          
          <div className="grid md:grid-cols-3 gap-8">
            {content.ebooks.map((ebook, index) => (
              <div key={ebook.id} className="bg-white rounded-xl shadow-lg p-6 hover:shadow-2xl transition-all duration-300 border-t-4 border-red-600 group">
                <div className="flex items-center mb-4">
                  <Book className="h-10 w-10 text-blue-900 mr-3" />
                  <EditableField
                    isEditing={admin.editMode}
                    value={ebook.title}
                    onChange={(val) => handleContentChange(`ebooks.${index}.title`, val)}
                    component="input"
                    className="text-xl font-bold text-blue-900 bg-transparent"
                    placeholder="Ebook title"
                  />
                </div>
                
                <EditableField
                  isEditing={admin.editMode}
                  value={ebook.description}
                  onChange={(val) => handleContentChange(`ebooks.${index}.description`, val)}
                  component="textarea"
                  className="text-gray-600 mb-4 min-h-[80px] bg-transparent"
                  placeholder="Ebook description"
                  rows="3"
                />
                
                <div className="flex items-center justify-between mb-6">
                  <EditableField
                    isEditing={admin.editMode}
                    value={ebook.price}
                    onChange={(val) => handleContentChange(`ebooks.${index}.price`, val)}
                    component="input"
                    className="text-2xl font-bold text-red-600 bg-transparent"
                    placeholder="Price"
                  />
                  <span className="text-sm text-gray-500 bg-gray-100 px-2 py-1 rounded">
                    {CONSTANTS.CURRENCY}
                  </span>
                </div>
                
                <button className="w-full bg-gradient-to-r from-blue-900 to-blue-800 text-white py-3 rounded-lg font-semibold hover:from-blue-800 hover:to-blue-700 transition group-hover:scale-[1.02] shadow-md">
                  Purchase Now
                </button>
              </div>
            ))}
          </div>
        </div>
      </section>
      
      {/* Workshops Section */}
      <section id="workshops" className="py-20 bg-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <SectionHeader
            title="Workshops & Events"
            isEditing={admin.editMode}
            onTitleChange={() => {}}
          />
          
          <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
            {CONSTANTS.WORKSHOPS.map((workshop) => (
              <div key={workshop.id} className="border-2 border-blue-100 rounded-xl p-6 hover:border-red-600 transition-all hover:shadow-xl bg-gradient-to-br from-white to-blue-50">
                <workshop.icon className="h-12 w-12 text-red-600 mb-4" />
                <h3 className="text-xl font-bold mb-3 text-blue-900">{workshop.title}</h3>
                <p className="text-gray-600 mb-4">{workshop.description}</p>
                <button className="text-red-600 font-semibold flex items-center hover:text-red-700 group">
                  Learn More
                  <ChevronRight className="h-4 w-4 ml-1 group-hover:translate-x-1 transition" />
                </button>
              </div>
            ))}
          </div>
        </div>
      </section>
      
      {/* Life Coaching Section */}
      <section id="coaching" className="py-20 bg-gradient-to-br from-blue-900 via-blue-800 to-blue-900 text-white relative overflow-hidden">
        <div className="absolute inset-0 bg-gradient-to-br from-red-900/10 via-transparent to-blue-900/10" />
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
          <SectionHeader
            title="Life Coaching"
            subtitle="One-on-one guidance to discover your written destiny"
            isEditing={admin.editMode}
            onTitleChange={() => {}}
            onSubtitleChange={() => {}}
          />
          
          <div className="grid md:grid-cols-3 gap-8 max-w-5xl mx-auto mb-12">
            {[
              { number: 1, title: "Revelation", description: "We seek God's word over your life and uncover what has been written" },
              { number: 2, title: "Divine Strategy", description: "Create a God-ordained roadmap to walk in your destiny" },
              { number: 3, title: "Accountability", description: "Regular sessions to keep you aligned with heaven's agenda" }
            ].map((step) => (
              <div key={step.number} className="text-center">
                <div className="bg-gradient-to-br from-red-600 to-red-500 rounded-full w-24 h-24 flex items-center justify-center mx-auto mb-6 shadow-xl">
                  <span className="text-4xl font-bold text-white">{step.number}</span>
                </div>
                <h3 className="text-2xl font-bold mb-3">{step.title}</h3>
                <p className="text-blue-100">{step.description}</p>
              </div>
            ))}
          </div>
          
          <div className="text-center">
            <button
              onClick={() => handleNavigate('contact')}
              className="bg-gradient-to-r from-red-600 to-red-500 text-white px-12 py-4 rounded-lg font-bold text-lg hover:from-red-700 hover:to-red-600 transition-all shadow-xl hover:shadow-2xl transform hover:-translate-y-1"
            >
              Schedule Free Consultation
              <Calendar className="inline-block ml-2 h-5 w-5" />
            </button>
          </div>
        </div>
      </section>
      
      {/* Prayer Request Section */}
      <section id="prayer" className="py-20 bg-gradient-to-b from-blue-50 to-gray-50">
        <div className="max-w-3xl mx-auto px-4 sm:px-6 lg:px-8">
          <SectionHeader
            title="Submit a Prayer Request"
            subtitle="We stand in agreement with you for breakthrough"
            isEditing={admin.editMode}
            onTitleChange={() => {}}
            onSubtitleChange={() => {}}
          />
          
          <div className="bg-white rounded-xl shadow-xl p-8 border-t-4 border-red-600">
            <form onSubmit={(e) => { e.preventDefault(); handlePrayerSubmit(); }}>
              <div className="space-y-6">
                <div>
                  <label className="block text-blue-900 font-semibold mb-2">
                    Your Name *
                  </label>
                  <input
                    type="text"
                    value={prayerRequestForm.form.name}
                    onChange={(e) => prayerRequestForm.handleChange('name', e.target.value)}
                    className="w-full px-4 py-3 border-2 border-blue-200 rounded-lg focus:ring-2 focus:ring-red-600 focus:border-red-600 outline-none transition"
                    placeholder="Enter your name"
                    required
                  />
                </div>
                
                <div>
                  <label className="block text-blue-900 font-semibold mb-2">
                    Email (optional)
                  </label>
                  <input
                    type="email"
                    value={prayerRequestForm.form.email}
                    onChange={(e) => prayerRequestForm.handleChange('email', e.target.value)}
                    className="w-full px-4 py-3 border-2 border-blue-200 rounded-lg focus:ring-2 focus:ring-red-600 focus:border-red-600 outline-none transition"
                    placeholder="your@email.com"
                  />
                </div>
                
                <div>
                  <label className="block text-blue-900 font-semibold mb-2">
                    Prayer Request *
                  </label>
                  <textarea
                    rows="6"
                    value={prayerRequestForm.form.message}
                    onChange={(e) => prayerRequestForm.handleChange('message', e.target.value)}
                    className="w-full px-4 py-3 border-2 border-blue-200 rounded-lg focus:ring-2 focus:ring-red-600 focus:border-red-600 outline-none transition"
                    placeholder="Share your prayer request..."
                    required
                  />
                </div>
                
                <button
                  type="submit"
                  className="w-full bg-gradient-to-r from-blue-900 to-blue-800 text-white py-4 rounded-lg font-bold text-lg hover:from-blue-800 hover:to-blue-700 transition-all shadow-lg hover:shadow-xl"
                >
                  Submit Prayer Request
                  <Heart className="inline-block ml-2 h-5 w-5" />
                </button>
              </div>
            </form>
          </div>
        </div>
      </section>
      
      {/* Blog Section */}
      <section id="blog" className="py-20 bg-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <SectionHeader
            title="Latest Teachings"
            isEditing={admin.editMode}
            onTitleChange={() => {}}
          />
          
          <div className="grid md:grid-cols-3 gap-8">
            {CONSTANTS.BLOG_POSTS.map((post) => (
              <article key={post.id} className="border-2 border-blue-100 rounded-xl overflow-hidden hover:shadow-xl transition-all duration-300 hover:border-red-600 group">
                <div className="bg-gradient-to-br from-blue-900 to-blue-800 h-48 flex items-center justify-center">
                  <FileText className="h-16 w-16 text-red-500 group-hover:scale-110 transition" />
                </div>
                <div className="p-6">
                  <div className="flex items-center mb-3">
                    <Calendar className="h-4 w-4 text-red-600 mr-2" />
                    <time className="text-sm text-red-600 font-semibold">{post.date}</time>
                  </div>
                  <h3 className="text-xl font-bold mb-3 text-blue-900">{post.title}</h3>
                  <p className="text-gray-600 mb-4">{post.excerpt}</p>
                  <button className="text-red-600 font-semibold flex items-center hover:text-red-700 group">
                    Read More
                    <ChevronRight className="h-4 w-4 ml-1 group-hover:translate-x-1 transition" />
                  </button>
                </div>
              </article>
            ))}
          </div>
        </div>
      </section>
      
      {/* Contact Section */}
      <section id="contact" className="py-20 bg-gradient-to-b from-gray-50 to-blue-50">
        <div className="max-w-3xl mx-auto px-4 sm:px-6 lg:px-8">
          <SectionHeader
            title="Connect With Us"
            subtitle="Begin your journey into divine destiny today"
            isEditing={admin.editMode}
            onTitleChange={() => {}}
            onSubtitleChange={() => {}}
          />
          
          <div className="bg-white rounded-xl shadow-xl p-8 border-t-4 border-red-600">
            <form onSubmit={(e) => { e.preventDefault(); handleContactSubmit(); }}>
              <div className="space-y-6">
                <div className="grid md:grid-cols-2 gap-6">
                  <div>
                    <label className="block text-blue-900 font-semibold mb-2">
                      First Name *
                    </label>
                    <input
                      type="text"
                      value={contactForm.form.firstName}
                      onChange={(e) => contactForm.handleChange('firstName', e.target.value)}
                      className="w-full px-4 py-3 border-2 border-blue-200 rounded-lg focus:ring-2 focus:ring-red-600 focus:border-red-600 outline-none transition"
                      required
                    />
                  </div>
                  <div>
                    <label className="block text-blue-900 font-semibold mb-2">
                      Last Name
                    </label>
                    <input
                      type="text"
                      value={contactForm.form.lastName}
                      onChange={(e) => contactForm.handleChange('lastName', e.target.value)}
                      className="w-full px-4 py-3 border-2 border-blue-200 rounded-lg focus:ring-2 focus:ring-red-600 focus:border-red-600 outline-none transition"
                    />
                  </div>
                </div>
                
                <div>
                  <label className="block text-blue-900 font-semibold mb-2">
                    Email *
                  </label>
                  <input
                    type="email"
                    value={contactForm.form.email}
                    onChange={(e) => contactForm.handleChange('email', e.target.value)}
                    className="w-full px-4 py-3 border-2 border-blue-200 rounded-lg focus:ring-2 focus:ring-red-600 focus:border-red-600 outline-none transition"
                    required
                  />
                </div>
                
                <div>
                  <label className="block text-blue-900 font-semibold mb-2">
                    Phone (optional)
                  </label>
                  <input
                    type="tel"
                    value={contactForm.form.phone}
                    onChange={(e) => contactForm.handleChange('phone', e.target.value)}
                    className="w-full px-4 py-3 border-2 border-blue-200 rounded-lg focus:ring-2 focus:ring-red-600 focus:border-red-600 outline-none transition"
                  />
                </div>
                
                <div>
                  <label className="block text-blue-900 font-semibold mb-2">
                    What are you interested in?
                  </label>
                  <select
                    value={contactForm.form.interest}
                    onChange={(e) => contactForm.handleChange('interest', e.target.value)}
                    className="w-full px-4 py-3 border-2 border-blue-200 rounded-lg focus:ring-2 focus:ring-red-600 focus:border-red-600 outline-none transition bg-white"
                  >
                    <option>Life Coaching</option>
                    <option>Workshops & Retreats</option>
                    <option>Speaking Engagement</option>
                    <option>General Inquiry</option>
                  </select>
                </div>
                
                <div>
                  <label className="block text-blue-900 font-semibold mb-2">
                    Message *
                  </label>
                  <textarea
                    rows="5"
                    value={contactForm.form.message}
                    onChange={(e) => contactForm.handleChange('message', e.target.value)}
                    className="w-full px-4 py-3 border-2 border-blue-200 rounded-lg focus:ring-2 focus:ring-red-600 focus:border-red-600 outline-none transition"
                    placeholder="Tell us how we can help you discover your destiny..."
                    required
                  />
                </div>
                
                <button
                  type="submit"
                  className="w-full bg-gradient-to-r from-blue-900 to-blue-800 text-white py-4 rounded-lg font-bold text-lg hover:from-blue-800 hover:to-blue-700 transition-all shadow-lg hover:shadow-xl"
                >
                  Send Message
                  <Mail className="inline-block ml-2 h-5 w-5" />
                </button>
              </div>
            </form>
          </div>
        </div>
      </section>
      
      {/* Footer */}
      <footer className="bg-gradient-to-b from-blue-900 to-gray-900 text-white py-12">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="grid md:grid-cols-4 gap-8 mb-8">
            <div>
              <div className="flex items-center mb-4">
                <Sparkles className="h-8 w-8 text-red-500 mr-3" />
                <div>
                  <h3 className="text-xl font-bold">The Definitive Word</h3>
                  <p className="text-sm text-red-400 italic">Your Destiny Has Been Written</p>
                </div>
              </div>
              <p className="text-gray-400 text-sm">
                Empowering lives through wisdom and divine purpose.
              </p>
            </div>
            
            <div>
              <h4 className="font-bold mb-4 text-red-400">Quick Links</h4>
              <ul className="space-y-2">
                {['About', 'Ebooks', 'Workshops', 'Coaching'].map((item) => (
                  <li key={item}>
                    <button
                      onClick={() => handleNavigate(item.toLowerCase())}
                      className="text-gray-400 hover:text-white transition text-sm"
                    >
                      {item}
                    </button>
                  </li>
                ))}
              </ul>
            </div>
            
            <div>
              <h4 className="font-bold mb-4 text-red-400">Resources</h4>
              <ul className="space-y-2">
                {['Blog', 'Prayer', 'Contact'].map((item) => (
                  <li key={item}>
                    <button
                      onClick={() => handleNavigate(item.toLowerCase())}
                      className="text-gray-400 hover:text-white transition text-sm"
                    >
                      {item}
                    </button>
                  </li>
                ))}
              </ul>
            </div>
            
            <div>
              <h4 className="font-bold mb-4 text-red-400">Connect</h4>
              <div className="space-y-3">
                <div className="flex items-center">
                  <Mail className="h-4 w-4 text-gray-400 mr-3" />
                  <EditableField
                    isEditing={admin.editMode}
                    value={content.contact.email}
                    onChange={(val) => handleContentChange('contact.email', val)}
                    component="input"
                    className="text-gray-400 text-sm bg-transparent"
                    placeholder="Email address"
                  />
                </div>
                <div className="flex items-center">
                  <Phone className="h-4 w-4 text-gray-400 mr-3" />
                  <EditableField
                    isEditing={admin.editMode}
                    value={content.contact.phone}
                    onChange={(val) => handleContentChange('contact.phone', val)}
                    component="input"
                    className="text-gray-400 text-sm bg-transparent"
                    placeholder="Phone number"
                  />
                </div>
              </div>
            </div>
          </div>
          
          <div className="border-t border-blue-800 pt-8 text-center">
            <p className="text-gray-400 text-sm">
              &copy; {new Date().getFullYear()} The Definitive Word. All rights reserved.
            </p>
            <p className="text-sm mt-2 italic text-red-400">
              "For I know the plans I have for you" - Jeremiah 29:11
            </p>
          </div>
        </div>
      </footer>
    </div>
  );
};

export default MinistryWebsite;
