<script>
  let name = '';
  let email = '';
  let message = '';
  let isSubmitting = false;
  let submitStatus = null;
  let showCopyNotification = false;

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

  function copyEmail() {
    navigator.clipboard.writeText('msulthanhs15@gmail.com');
    showCopyNotification = true;
    setTimeout(() => {
      showCopyNotification = false;
    }, 2000);
  }

  async function handleSubmit() {
    isSubmitting = true;
    submitStatus = null;
    
    try {
      // Di sini Anda bisa menambahkan logika untuk mengirim email
      // Contoh: await sendEmail({ name, email, message });
      
      // Simulasi pengiriman
      await new Promise(resolve => setTimeout(resolve, 1000));
      
      submitStatus = 'success';
      name = '';
      email = '';
      message = '';
    } catch (error) {
      submitStatus = 'error';
    } finally {
      isSubmitting = false;
    }
  }
</script>

<section id="contact" class="contact section">
  <div class="container">
    <h2 class="section-title">Contact</h2>
    <div class="contact-content">
      <div class="contact-info">
        <div class="contact-card">
          <h3>Let's Connect</h3>
          <p>
            I'm always open to discussing new projects, creative ideas or
            opportunities to be part of your visions.
          </p>
          <div class="email-container">
            <button class="email-button" on:click={copyEmail}>
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/google/google-original.svg" alt="Email" />
              <span>Email</span>
            </button>
            {#if showCopyNotification}
              <div class="copy-notification">Email copied to clipboard!</div>
            {/if}
          </div>
          <div class="social-links">
            {#each socialLinks as link}
              <a
                href={link.url}
                target="_blank"
                rel="noopener noreferrer"
                class="social-link"
              >
                <img src={link.icon} alt={link.name} />
                <span>{link.name}</span>
              </a>
            {/each}
          </div>
        </div>
      </div>
      <div class="contact-form-wrapper">
        <form on:submit|preventDefault={handleSubmit} class="contact-form">
          <div class="form-group">
            <label for="name">Name</label>
            <input
              type="text"
              id="name"
              bind:value={name}
              required
              placeholder="Your name"
            />
          </div>

          <div class="form-group">
            <label for="email">Email</label>
            <input
              type="email"
              id="email"
              bind:value={email}
              required
              placeholder="Your email"
            />
          </div>

          <div class="form-group">
            <label for="message">Message</label>
            <textarea
              id="message"
              bind:value={message}
              required
              placeholder="Your message"
              rows="5"
            ></textarea>
          </div>

          <button type="submit" class="btn btn-primary" disabled={isSubmitting}>
            {isSubmitting ? 'Sending...' : 'Send Message'}
          </button>

          {#if submitStatus === 'success'}
            <p class="success-message">Message sent successfully!</p>
          {:else if submitStatus === 'error'}
            <p class="error-message">Failed to send message. Please try again.</p>
          {/if}
        </form>
      </div>
    </div>
  </div>
</section>

<style>
  .contact {
    background-color: var(--background-color);
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 1rem;
  }

  .section {
    padding: 8rem 0;
    position: relative;
  }

  .section::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--primary-color), transparent);
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

  .contact-content {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: start;
  }

  .contact-info {
    max-width: 400px;
  }

  .contact-card {
    background-color: var(--card-background);
    border-radius: 0.5rem;
    padding: 2rem;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
    border: 1px solid rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(10px);
  }

  .contact-info h3 {
    font-size: 1.5rem;
    margin-bottom: 1.5rem;
    color: var(--primary-color);
    text-shadow: 0 0 5px rgba(122, 162, 247, 0.2);
  }

  .contact-info p {
    margin-bottom: 2.5rem;
    color: #9ca3af;
  }

  .email-container {
    position: relative;
    margin-bottom: 1.5rem;
    padding-bottom: 1.5rem;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  }

  .email-button {
    display: flex;
    align-items: center;
    gap: 1rem;
    background-color: rgba(36, 40, 59, 0.6);
    border: 2px solid var(--primary-color);
    padding: 12px;
    border-radius: 0.375rem;
    color: var(--text-color);
    cursor: pointer;
    transition: transform 0.3s ease, background-color 0.3s ease, border-color 0.3s ease;
    width: 100%;
    backdrop-filter: blur(5px);
    box-sizing: border-box;
    justify-content: center;
  }

  .email-button:hover {
    transform: translateX(5px) scale(1.02);
    background-color: rgba(36, 40, 59, 0.8);
    border-color: #f472b6;
  }

  .email-button img {
    width: 24px;
    height: 24px;
  }

  .copy-notification {
    position: absolute;
    bottom: -25px;
    left: 50%;
    transform: translateX(-50%);
    background-color: var(--primary-color);
    color: white;
    padding: 0.5rem 1rem;
    border-radius: 0.375rem;
    font-size: 0.875rem;
    animation: fadeInOut 2s ease;
  }

  @keyframes fadeInOut {
    0% { opacity: 0; }
    20% { opacity: 1; }
    80% { opacity: 1; }
    100% { opacity: 0; }
  }

  .social-links {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    margin-top: 1rem;
  }

  .social-link {
    display: flex;
    align-items: center;
    gap: 1rem;
    color: var(--text-color);
    text-decoration: none;
    padding: 12px;
    border-radius: 0.375rem;
    background-color: rgba(36, 40, 59, 0.6);
    border: 2px solid var(--primary-color);
    transition: transform 0.3s ease, background-color 0.3s ease, border-color 0.3s ease;
    backdrop-filter: blur(5px);
    box-sizing: border-box;
    justify-content: center;
  }

  .social-link:hover {
    transform: translateX(5px) scale(1.02);
    background-color: rgba(36, 40, 59, 0.8);
    border-color: #f472b6;
  }

  .social-link img {
    width: 24px;
    height: 24px;
  }

  .contact-form {
    max-width: 600px;
    margin: 0 auto;
  }

  .form-group {
    margin-bottom: 1.5rem;
  }

  label {
    display: block;
    margin-bottom: 0.5rem;
    color: var(--text-color);
    font-weight: 500;
  }

  input,
  textarea {
    width: 100%;
    padding: 0.75rem;
    border: 1px solid #374151;
    border-radius: 0.375rem;
    background-color: var(--card-background);
    color: var(--text-color);
    font-size: 1rem;
    transition: border-color 0.3s ease;
  }

  input:focus,
  textarea:focus {
    outline: none;
    border-color: var(--primary-color);
  }

  input::placeholder,
  textarea::placeholder {
    color: #6b7280;
  }

  button {
    width: 100%;
    margin-top: 1rem;
  }

  .success-message {
    margin-top: 1rem;
    padding: 0.75rem;
    background-color: #059669;
    color: white;
    border-radius: 0.375rem;
    text-align: center;
  }

  .error-message {
    margin-top: 1rem;
    padding: 0.75rem;
    background-color: #dc2626;
    color: white;
    border-radius: 0.375rem;
    text-align: center;
  }

  @media (max-width: 768px) {
    .section {
      padding: 4rem 0;
    }

    .section-title {
      font-size: 2rem;
    }

    .contact-content {
      grid-template-columns: 1fr;
      gap: 2rem;
    }

    .contact-info {
      max-width: 100%;
      text-align: center;
    }

    .social-links {
      align-items: center;
    }
  }
</style> 