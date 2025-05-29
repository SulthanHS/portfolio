<script>
  import { fade } from 'svelte/transition';
  const navLinks = [
    { href: '#home', text: 'Home' },
    { href: '#about', text: 'About' },
    { href: '#skills', text: 'Skills' },
    { href: '#activities', text: 'Activities' },
    { href: '#contact', text: 'Contact' }
  ];
</script>

<section id="home" class="hero section">
  <div class="hero-bg-blur"></div>
  <div class="japanese-pattern-overlay"></div>
  <div class="japanese-asanoha-overlay"></div>
  <div class="decorative-circles">
    <div class="circle circle-1"></div>
    <div class="circle circle-2"></div>
    <div class="circle circle-3"></div>
  </div>
  <div class="container">
    <div class="hero-content">
      <div class="hero-text">
        <div class="hero-badge-glass">
          <span class="badge-icon">🚀</span> Junior Web Developer
        </div>
        <h1 class="hero-main-title">
          <span class="greeting">Hello, I'm</span>
          <span class="name-gradient-animate">M Sulthan Hariz Shiddiq</span>
        </h1>
        <p class="hero-description">
          I build modern, beautiful, and interactive web experiences.<br />
          <span class="hero-highlight">Let's create something amazing together!</span>
        </p>
        <div class="hero-buttons">
          <a href="#activities" class="btn-glass">
            <span>See My Activities</span>
            <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>
          </a>
          <a href="#contact" class="btn-glass-secondary">
            <span>Contact Me</span>
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 10.5V6a2 2 0 0 0-2-2H5a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2v-4.5"/><polyline points="17 8 21 12 17 16"/><line x1="21" y1="12" x2="9" y2="12"/></svg>
          </a>
        </div>
      </div>
      <div class="hero-image">
        <div class="avatar-glow">
          <img src="/images/profilegweh.jpg" alt="My profile" class="avatar-img" />
        </div>
        <div class="floating-tech-icons">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/svelte/svelte-original.svg" alt="Svelte" class="floating-icon floating1" />
          <img src="https://www.vectorlogo.zone/logos/laravel/laravel-icon.svg" alt="Laravel" class="floating-icon floating2 laravel-icon" />
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="JS" class="floating-icon floating3" />
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" alt="React" class="floating-icon floating4" />
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    background: none;
    padding-top: 4rem;
    position: relative;
    overflow: hidden;
  }

  .hero-bg-blur {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: 
      radial-gradient(circle at 60% 40%, rgba(193, 50, 142, 0.4) 0%, transparent 60%),
      radial-gradient(circle at 20% 80%, rgba(168, 73, 122, 0.4) 0%, transparent 70%),
      radial-gradient(circle at 80% 20%, rgba(99, 102, 241, 0.4) 0%, transparent 60%);
    filter: blur(80px);
    opacity: 0.5;
    z-index: 0;
  }

  .japanese-pattern-overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-image: url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgdmlld0JveD0iMCAwIDIwMCAyMDAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTAgMjAwVjBsMTAwIDEwMCAxMDAtMTAwVjIwMEwwIDEwMCAyMDAgMCIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjRTZFMzEwIiBzdHJva2Utd2lkdGg9IjIiLz48L3N2Zz4=');
    background-size: 100px 100px;
    opacity: 0.1;
    z-index: 1;
    pointer-events: none;
  }

  .japanese-asanoha-overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-image: url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjAiIGhlaWdodD0iMTA0IiB2aWV3Qm94PSIwIDAgNjAgMTA0IiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPjxnIHN0cm9rZT0iI0U2RTMxMCIgc3Ryb2tlLXdpZHRoPSIyIiBmaWxsPSJub25lIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCI+PHBhdGggZD0iTTMwIDBMMSA1MiAzMCAxMDQgNTkgNTIgMzAgMCIvPjxwYXRoIGQ9Ik01OSA1MiAzMCAwIDMgNTIgNTkgNTIiLz48LzxnPjwvc3ZnPg==');
    background-size: 60px 104px;
    opacity: 0.08;
    z-index: 1;
    pointer-events: none;
  }

  .decorative-circles {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    overflow: hidden;
    z-index: 1;
  }

  .circle {
    position: absolute;
    border-radius: 50%;
    background: linear-gradient(45deg, var(--primary-color), #f472b6);
    opacity: 0.1;
    animation: float 8s ease-in-out infinite;
  }

  .circle-1 {
    width: 300px;
    height: 300px;
    top: -150px;
    right: -150px;
    animation-delay: 0s;
  }

  .circle-2 {
    width: 200px;
    height: 200px;
    bottom: -100px;
    left: -100px;
    animation-delay: 2s;
  }

  .circle-3 {
    width: 150px;
    height: 150px;
    top: 50%;
    right: 10%;
    animation-delay: 4s;
  }

  @keyframes float {
    0%, 100% {
      transform: translateY(0) rotate(0deg);
    }
    50% {
      transform: translateY(-20px) rotate(180deg);
    }
  }

  .hero-content {
    display: flex;
    flex-direction: row;
    gap: 4rem;
    align-items: center;
    position: relative;
    z-index: 2;
    justify-content: space-between;
  }

  .hero-text {
    flex: 1;
    position: relative;
  }

  .hero-text::before {
    content: '';
    position: absolute;
    top: -20px;
    left: -20px;
    right: -20px;
    bottom: -20px;
    background: radial-gradient(circle at center, rgba(99, 102, 241, 0.1) 0%, transparent 70%);
    border-radius: 20px;
    z-index: -1;
  }

  .hero-badge-glass {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    background: rgba(30, 41, 59, 0.6);
    border: 1.5px solid rgba(99, 102, 241, 0.25);
    color: var(--primary-color);
    padding: 0.5rem 1.25rem;
    border-radius: 2rem;
    font-size: 1rem;
    font-weight: 500;
    box-shadow: 0 2px 16px 0 rgba(99,102,241,0.10);
    margin-bottom: 1.5rem;
    backdrop-filter: blur(8px);
    letter-spacing: 0.03em;
  }

  .badge-icon {
    font-size: 1.2em;
  }

  .hero-main-title {
    margin-bottom: 1.5rem;
  }

  .greeting {
    font-size: 1.5rem;
    color: #9ca3af;
    font-weight: 400;
    display: block;
    margin-bottom: 0.5rem;
  }

  .name-gradient-animate {
    font-size: 3.5rem;
    font-weight: 800;
    background: linear-gradient(90deg, #6366f1, #818cf8, #f472b6, #6366f1);
    background-size: 200% 200%;
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: gradientMove 4s ease-in-out infinite;
    display: block;
    line-height: 1.1;
  }

  @keyframes gradientMove {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }

  .hero-description {
    font-size: 1.25rem;
    color: #9ca3af;
    max-width: 600px;
    margin-bottom: 2.5rem;
    line-height: 1.6;
  }

  .hero-highlight {
    color: #f472b6;
    font-weight: 600;
    font-size: 1.1em;
  }

  .hero-buttons {
    display: flex;
    gap: 1.2rem;
    margin-top: 1rem;
  }

  .btn-glass, .btn-glass-secondary {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    padding: 0.85rem 1.7rem;
    border-radius: 0.7rem;
    font-weight: 600;
    font-size: 1.1rem;
    text-decoration: none;
    border: 1.5px solid var(--primary-color);
    background: rgba(30,41,59,0.5);
    color: var(--primary-color);
    box-shadow: 0 2px 16px 0 rgba(99,102,241,0.10);
    transition: all 0.2s cubic-bezier(.4,2,.6,1);
    backdrop-filter: blur(8px);
    cursor: pointer;
  }

  .btn-glass:hover, .btn-glass-secondary:hover {
    background: var(--primary-color);
    color: #fff;
    transform: translateY(-2px) scale(1.04);
    box-shadow: 0 4px 24px 0 rgba(99,102,241,0.18);
  }

  .btn-glass-secondary {
    border: 1.5px solid #f472b6;
    color: #f472b6;
  }

  .btn-glass-secondary:hover {
    background: #f472b6;
    color: #fff;
  }

  .hero-image {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
    z-index: 2;
  }

  .avatar-glow {
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 200px;
    height: 200px;
    position: relative;
    overflow: hidden;
    border-radius: 50%;
    border: 4px solid var(--primary-color);
    box-shadow: 0 0 20px rgba(99, 102, 241, 0.3);
  }

  .avatar-img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 50%;
  }

  .floating-tech-icons {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    pointer-events: none;
  }

  .floating-icon {
    position: absolute;
    width: 60px;
    height: 60px;
    opacity: 0.95;
    filter: drop-shadow(0 4px 12px rgba(99, 102, 241, 0.3));
    animation: floatIcon 6s ease-in-out infinite;
    background-color: rgba(36, 40, 59, 0.6);
    border: 2px solid var(--primary-color);
    border-radius: 8px;
    padding: 6px;
    box-sizing: border-box;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .floating1 { left: -30px; top: 10px; animation-delay: 0s; }
  .floating2 { right: -30px; top: 30px; animation-delay: 1.5s; }
  .floating3 { left: 10px; bottom: -30px; animation-delay: 3s; }
  .floating4 { right: 10px; bottom: -30px; animation-delay: 4.5s; }

  @keyframes floatIcon {
    0%, 100% { 
      transform: translateY(0) scale(1) rotate(0deg); 
    }
    50% { 
      transform: translateY(-18px) scale(1.08) rotate(10deg); 
    }
  }

  @media (max-width: 768px) {
    .hero-content {
      flex-direction: column;
      text-align: center;
      gap: 3rem;
    }

    .hero-text {
      text-align: center;
    }

    .hero-badge-glass {
      margin-left: auto;
      margin-right: auto;
    }

    .hero-description {
      margin-left: auto;
      margin-right: auto;
    }

    .hero-buttons {
      justify-content: center;
    }

    .hero-image {
      margin-top: 2rem;
    }

    .avatar-glow {
      width: 120px;
      height: 120px;
    }

    .floating-icon {
      width: 40px;
      height: 40px;
    }
  }

  @media (max-width: 480px) {
    .name-gradient-animate {
      font-size: 2.5rem;
    }

    .hero-badge-glass {
      font-size: 0.875rem;
      padding: 0.375rem 1rem;
    }

    .btn-glass, .btn-glass-secondary {
      padding: 0.75rem 1.25rem;
      font-size: 1rem;
    }

    .avatar-glow {
      width: 100px;
      height: 100px;
    }

    .floating-icon {
      width: 32px;
      height: 32px;
    }
  }
</style> 