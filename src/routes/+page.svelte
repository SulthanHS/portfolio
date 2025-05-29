<script>
  import Navbar from '$lib/components/Navbar.svelte';
  import About from '$lib/components/About.svelte';
  import Skills from '$lib/components/Skills.svelte';
  import Activities from '$lib/components/Activities.svelte';
  import ContactForm from '$lib/components/ContactForm.svelte';
  import Footer from '$lib/components/Footer.svelte';
  import Hero from '$lib/components/Hero.svelte';

  // Add JavaScript for smooth scrolling
  import { onMount } from 'svelte';

  onMount(() => {
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();

        const targetId = this.getAttribute('href').substring(1);
        const targetElement = document.getElementById(targetId);

        if (targetElement) {
          // Custom smooth scroll animation
          const startPosition = window.pageYOffset;
          const targetPosition = targetElement.getBoundingClientRect().top + window.pageYOffset;
          const distance = targetPosition - startPosition;
          const duration = 800; // Adjust duration as needed (milliseconds)
          let startTime = null;

          function animateScroll(currentTime) {
            if (startTime === null) startTime = currentTime;
            const timeElapsed = currentTime - startTime;
            const progress = Math.min(timeElapsed / duration, 1);
            const easeInOutQuad = (t) => t < 0.5 ? 2 * t * t : -1 + (4 - 2 * t) * t; // Easing function
            window.scrollTo(0, startPosition + distance * easeInOutQuad(progress));

            if (timeElapsed < duration) {
              requestAnimationFrame(animateScroll);
            }
          }

          requestAnimationFrame(animateScroll);
        }
      });
    });
  });

  const navLinks = [
    { href: '#home', text: 'Home' },
    { href: '#about', text: 'About' },
    { href: '#skills', text: 'Skills' },
    { href: '#activities', text: 'Activities' },
    { href: '#contact', text: 'Contact' }
  ];
</script>

<Navbar />

<main>
  <Hero />
  <About />
  <Skills />
  <Activities />
  <ContactForm />
</main>

<Footer />

<style>
  :global(body) {
    font-family: 'Shippori Mincho', serif;
  }

  :global(:root) {
    --primary-color: #7aa2f7; /* Tokyo Night blue */
    --primary-hover: #6183bb; /* Slightly darker blue */
    --background-color: #1a1b26; /* Tokyo Night background */
    --card-background: #24283b; /* Tokyo Night darker background */
    --text-color: #c0caf5; /* Tokyo Night text color */
  }
</style>

