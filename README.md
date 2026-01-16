import React, { useState, useEffect, useRef } from 'react';
import { Code, Palette, Database, Blocks, Mail, Linkedin, Facebook, Instagram, Globe, ChevronRight, Sparkles, ExternalLink, Award, Target, Zap, Users, Briefcase, Star } from 'lucide-react';

const AnimatedPortfolio = () => {
  const [activeCard, setActiveCard] = useState(null);
  const [mousePos, setMousePos] = useState({ x: 0, y: 0 });
  const [scrollY, setScrollY] = useState(0);
  const containerRef = useRef(null);

  useEffect(() => {
    const handleMouseMove = (e) => {
      if (containerRef.current) {
        const rect = containerRef.current.getBoundingClientRect();
        setMousePos({
          x: (e.clientX - rect.left - rect.width / 2) / 20,
          y: (e.clientY - rect.top - rect.height / 2) / 20
        });
      }
    };

    const handleScroll = () => {
      setScrollY(window.scrollY);
    };

    window.addEventListener('mousemove', handleMouseMove);
    window.addEventListener('scroll', handleScroll);
    return () => {
      window.removeEventListener('mousemove', handleMouseMove);
      window.removeEventListener('scroll', handleScroll);
    };
  }, []);

  const skills = [
    {
      id: 'design',
      icon: Palette,
      title: 'Design That Tells Stories',
      color: 'from-purple-500 via-pink-500 to-purple-600',
      tools: ['Photoshop', 'Illustrator', 'CorelDRAW', 'Sketch'],
      description: 'Brand identities • Logos • UI/UX • Marketing materials',
      details: 'Not just pretty pixels - strategic design that converts'
    },
    {
      id: 'web',
      icon: Code,
      title: 'Code That Powers Ideas',
      color: 'from-blue-500 via-cyan-500 to-blue-600',
      tools: ['React', 'Vue', 'JavaScript', 'PHP', 'Java', 'Kotlin'],
      description: 'Web apps • E-commerce • CMS • Mobile-responsive',
      details: 'Building digital products from concept to launch'
    },
    {
      id: 'data',
      icon: Database,
      title: 'AI & Data Solutions',
      color: 'from-green-500 via-emerald-500 to-green-600',
      tools: ['Python', 'TensorFlow', 'SQL', 'Machine Learning'],
      description: 'ML models • Data analysis • Predictive algorithms',
      details: 'Making machines work smarter, not harder'
    },
    {
      id: 'blockchain',
      icon: Blocks,
      title: 'Blockchain Innovation',
      color: 'from-orange-500 via-red-500 to-orange-600',
      tools: ['Smart Contracts', 'DeFi', 'Web3', 'Solidity'],
      description: 'Smart contracts • DeFi apps • Web3 integration',
      details: 'Building the future of decentralized tech'
    }
  ];

  const socialLinks = [
    { icon: Globe, label: 'Portfolio', url: 'https://www.emonisamuel.co.ke', color: 'from-indigo-500 to-purple-500' },
    { icon: Linkedin, label: 'LinkedIn', url: 'https://www.linkedin.com/in/samuelemoni/', color: 'from-blue-600 to-blue-700' },
    { icon: Instagram, label: 'Instagram', url: 'https://www.instagram.com/Emoni_Samuel/', color: 'from-pink-500 to-purple-600' },
    { icon: Facebook, label: 'Facebook', url: 'https://facebook.com/profile.php?id=61580678667530', color: 'from-blue-500 to-blue-600' },
    { icon: Mail, label: 'Email', url: 'mailto:emonisamuel54@gmail.com', color: 'from-red-500 to-orange-500' }
  ];

  const highlights = [
    { icon: Award, text: '4+ Years Design Experience', color: 'text-purple-400' },
    { icon: Code, text: 'Full-Stack Developer', color: 'text-cyan-400' },
    { icon: Target, text: 'BSc Applied CS - Chuka University', color: 'text-green-400' },
    { icon: Zap, text: 'Available for Projects', color: 'text-yellow-400' }
  ];

  const whyFollow = [
    { icon: Sparkles, title: 'Real Projects', desc: 'Design breakdowns, code tutorials, case studies' },
    { icon: Users, title: 'Learn Together', desc: 'Free resources, honest lessons, collaboration' },
    { icon: Star, title: 'Fresh Content', desc: 'Regular updates across all platforms' }
  ];

  const goals = [
    'Master React & Next.js',
    '3 Full-Stack SaaS Apps',
    'AI-Powered Tools',
    'DeFi Dashboard',
    '24 Technical Articles',
    'Open-Source Contributions'
  ];

  return (
    <div 
      ref={containerRef}
      className="min-h-screen bg-gradient-to-br from-slate-950 via-purple-950 to-slate-950 text-white overflow-x-hidden"
    >
      <style>{`
        @keyframes float {
          0%, 100% { transform: translateY(0) translateX(0); }
          50% { transform: translateY(-20px) translateX(10px); }
        }
        @keyframes slideInUp {
          from { transform: translateY(50px); opacity: 0; }
          to { transform: translateY(0); opacity: 1; }
        }
        @keyframes slideInLeft {
          from { transform: translateX(-50px); opacity: 0; }
          to { transform: translateX(0); opacity: 1; }
        }
        @keyframes slideInRight {
          from { transform: translateX(50px); opacity: 0; }
          to { transform: translateX(0); opacity: 1; }
        }
        @keyframes glow {
          0%, 100% { box-shadow: 0 0 20px rgba(147, 51, 234, 0.5); }
          50% { box-shadow: 0 0 40px rgba(147, 51, 234, 0.8); }
        }
        @keyframes pulse {
          0%, 100% { opacity: 1; }
          50% { opacity: 0.5; }
        }
        @keyframes spin {
          from { transform: rotate(0deg); }
          to { transform: rotate(360deg); }
        }
        @keyframes gradient {
          0% { background-position: 0% 50%; }
          50% { background-position: 100% 50%; }
          100% { background-position: 0% 50%; }
        }
        .animate-float { animation: float 6s ease-in-out infinite; }
        .animate-slideInUp { animation: slideInUp 0.6s ease-out forwards; }
        .animate-slideInLeft { animation: slideInLeft 0.6s ease-out forwards; }
        .animate-slideInRight { animation: slideInRight 0.6s ease-out forwards; }
        .animate-glow { animation: glow 3s ease-in-out infinite; }
        .animate-pulse { animation: pulse 2s ease-in-out infinite; }
        .animate-spin-slow { animation: spin 20s linear infinite; }
        .animate-gradient { animation: gradient 8s ease infinite; background-size: 200% 200%; }
        
        .glass {
          background: rgba(255, 255, 255, 0.05);
          backdrop-filter: blur(10px);
          border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .glass-strong {
          background: rgba(255, 255, 255, 0.1);
          backdrop-filter: blur(20px);
          border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .hover-lift {
          transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .hover-lift:hover {
          transform: translateY(-10px);
          box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }
      `}</style>

      {/* Animated background particles */}
      <div className="fixed inset-0 overflow-hidden pointer-events-none">
        {[...Array(30)].map((_, i) => (
          <div
            key={i}
            className="absolute w-2 h-2 bg-white rounded-full opacity-20"
            style={{
              left: `${Math.random() * 100}%`,
              top: `${Math.random() * 100}%`,
              animation: `float ${5 + Math.random() * 10}s linear infinite`,
              animationDelay: `${Math.random() * 5}s`
            }}
          />
        ))}
        
        {/* Gradient orbs */}
        <div className="absolute top-1/4 left-1/4 w-96 h-96 bg-purple-500 rounded-full filter blur-3xl opacity-20 animate-pulse" />
        <div className="absolute bottom-1/4 right-1/4 w-96 h-96 bg-cyan-500 rounded-full filter blur-3xl opacity-20 animate-pulse" style={{ animationDelay: '1s' }} />
      </div>

      <div className="max-w-7xl mx-auto px-6 py-12 relative z-10">
        {/* Hero Section */}
        <div 
          className="text-center mb-20 animate-slideInUp"
          style={{
            transform: `translate(${mousePos.x}px, ${mousePos.y}px)`,
            transition: 'transform 0.2s ease-out'
          }}
        >
          <div className="inline-flex items-center gap-2 mb-6 px-6 py-3 glass rounded-full hover-lift animate-glow">
            <div className="w-3 h-3 bg-green-500 rounded-full animate-pulse" />
            <span className="text-sm font-medium">Available for Projects</span>
            <Sparkles className="w-4 h-4 text-yellow-400" />
          </div>
          
          <h1 className="text-7xl font-bold mb-4 animate-gradient bg-gradient-to-r from-purple-400 via-pink-400 to-cyan-400 bg-clip-text text-transparent">
            Samuel Emoni
          </h1>
          
          <div className="flex flex-wrap justify-center gap-3 mb-6">
            {['Creative Technologist', 'Designer', 'Developer', 'Problem Solver'].map((role, i) => (
              <span 
                key={i}
                className="px-4 py-2 glass rounded-full text-sm animate-slideInUp hover-lift"
                style={{ animationDelay: `${i * 0.1}s` }}
              >
                {role}
              </span>
            ))}
          </div>
          
          <p className="text-xl text-gray-300 max-w-3xl mx-auto mb-8 animate-slideInUp" style={{ animationDelay: '0.2s' }}>
            I don't just code. I don't just design. <span className="text-cyan-400 font-semibold">I create experiences that matter.</span>
          </p>

          {/* Highlights */}
          <div className="grid grid-cols-2 md:grid-cols-4 gap-4 max-w-4xl mx-auto mb-12">
            {highlights.map((item, i) => {
              const Icon = item.icon;
              return (
                <div 
                  key={i}
                  className="glass-strong rounded-xl p-4 hover-lift animate-slideInUp"
                  style={{ animationDelay: `${0.3 + i * 0.1}s` }}
                >
                  <Icon className={`w-6 h-6 ${item.color} mx-auto mb-2`} />
                  <p className="text-xs text-gray-300">{item.text}</p>
                </div>
              );
            })}
          </div>

          {/* Social Links */}
          <div className="flex flex-wrap justify-center gap-4">
            {socialLinks.map((link, i) => {
              const Icon = link.icon;
              return (
                <a
                  key={i}
                  href={link.url}
                  target="_blank"
                  rel="noopener noreferrer"
                  className="group relative"
                  style={{ animationDelay: `${0.5 + i * 0.1}s` }}
                >
                  <div className={`glass-strong rounded-2xl px-6 py-4 hover-lift flex items-center gap-3 animate-slideInUp`}>
                    <Icon className="w-5 h-5" />
                    <span className="font-medium">{link.label}</span>
                    <ExternalLink className="w-4 h-4 opacity-0 group-hover:opacity-100 transition-opacity" />
                  </div>
                  <div className={`absolute inset-0 bg-gradient-to-r ${link.color} rounded-2xl opacity-0 group-hover:opacity-20 transition-opacity blur-xl`} />
                </a>
              );
            })}
          </div>
        </div>

        {/* Why Follow Me Section */}
        <div className="mb-20">
          <h2 className="text-4xl font-bold text-center mb-12 animate-slideInUp">
            <span className="bg-gradient-to-r from-purple-400 to-cyan-400 bg-clip-text text-transparent">
              Why Follow My Journey?
            </span>
          </h2>
          
          <div className="grid md:grid-cols-3 gap-6">
            {whyFollow.map((item, i) => {
              const Icon = item.icon;
              return (
                <div 
                  key={i}
                  className="glass-strong rounded-2xl p-8 hover-lift animate-slideInUp"
                  style={{ animationDelay: `${i * 0.1}s` }}
                >
                  <div className="w-16 h-16 bg-gradient-to-br from-purple-500 to-cyan-500 rounded-xl flex items-center justify-center mb-4 animate-float">
                    <Icon className="w-8 h-8" />
                  </div>
                  <h3 className="text-2xl font-bold mb-3">{item.title}</h3>
                  <p className="text-gray-400">{item.desc}</p>
                </div>
              );
            })}
          </div>
        </div>

        {/* Skills Grid */}
        <div className="mb-20">
          <h2 className="text-4xl font-bold text-center mb-12 animate-slideInUp">
            <span className="bg-gradient-to-r from-pink-400 to-orange-400 bg-clip-text text-transparent">
              What I Actually Do
            </span>
          </h2>
          
          <div className="grid md:grid-cols-2 gap-8">
            {skills.map((skill, idx) => {
              const Icon = skill.icon;
              return (
                <div
                  key={skill.id}
                  className="group relative animate-slideInUp"
                  style={{ animationDelay: `${idx * 0.15}s` }}
                  onMouseEnter={() => setActiveCard(skill.id)}
                  onMouseLeave={() => setActiveCard(null)}
                >
                  <div className={`
                    glass-strong rounded-3xl p-8 hover-lift h-full
                    transition-all duration-500
                    ${activeCard === skill.id ? 'scale-105' : ''}
                  `}>
                    <div className="relative">
                      <div className={`
                        w-20 h-20 rounded-2xl bg-gradient-to-br ${skill.color}
                        flex items-center justify-center mb-6
                        transition-transform duration-500
                        ${activeCard === skill.id ? 'rotate-12 scale-110' : ''}
                      `}>
                        <Icon className="w-10 h-10 text-white" />
                      </div>
                      
                      <h3 className="text-2xl font-bold mb-2">{skill.title}</h3>
                      <p className="text-sm text-gray-400 mb-4">{skill.details}</p>
                      <p className="text-sm text-cyan-300 mb-6">{skill.description}</p>
                      
                      <div className="flex flex-wrap gap-2">
                        {skill.tools.map((tool, i) => (
                          <span 
                            key={i}
                            className="text-sm px-4 py-2 glass rounded-full border border-white/20 hover:border-white/40 transition-all hover:scale-110"
                          >
                            {tool}
                          </span>
                        ))}
                      </div>
                    </div>
                  </div>
                  
                  {/* Animated border gradient */}
                  <div className={`
                    absolute inset-0 bg-gradient-to-r ${skill.color} rounded-3xl opacity-0 
                    group-hover:opacity-30 transition-opacity blur-xl -z-10
                  `} />
                </div>
              );
            })}
          </div>
        </div>

        {/* 2025 Goals */}
        <div className="mb-20">
          <h2 className="text-4xl font-bold text-center mb-12 animate-slideInUp">
            <span className="bg-gradient-to-r from-green-400 to-blue-400 bg-clip-text text-transparent">
              Mission 2025
            </span>
          </h2>
          
          <div className="glass-strong rounded-3xl p-8 max-w-4xl mx-auto animate-slideInUp hover-lift">
            <div className="grid md:grid-cols-2 gap-4">
              {goals.map((goal, i) => (
                <div 
                  key={i}
                  className="flex items-center gap-3 p-4 glass rounded-xl hover:bg-white/10 transition-all animate-slideInLeft"
                  style={{ animationDelay: `${i * 0.1}s` }}
                >
                  <div className="w-8 h-8 rounded-full bg-gradient-to-r from-green-400 to-cyan-400 flex items-center justify-center flex-shrink-0 animate-pulse">
                    <ChevronRight className="w-5 h-5" />
                  </div>
                  <span className="text-sm">{goal}</span>
                </div>
              ))}
            </div>
          </div>
        </div>

        {/* CTA Section */}
        <div className="text-center glass-strong rounded-3xl p-12 animate-slideInUp hover-lift">
          <Briefcase className="w-16 h-16 mx-auto mb-6 text-purple-400 animate-float" />
          <h2 className="text-4xl font-bold mb-4">
            <span className="bg-gradient-to-r from-purple-400 via-pink-400 to-cyan-400 bg-clip-text text-transparent">
              Let's Build Something Amazing
            </span>
          </h2>
          <p className="text-xl text-gray-300 mb-8 max-w-2xl mx-auto">
            Available for freelance projects, collaborations, and full-time opportunities
          </p>
          
          <div className="flex flex-wrap justify-center gap-4">
            <a
              href="mailto:emonisamuel54@gmail.com"
              className="px-8 py-4 bg-gradient-to-r from-purple-500 to-pink-500 rounded-2xl font-semibold hover:scale-105 transition-transform flex items-center gap-2 hover-lift"
            >
              <Mail className="w-5 h-5" />
              Start a Project
            </a>
            <a
              href="https://www.emonisamuel.co.ke"
              target="_blank"
              rel="noopener noreferrer"
              className="px-8 py-4 glass-strong rounded-2xl font-semibold hover:scale-105 transition-transform flex items-center gap-2 hover-lift"
            >
              <Globe className="w-5 h-5" />
              View Portfolio
            </a>
          </div>
        </div>

        {/* Footer */}
        <div className="text-center mt-12 text-gray-500 text-sm animate-slideInUp">
          <p className="mb-2">© 2025 Samuel Emoni • Built with ❤️ & Code</p>
          <p>BSc Applied Computer Science • Chuka University</p>
        </div>
      </div>
    </div>
  );
};

export default AnimatedPortfolio;
