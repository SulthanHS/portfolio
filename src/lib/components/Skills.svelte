<script>
  import { fade } from 'svelte/transition';
  import SkillCard from './SkillCard.svelte';

  const skills = [
    {
      name: 'Laravel',
      type: 'technical',
      logo: 'https://www.vectorlogo.zone/logos/laravel/laravel-icon.svg',
      url: 'https://laravel.com'
    },
    {
      name: 'Svelte',
      type: 'technical',
      logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/svelte/svelte-original.svg',
      url: 'https://svelte.dev'
    },
    {
      name: 'JavaScript',
      type: 'technical',
      logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg',
      url: 'https://developer.mozilla.org/en-US/docs/Web/JavaScript'
    },
    {
      name: 'HTML5',
      type: 'technical',
      logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg',
      url: 'https://developer.mozilla.org/en-US/docs/Web/HTML'
    },
    {
      name: 'CSS3',
      type: 'technical',
      logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg',
      url: 'https://developer.mozilla.org/en-US/docs/Web/CSS'
    },
    {
      name: 'React',
      type: 'technical',
      logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg',
      url: 'https://react.dev'
    },
    {
      name: 'Node.js',
      type: 'technical',
      logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg',
      url: 'https://nodejs.org'
    },
    {
      name: 'PostgreSQL',
      type: 'technical',
      logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg',
      url: 'https://www.postgresql.org'
    },
    {
      name: 'MongoDB',
      type: 'technical',
      logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg',
      url: 'https://www.mongodb.com'
    },
    {
      name: 'Git',
      type: 'technical',
      logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg',
      url: 'https://git-scm.com'
    }
  ];

  const softSkills = [
    {
      name: 'Problem Solving',
      description: 'Strong analytical and debugging skills with experience in identifying and resolving complex technical issues efficiently.'
    },
    {
      name: 'API Design',
      description: 'Proficient in designing and implementing RESTful APIs with a focus on scalability, security, and best practices.'
    },
    {
      name: 'Application Architecture',
      description: 'Understanding of scalable and maintainable application design patterns, microservices architecture, and system integration.'
    },
    {
      name: 'Database Design',
      description: 'Experience in database modeling, optimization, and management with both SQL and NoSQL databases.'
    },
    {
      name: 'Version Control',
      description: 'Proficient in Git workflow, collaborative development practices, and maintaining clean code repositories.'
    }
  ];
</script>

<section id="skills" class="skills section">
  <div class="container">
    <h2 class="section-title">My Skills</h2>
    <div class="skills-container">
      <div class="skills-category">
        <h3 class="skills-category-title">Technical Skills</h3>
        <div class="skills-grid">
          {#each skills as skill}
            <SkillCard {...skill} />
          {/each}
        </div>
      </div>
      <div class="skills-category">
        <h3 class="skills-category-title">Professional Skills</h3>
        <div class="soft-skills-list">
          {#each softSkills as skill}
            <div class="soft-skill-item">
              <h4 class="soft-skill-title">{skill.name}</h4>
              <p class="soft-skill-description">{skill.description}</p>
            </div>
          {/each}
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .skills {
    background-color: var(--background-color);
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

  .skills-container {
    display: flex;
    flex-direction: column;
    gap: 4rem;
    max-width: 900px;
    margin: 0 auto;
  }

  .skills-category {
    background: var(--card-background);
    border-radius: 1rem;
    padding: 2rem;
    border: 1px solid rgba(255, 255, 255, 0.1);
  }

  .skills-category-title {
    color: var(--primary-color);
    font-size: 1.5rem;
    margin-bottom: 2rem;
    text-align: center;
    position: relative;
    padding-bottom: 1rem;
  }

  .skills-category-title::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 50px;
    height: 2px;
    background: var(--primary-color);
  }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 1.5rem;
    margin-top: 2rem;
  }

  .soft-skills-list {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    padding: 1rem;
    max-width: 700px;
    margin: 0 auto;
  }

  .soft-skill-item {
    background: rgba(36, 40, 59, 0.3);
    border-radius: 0.75rem;
    padding: 1.5rem;
    border: 1px solid rgba(99, 102, 241, 0.2);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .soft-skill-item:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(99, 102, 241, 0.15);
  }

  .soft-skill-title {
    color: var(--primary-color);
    font-size: 1.2rem;
    margin-bottom: 0.75rem;
    font-weight: 600;
  }

  .soft-skill-description {
    color: #9ca3af;
    line-height: 1.6;
    margin: 0;
  }

  @media (max-width: 1200px) {
    .skills-grid {
      grid-template-columns: repeat(4, 1fr);
    }
  }

  @media (max-width: 992px) {
    .skills-grid {
      grid-template-columns: repeat(3, 1fr);
    }
  }

  @media (max-width: 768px) {
    .skills-container {
      gap: 2rem;
    }

    .skills-category {
      padding: 1.5rem;
    }

    .skills-grid {
      grid-template-columns: repeat(2, 1fr);
    }

    .soft-skills-list {
      padding: 0.5rem;
      max-width: 100%;
    }

    .soft-skill-item {
      padding: 1.25rem;
    }
  }

  @media (max-width: 480px) {
    .skills-grid {
      grid-template-columns: repeat(2, 1fr);
      gap: 1rem;
    }
  }
</style> 