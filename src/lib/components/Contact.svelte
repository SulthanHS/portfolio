<script>
  import { fade } from 'svelte/transition';

  let formData = {
    name: '',
    email: '',
    message: ''
  };

  let isSubmitting = false;
  let submitStatus = null;

  async function handleSubmit() {
    isSubmitting = true;
    submitStatus = null;

    try {
      // Simulate form submission
      await new Promise(resolve => setTimeout(resolve, 1000));
      submitStatus = 'success';
      formData = { name: '', email: '', message: '' };
    } catch (error) {
      submitStatus = 'error';
    } finally {
      isSubmitting = false;
    }
  }
</script>

<section id="contact" class="contact-section">
  <div class="container">
    <h2 class="section-title">Contact Me</h2>
    <div class="contact-content">
      <div class="contact-info" in:fade={{ duration: 500 }}>
        <h3>Let's Connect</h3>
        <p>Feel free to reach out to me for any questions or opportunities.</p>
        <div class="contact-details">
          <div class="contact-item">
            <span class="icon">📧</span>
            <span>email@example.com</span>
          </div>
          <div class="contact-item">
            <span class="icon">📱</span>
            <span>+1234567890</span>
          </div>
          <div class="contact-item">
            <span class="icon">📍</span>
            <span>Jakarta, Indonesia</span>
          </div>
        </div>
      </div>

      <form class="contact-form" on:submit|preventDefault={handleSubmit} in:fade={{ duration: 500, delay: 200 }}>
        <div class="form-group">
          <label for="name">Name</label>
          <input
            type="text"
            id="name"
            bind:value={formData.name}
            required
            placeholder="Your name"
          />
        </div>

        <div class="form-group">
          <label for="email">Email</label>
          <input
            type="email"
            id="email"
            bind:value={formData.email}
            required
            placeholder="Your email"
          />
        </div>

        <div class="form-group">
          <label for="message">Message</label>
          <textarea
            id="message"
            bind:value={formData.message}
            required
            placeholder="Your message"
            rows="5"
          ></textarea>
        </div>

        <button type="submit" class="submit-btn" disabled={isSubmitting}>
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
</section>

<style>
  .contact-section {
    padding: 6rem 0;
    background: var(--background-color);
  }

  .contact-content {
    display: grid;
    grid-template-columns: 1fr 2fr;
    gap: 4rem;
    margin-top: 3rem;
  }

  .contact-info {
    color: var(--text-color);
  }

  .contact-info h3 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
    color: var(--primary-color);
  }

  .contact-info p {
    margin-bottom: 2rem;
    line-height: 1.6;
  }

  .contact-details {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .contact-item {
    display: flex;
    align-items: center;
    gap: 1rem;
  }

  .icon {
    font-size: 1.5rem;
  }

  .contact-form {
    background: rgba(255, 255, 255, 0.05);
    padding: 2rem;
    border-radius: 12px;
  }

  .form-group {
    margin-bottom: 1.5rem;
  }

  label {
    display: block;
    margin-bottom: 0.5rem;
    color: var(--text-color);
  }

  input,
  textarea {
    width: 100%;
    padding: 0.8rem;
    background: rgba(255, 255, 255, 0.1);
    border: 1px solid rgba(255, 255, 255, 0.2);
    border-radius: 8px;
    color: var(--text-color);
    font-size: 1rem;
  }

  input:focus,
  textarea:focus {
    outline: none;
    border-color: var(--primary-color);
  }

  .submit-btn {
    background: var(--primary-color);
    color: white;
    padding: 1rem 2rem;
    border: none;
    border-radius: 8px;
    font-size: 1rem;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }

  .submit-btn:hover:not(:disabled) {
    background: #f472b6;
  }

  .submit-btn:disabled {
    opacity: 0.7;
    cursor: not-allowed;
  }

  .success-message {
    color: #4ade80;
    margin-top: 1rem;
  }

  .error-message {
    color: #f87171;
    margin-top: 1rem;
  }

  @media (max-width: 768px) {
    .contact-section {
      padding: 4rem 0;
    }

    .contact-content {
      grid-template-columns: 1fr;
      gap: 2rem;
    }
  }
</style> 