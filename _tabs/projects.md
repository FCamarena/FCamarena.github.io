---
layout: page
icon: fas fa-laptop-code
order: 2
excerpt_separator: <!--more-->
---

<div class="page-content-wrapper">
    <nav id="custom-sidebar">
        <div class="sidebar-header">
            <h4 class="mb-0">Navigation</h4>
        </div>
        <ul class="nav flex-column">
            <li class="nav-item">
                <a class="nav-link" href="#research-projects--publications">Research Projects & Publications</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#journal-publications">Journal Publications</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#conference-publications">Conference Publications</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#research-projects">Research Projects</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#science-communication">Science Communication</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#technical-skills">Technical Skills</a>
            </li>
        </ul>
    </nav>
    
    <div class="main-content markdown-content">
        {% capture my_content %}
# Research Projects & Publications

## Journal Publications

### Knowledge Distillation in Video-Based Human Action Recognition (2024)
*Journal of Imaging*
- Developed an intuitive approach to efficient and flexible model training
- Explored state-of-the-art knowledge distillation techniques
- [DOI: 10.3390/jimaging10040085](https://doi.org/10.3390/jimaging10040085)

### An Overview of the Vision-Based Human Action Recognition Field (2023)
*Mathematical and Computational Applications*
- Comprehensive survey of current methods and challenges
- Analysis of state-of-the-art approaches
- [DOI: 10.3390/mca28020061](https://doi.org/10.3390/mca28020061)

### Action Recognition by Key Trajectories (2022)
*Pattern Analysis and Applications*
- Novel approach to action recognition using trajectory analysis
- Improved efficiency in human activity recognition
- [DOI: 10.1007/s10044-021-01054-z](https://doi.org/10.1007/s10044-021-01054-z)

## Conference Publications

### Boosting Self-supervised Video-based Human Action Recognition (2022)
*LatinX in AI at NeurIPS 2022*
- Innovative approach to knowledge distillation in video tasks
- Enhanced self-supervised learning techniques
- Presented at premier machine learning conference

### Enhancing Self-supervision by Distilling Knowledge (2022)
*LatinX in AI at ECCV*
- Best doctoral consortium presentation award
- Novel approach to knowledge distillation
- Application to video understanding tasks

### Improving Dense Trajectories for Human Activities (2019)
*7th International Workshop on Biometrics and Forensics*
- Enhanced approach for action recognition
- Focus on simple human activities
- [DOI: 10.1109/iwbf.2019.8739244](https://doi.org/10.1109/iwbf.2019.8739244)

## Research Projects

### Video-Based Human Action Recognition
*PhD Research Project*
- Developed novel approaches to action recognition
- Implemented self-supervised learning techniques
- Created efficient knowledge distillation methods
- Achieved state-of-the-art results on benchmark datasets

### Key Trajectories for Action Recognition
*Master's Research Project*
- Designed innovative trajectory analysis methods
- Improved efficiency in action recognition
- Implemented real-time processing capabilities

### Ant Colony Optimization for Feature Selection
*Undergraduate Research Project*
- Applied bio-inspired algorithms to machine learning
- Enhanced feature selection in computer vision tasks
- Reduced computational complexity while maintaining accuracy

## Science Communication

### Technical Blog Posts
- Regular contributions on AI and Computer Vision topics
- Focus on making complex concepts accessible
- Practical tutorials and implementation guides

### Conference Presentations
- Presented research at international conferences
- Engaged with diverse academic audiences
- Developed effective scientific communication skills

## Technical Skills

### Programming Languages
- Python (Advanced)
- C++ (Intermediate)
- MATLAB (Intermediate)

### Deep Learning
- PyTorch
- TensorFlow
- Keras

### Computer Vision
- OpenCV
- Image Processing
- Video Analysis

### Development Tools
- Git
- Docker
- Linux/Unix

### Other Skills
- LaTeX
- API Development
- Database Management
- Cloud Computing (AWS)
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
