<script>
  export let title;
  export let description;
  export let image;
  export let technologies;
</script>

<div class="project-card">
  <div class="project-image">
    <img src={image} alt={title} />
  </div>
  <div class="project-content">
    <h3 class="project-title">{title}</h3>
    <p class="project-description">{description}</p>
    <div class="project-technologies">
      {#each technologies as tech}
        <span class="tech-tag">{tech}</span>
      {/each}
    </div>
  </div>
</div>

<style>
  .project-card {
    background-color: var(--card-background);
    border-radius: 0.5rem;
    overflow: hidden;
    transition: transform 0.3s ease;
    height: 100%;
    display: flex;
    flex-direction: column;
  }

  .project-card:hover {
    transform: translateY(-5px);
  }

  .project-image {
    width: 100%;
    height: 200px;
    background-color: var(--background-color);
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 1.5rem;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  }

  .project-image img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    filter: brightness(0.9) contrast(1.1);
    transition: transform 0.3s ease;
  }

  .project-card:hover .project-image img {
    transform: scale(1.05);
  }

  .project-content {
    padding: 1.5rem;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
  }

  .project-title {
    font-size: 1.5rem;
    margin-bottom: 1rem;
    color: var(--text-color);
    font-weight: 700;
  }

  .project-description {
    color: #9ca3af;
    margin-bottom: 1.5rem;
    flex-grow: 1;
  }

  .project-technologies {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .tech-tag {
    background-color: var(--primary-color);
    color: white;
    padding: 0.25rem 0.75rem;
    border-radius: 1rem;
    font-size: 0.875rem;
  }
</style> 