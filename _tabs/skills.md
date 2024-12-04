---
layout: page
icon: fas fa-code
order: 4
---

<div class="page-content-wrapper">
    <nav id="custom-sidebar">
        <div class="sidebar-header">
            <h4 class="mb-0">Navigation</h4>
        </div>
        <ul class="nav flex-column">
            <li class="nav-item">
                <a class="nav-link" href="#technical-skills">Technical Skills</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#programming-languages">Programming Languages</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#machine-learning--ai">Machine Learning & AI</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#research-skills">Research Skills</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#development-tools">Development Tools</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#soft-skills">Soft Skills</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#languages">Languages</a>
            </li>
        </ul>
    </nav>
    
    <div class="main-content markdown-content">
        {% capture my_content %}
# Technical Skills

## Programming Languages
- Python (Advanced)
  - Expert in scientific computing libraries (NumPy, SciPy, Pandas)
  - Deep learning frameworks (PyTorch, TensorFlow)
  - Web frameworks (Flask, FastAPI)
- C++ (Intermediate)
  - OpenCV and computer vision applications
  - Algorithm implementation
  - Performance optimization
- JavaScript/TypeScript
  - Frontend development (React, Vue.js)
  - Node.js backend development
  - Web APIs and REST services
- MATLAB
  - Signal processing
  - Image processing
  - Scientific computing
- Shell Scripting (Bash)
  - Automation
  - System administration
  - Development workflows

## Machine Learning & AI
- Deep Learning Frameworks
  - PyTorch (Primary framework)
    - Custom architectures
    - Transfer learning
    - Model optimization
  - TensorFlow/Keras
    - Model development
    - Production deployment
    - TensorBoard visualization
- Computer Vision Libraries
  - OpenCV
    - Image processing
    - Video analysis
    - Real-time applications
  - scikit-image
    - Advanced image processing
    - Feature extraction
    - Image segmentation
- Machine Learning Libraries
  - scikit-learn
    - Classical ML algorithms
    - Model evaluation
    - Feature engineering
  - NumPy & Pandas
    - Data manipulation
    - Statistical analysis
    - Performance optimization

## Research Skills
- Experimental Design
  - Hypothesis formulation
  - Control group design
  - Statistical validation
- Statistical Analysis
  - Hypothesis testing
  - Regression analysis
  - Data visualization
- Technical Writing
  - Research papers
  - Technical documentation
  - Grant proposals
- Literature Review
  - Systematic reviews
  - Meta-analysis
  - Citation management
- Research Methodology
  - Quantitative methods
  - Qualitative analysis
  - Mixed methods research

## Development Tools
- Version Control
  - Git/GitHub
  - GitLab
  - Branching strategies
- Containerization
  - Docker
  - Docker Compose
  - Container orchestration
- Operating Systems
  - Linux/Unix administration
  - Shell scripting
  - System optimization
- Cloud Platforms
  - AWS (EC2, S3, Lambda)
  - Google Cloud Platform
  - Azure ML
- Development Environment
  - VS Code
  - PyCharm
  - Jupyter Notebooks
  - vim

## Soft Skills
- Technical Leadership
  - Team management
  - Project planning
  - Mentoring
- Project Management
  - Agile methodologies
  - Sprint planning
  - Risk management
- Public Speaking
  - Conference presentations
  - Technical workshops
  - Classroom instruction
- Academic Writing
  - Research papers
  - Grant proposals
  - Technical documentation
- Team Collaboration
  - Cross-functional teams
  - Remote collaboration
  - Code review

## Languages
- English (Professional)
  - Technical writing
  - Academic presentations
  - Professional communication
- Spanish (Native)
  - Technical translation
  - Academic instruction
  - Professional writing
        {% endcapture %}
        {{ my_content | markdownify }}
    </div>
</div>

<style>
.page-content-wrapper {
    display: flex;
    width: 100%;
    gap: 2rem;
}

#custom-sidebar {
    width: 250px;
    height: calc(100vh - 5rem);
    background: var(--sidebar-bg);
    padding: 20px;
    position: sticky;
    top: 5rem;
    border-right: 1px solid var(--border-color);
    margin-left: -2rem;
    transition: transform 0.3s ease-in-out;
}

.main-content {
    flex: 1;
    min-width: 0;
}

.markdown-content {
    padding-right: 2rem;
}

.nav-link {
    color: var(--text-color);
    padding: 10px;
    display: block;
    text-decoration: none;
}

.nav-link:hover {
    background: var(--hover-bg);
    border-radius: 5px;
}

.nav-link.active {
    color: var(--link-color);
    background: var(--hover-bg);
}
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
    // Highlight current section in navigation
    const navLinks = document.querySelectorAll('.nav-link');
    const sections = document.querySelectorAll('h1, h2');
    
    function updateActiveSection() {
        let current = '';
        sections.forEach(section => {
            const sectionTop = section.getBoundingClientRect().top;
            if (sectionTop <= 100) {
                current = section.getAttribute('id');
            }
        });

        navLinks.forEach(link => {
            link.classList.remove('active');
            if (link.getAttribute('href').substring(1) === current) {
                link.classList.add('active');
            }
        });
    }

    window.addEventListener('scroll', updateActiveSection);
    updateActiveSection(); // Initial call
});
</script>
