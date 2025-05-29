<script>
  const socialLinks = [
    {
      name: 'GitHub',
      url: 'https://github.com/SulthanHS',
      icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg'
    },
    {
      name: 'LinkedIn',
      url: 'https://www.linkedin.com/in/m-sulthan-hariz-shiddiq-2015b932a',
      icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg'
    },
    {
      name: 'Instagram',
      url: 'https://www.instagram.com/sulthanhrz/',
      icon: 'https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/instagram.svg'
    }
  ];
</script>

<footer>
  <div class="container">
    <div class="footer-content">
      <div class="footer-section">
        <h3>M Sulthan Hariz Shiddiq</h3>
        <p>Junior Web Developer passionate about creating beautiful and functional web applications.</p>
      </div>
      <div class="footer-section">
        <h4>Quick Links</h4>
        <ul>
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#skills">Skills</a></li>
          <li><a href="#activities">Activities</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>
      <div class="footer-section">
        <h4>Connect With Me</h4>
        <div class="footer-social-links">
          {#each socialLinks as link}
            <a href={link.url} target="_blank" rel="noopener noreferrer" class="footer-social-link">
              <img src={link.icon} alt={link.name} />
              <span>{link.name}</span>
            </a>
          {/each}
        </div>
      </div>
    </div>
    <div class="footer-bottom">
      <p>&copy; {new Date().getFullYear()} M Sulthan Hariz Shiddiq. All rights reserved.</p>
      <p class="footer-note">Built using SvelteKit</p>
    </div>
  </div>
</footer>

<style>
  footer {
    background-color: var(--card-background);
    color: #9ca3af;
    padding: 4rem 0 2rem;
    margin-top: 4rem;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 1rem;
  }

  .footer-content {
    display: grid;
    grid-template-columns: 2fr 1fr 1fr;
    gap: 4rem;
    margin-bottom: 3rem;
  }

  .footer-section h3 {
    color: var(--primary-color);
    font-size: 1.5rem;
    margin-bottom: 1rem;
  }

  .footer-section h4 {
    color: var(--primary-color);
    font-size: 1.2rem;
    margin-bottom: 1.5rem;
  }

  .footer-section p {
    line-height: 1.6;
    margin-bottom: 1rem;
  }

  .footer-section ul {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .footer-section ul li {
    margin-bottom: 0.75rem;
  }

  .footer-section ul li a {
    color: #9ca3af;
    text-decoration: none;
    transition: color 0.3s ease;
  }

  .footer-section ul li a:hover {
    color: var(--primary-color);
  }

  .footer-social-links {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .footer-social-link {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    color: #9ca3af;
    text-decoration: none;
    transition: color 0.3s ease;
  }

  .footer-social-link:hover {
    color: var(--primary-color);
  }

  .footer-social-link img {
    width: 20px;
    height: 20px;
  }

  .footer-bottom {
    text-align: center;
    padding-top: 2rem;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
  }

  .footer-note {
    margin-top: 0.5rem;
    font-size: 0.9rem;
    color: #6b7280;
  }

  @media (max-width: 768px) {
    .footer-content {
      grid-template-columns: 1fr;
      gap: 2rem;
      text-align: center;
    }

    .footer-social-links {
      align-items: center;
    }

    .footer-section ul li {
      margin-bottom: 0.5rem;
    }
  }
</style> 