<script>
  let isMenuOpen = false;
  
  const menuItems = [
    { href: '#home', text: 'Home' },
    { href: '#about', text: 'About' },
    { href: '#skills', text: 'Skills' },
    { href: '#activities', text: 'Activities' },
    { href: '#contact', text: 'Contact' }
  ];

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }

  function smoothScroll(e) {
    e.preventDefault();
    const targetId = e.currentTarget.getAttribute('href').substring(1);
    const targetElement = document.getElementById(targetId);
    
    if (targetElement) {
      const startPosition = window.pageYOffset;
      const targetPosition = targetElement.getBoundingClientRect().top + window.pageYOffset;
      const distance = targetPosition - startPosition;
      const duration = 800;
      let startTime = null;

      function animateScroll(currentTime) {
        if (startTime === null) startTime = currentTime;
        const timeElapsed = currentTime - startTime;
        const progress = Math.min(timeElapsed / duration, 1);
        const easeInOutQuad = (t) => t < 0.5 ? 2 * t * t : -1 + (4 - 2 * t) * t;
        window.scrollTo(0, startPosition + distance * easeInOutQuad(progress));

        if (timeElapsed < duration) {
          requestAnimationFrame(animateScroll);
        }
      }

      requestAnimationFrame(animateScroll);
      isMenuOpen = false;
    }
  }
</script>

<nav class="navbar">
  <div class="container navbar-container">
    <a href="#home" class="logo" on:click={smoothScroll}>M Sulthan HS</a>
    
    <button class="menu-toggle" on:click={toggleMenu} aria-label="Toggle menu">
      <span class="hamburger"></span>
    </button>

    <ul class="nav-links" class:active={isMenuOpen}>
      {#each menuItems as item}
        <li>
          <a href={item.href} on:click={smoothScroll}>
            {item.text}
          </a>
        </li>
      {/each}
    </ul>
  </div>
</nav>

<style>
  .navbar {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background: rgba(26, 27, 38, 0.8);
    backdrop-filter: blur(10px);
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    z-index: 1000;
  }

  .navbar-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 4rem;
  }

  .logo {
    font-size: 1.5rem;
    font-weight: bold;
    color: var(--primary-color);
    text-decoration: none;
    transition: color 0.3s ease;
  }

  .logo:hover {
    color: #f472b6;
  }

  .nav-links {
    display: flex;
    gap: 2rem;
    list-style: none;
    margin: 0;
    padding: 0;
  }

  .nav-links a {
    color: var(--text-color);
    text-decoration: none;
    font-weight: 500;
    transition: color 0.3s ease;
    position: relative;
  }

  .nav-links a:hover {
    color: var(--primary-color);
  }

  .nav-links a::after {
    content: '';
    position: absolute;
    bottom: -5px;
    left: 0;
    width: 0;
    height: 2px;
    background: var(--primary-color);
    transition: width 0.3s ease;
  }

  .nav-links a:hover::after {
    width: 100%;
  }

  .menu-toggle {
    display: none;
    background: none;
    border: none;
    cursor: pointer;
    padding: 0.5rem;
  }

  .hamburger {
    display: block;
    width: 24px;
    height: 2px;
    background-color: var(--text-color);
    position: relative;
    transition: background-color 0.3s ease;
  }

  .hamburger::before,
  .hamburger::after {
    content: '';
    position: absolute;
    width: 24px;
    height: 2px;
    background-color: var(--text-color);
    transition: transform 0.3s ease, background-color 0.3s ease;
  }

  .hamburger::before {
    top: -6px;
  }

  .hamburger::after {
    bottom: -6px;
  }

  @media (max-width: 768px) {
    .menu-toggle {
      display: block;
    }

    .nav-links {
      position: fixed;
      top: 4rem;
      left: 0;
      right: 0;
      background: rgba(26, 27, 38, 0.95);
      backdrop-filter: blur(10px);
      padding: 1rem;
      flex-direction: column;
      gap: 1rem;
      transform: translateY(-100%);
      opacity: 0;
      transition: transform 0.3s ease, opacity 0.3s ease;
      pointer-events: none;
    }

    .nav-links.active {
      transform: translateY(0);
      opacity: 1;
      pointer-events: auto;
    }

    .nav-links a {
      display: block;
      padding: 0.5rem 0;
    }

    .nav-links a::after {
      display: none;
    }
  }
</style> 