<script>
  import { fade } from 'svelte/transition';
</script>

<section id="about" class="about section">
  <div class="container">
    <h2 class="section-title">About Me</h2>
    <div class="about-content">
      <div class="about-text">
        <div class="about-card">
          <div class="floating-icons-left">
            <div class="japanese-icon">🏮</div>
            <div class="japanese-icon">🌸</div>
            <div class="japanese-icon">🎎</div>
            <div class="japanese-icon">🎌</div>
            <div class="japanese-icon">🗾</div>
          </div>
          <p>
            I'm a junior web developer who's passionate about learning and growing in the tech industry.
            My journey in web development started with curiosity about how websites work, and I've been
            actively learning and building projects to improve my skills. I enjoy creating responsive
            and user-friendly web applications that solve real-world problems.
          </p>
          <p>
            Currently, I'm focusing on mastering the fundamentals of web development and exploring
            modern technologies like React, Svelte, and Laravel. I'm eager to take on new challenges
            and opportunities that will help me grow as a developer. While I'm still early in my career,
            I bring enthusiasm, dedication, and a strong desire to learn to every project I work on.
            I believe in writing clean, maintainable code and following best practices in software development.
          </p>
          <div class="about-quote">
            <p>"The best way to predict the future is to implement it yourself."</p>
            <span class="quote-author">- David Heinemeier Hansson</span>
          </div>
          <div class="floating-icons-right">
            <div class="japanese-icon">⛩️</div>
            <div class="japanese-icon">🎋</div>
            <div class="japanese-icon">🌊</div>
            <div class="japanese-icon">🎭</div>
            <div class="japanese-icon">🗻</div>
          </div>
          <div class="floating-icons-bottom">
            <div class="japanese-icon">🎨</div>
            <div class="japanese-icon">🎪</div>
            <div class="japanese-icon">🎯</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .about {
    background-color: var(--card-background);
  }

  .about-content {
    display: grid;
    grid-template-columns: 1fr;
    gap: 3rem;
  }

  .about-text {
    max-width: 800px;
    margin: 0 auto;
  }

  .about-text p {
    margin-bottom: 1.5rem;
    color: #9ca3af;
    line-height: 1.6;
  }

  .about-card {
    background: var(--card-background);
    border-radius: 1rem;
    padding: 2.5rem;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
    border: 1px solid rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(8px);
  }

  .section-title {
    text-align: center;
    margin-bottom: 3rem;
    font-size: 2.5rem;
    position: relative;
    color: var(--text-color);
  }

  .section-title::after {
    content: '';
    position: absolute;
    bottom: -10px;
    left: 50%;
    transform: translateX(-50%);
    width: 50px;
    height: 3px;
    background: var(--primary-color);
  }

  .floating-icons-left, .floating-icons-right,
  .floating-icons-bottom {
    position: absolute;
    display: flex;
    gap: 2rem;
  }

  .floating-icons-left {
    left: -80px;
    top: 50%;
    transform: translateY(-50%);
    flex-direction: column;
  }

  .floating-icons-right {
    right: -80px;
    top: 50%;
    transform: translateY(-50%);
    flex-direction: column;
  }

  .floating-icons-bottom {
    bottom: -60px;
    left: 50%;
    transform: translateX(-50%);
  }

  .japanese-icon {
    font-size: 2rem;
    opacity: 0.7;
    transition: all 0.3s ease;
    filter: drop-shadow(0 0 8px rgba(99, 102, 241, 0.3));
  }

  .japanese-icon:hover {
    transform: scale(1.2);
    opacity: 1;
  }

  /* Animasi untuk setiap icon */
  .floating-icons-left .japanese-icon:nth-child(1) { animation: swing 3s ease-in-out infinite; }
  .floating-icons-left .japanese-icon:nth-child(2) { animation: float 3s ease-in-out infinite; }
  .floating-icons-left .japanese-icon:nth-child(3) { animation: rotate 4s linear infinite; }
  .floating-icons-left .japanese-icon:nth-child(4) { animation: swing 3.5s ease-in-out infinite; }
  .floating-icons-left .japanese-icon:nth-child(5) { animation: float 4s ease-in-out infinite; }

  .floating-icons-right .japanese-icon:nth-child(1) { animation: float 3s ease-in-out infinite; }
  .floating-icons-right .japanese-icon:nth-child(2) { animation: swing 3s ease-in-out infinite; }
  .floating-icons-right .japanese-icon:nth-child(3) { animation: wave 3s ease-in-out infinite; }
  .floating-icons-right .japanese-icon:nth-child(4) { animation: rotate 4s linear infinite; }
  .floating-icons-right .japanese-icon:nth-child(5) { animation: float 3.5s ease-in-out infinite; }

  .floating-icons-bottom .japanese-icon:nth-child(1) { animation: swing 3s ease-in-out infinite; }
  .floating-icons-bottom .japanese-icon:nth-child(2) { animation: float 3.5s ease-in-out infinite; }
  .floating-icons-bottom .japanese-icon:nth-child(3) { animation: wave 3s ease-in-out infinite; }

  @keyframes swing {
    0%, 100% { transform: rotate(-5deg); }
    50% { transform: rotate(5deg); }
  }

  @keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
  }

  @keyframes rotate {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }

  @keyframes wave {
    0%, 100% { transform: translateX(0) rotate(0deg); }
    50% { transform: translateX(10px) rotate(5deg); }
  }

  .about-quote {
    margin-top: 3rem;
    padding: 2rem;
    background: rgba(36, 40, 59, 0.3);
    border-radius: 1rem;
    border: 1px solid rgba(99, 102, 241, 0.2);
    position: relative;
  }

  .about-quote::before {
    content: '"';
    position: absolute;
    top: -20px;
    left: 20px;
    font-size: 4rem;
    color: var(--primary-color);
    opacity: 0.3;
    font-family: serif;
  }

  .about-quote p {
    font-style: italic;
    color: #9ca3af;
    text-align: center;
    margin: 0;
    font-size: 1.2rem;
    line-height: 1.6;
  }

  .quote-author {
    display: block;
    text-align: right;
    color: var(--primary-color);
    margin-top: 1rem;
    font-size: 0.9rem;
    font-style: normal;
  }

  @media (max-width: 1200px) {
    .floating-icons-left, .floating-icons-right,
    .floating-icons-bottom {
      display: none;
    }
  }
</style> 