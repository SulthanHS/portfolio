<script>
  import { fade } from 'svelte/transition';

  const activities = [
    {
      title: 'JavaScript Fundamentals',
      description: 'Completed comprehensive JavaScript course covering ES6+, async programming, and modern web development practices.',
      date: '2023',
      type: 'Education',
      platform: 'Dicoding'
    },
    {
      title: 'Backend Development',
      description: 'Mastered backend development with Node.js, Express, and RESTful API design principles.',
      date: '2023',
      type: 'Education',
      platform: 'Dicoding'
    },
    {
      title: 'Cloud Computing',
      description: 'Learned cloud infrastructure, deployment, and management using AWS and Google Cloud Platform.',
      date: '2025',
      type: 'Education',
      platform: 'Dicoding'
    },
    {
      title: 'Version Control with Git',
      description: 'Completed advanced Git course covering branching strategies, collaboration workflows, and best practices.',
      date: '2023',
      type: 'Education',
      platform: 'Dicoding'
    },
    {
      title: 'Problem Solving',
      description: 'Solved coding challenges on LeetCode focusing on algorithms and data structures.',
      date: '2025',
      type: 'Practice',
      platform: 'LeetCode'
    },
    {
      title: 'JavaScript Algorithms',
      description: 'Completed JavaScript algorithm challenges.',
      date: '2025',
      type: 'Practice',
      platform: 'HackerRank'
    }
  ];
</script>

<section id="activities" class="activities section">
  <div class="container">
    <h2 class="section-title">My Activities</h2>
    <div class="activities-grid">
      {#each activities as activity}
        <div class="activity-card">
          <div class="activity-type">{activity.type}</div>
          <div class="activity-platform">{activity.platform}</div>
          <h3 class="activity-title">{activity.title}</h3>
          <p class="activity-description">{activity.description}</p>
          <div class="activity-date">{activity.date}</div>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .activities {
    background-color: var(--card-background);
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

  .activities-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
    margin-top: 2rem;
    max-width: 900px;
    margin-left: auto;
    margin-right: auto;
  }

  .activity-card {
    background: rgba(36, 40, 59, 0.3);
    border-radius: 1rem;
    padding: 2rem;
    border: 1px solid rgba(99, 102, 241, 0.2);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    position: relative;
    overflow: hidden;
  }

  .activity-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 4px 20px rgba(99, 102, 241, 0.15);
  }

  .activity-type {
    position: absolute;
    top: 1rem;
    right: 1rem;
    background: var(--primary-color);
    color: white;
    padding: 0.25rem 0.75rem;
    border-radius: 1rem;
    font-size: 0.875rem;
    font-weight: 500;
  }

  .activity-platform {
    position: absolute;
    top: 1rem;
    left: 1rem;
    background: #f472b6;
    color: white;
    padding: 0.25rem 0.75rem;
    border-radius: 1rem;
    font-size: 0.875rem;
    font-weight: 500;
  }

  .activity-title {
    color: var(--primary-color);
    font-size: 1.25rem;
    margin: 2.5rem 0 1rem;
    font-weight: 600;
  }

  .activity-description {
    color: #9ca3af;
    line-height: 1.6;
    margin-bottom: 1.5rem;
  }

  .activity-date {
    color: #6b7280;
    font-size: 0.875rem;
    font-weight: 500;
  }

  @media (max-width: 768px) {
    .section {
      padding: 4rem 0;
    }

    .section-title {
      font-size: 2rem;
    }

    .activities-grid {
      grid-template-columns: 1fr;
    }
  }
</style> 