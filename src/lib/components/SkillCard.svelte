<script>
  export let name;
  export let type;
  export let logo;
  export let url;
</script>

<a href={url} target="_blank" rel="noopener noreferrer" class="skill-card">
  <img src={logo} alt={name} class="skill-logo" />
  <span class="skill-name">{name}</span>
</a>

<style>
  .skill-card {
    background: rgba(36, 40, 59, 0.3);
    border-radius: 0.75rem;
    padding: 1.5rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
    border: 1px solid rgba(99, 102, 241, 0.2);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    text-decoration: none;
    cursor: pointer;
  }

  .skill-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 4px 12px rgba(99, 102, 241, 0.15);
    border-color: var(--primary-color);
  }

  .skill-logo {
    width: 48px;
    height: 48px;
    object-fit: contain;
  }

  .skill-name {
    color: var(--text-color);
    font-size: 0.9rem;
    text-align: center;
  }
</style> 