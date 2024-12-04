---
layout: page
icon: fas fa-briefcase
order: 3
toc: true
excerpt_separator: <!--more-->
---

<div class="page-content-wrapper">
    <nav id="custom-sidebar">
        <div class="sidebar-header">
            <h4 class="mb-0">Navigation</h4>
        </div>
        <ul class="nav flex-column">
            <li class="nav-item">
                <a class="nav-link" href="#professional-experience">Professional Experience</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#academic-experience">Academic Experience</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#industry-experience">Industry Experience</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#education">Education</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#professional-development">Professional Development</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#awards--honors">Awards & Honors</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#professional-service">Professional Service</a>
            </li>
        </ul>
    </nav>
    
    <div class="main-content markdown-content">
        {% capture my_content %}
# Professional Experience

## Academic Experience

### Researcher - Advanced Artificial Intelligence Group
*2017 - 2024*
- Led research in video-based human action recognition
- Developed innovative approaches using self-supervised learning and knowledge distillation
- Published multiple papers in high-impact journals and conferences
- Collaborated with international research teams

### Assistant Professor - Advanced Artificial Intelligence Group
*2023*
- Designed and prepared educational materials for machine learning and data science courses
- Mentored three research groups in innovative artificial intelligence projects
- Guided the development of an automatic tool for extracting insights from scientific papers
- Contributed to curriculum development and research initiatives

### Adjunct Professor | Tecnológico de Monterrey
*2022 - Present*
- Design and teach advanced AI and Computer Vision courses
- Mentor students in research projects
- Develop practical coursework and assignments
- Collaborate with faculty on curriculum development

### Research Assistant | Computer Vision Lab
*2020 - Present*
- Lead research projects in action recognition
- Implement and evaluate deep learning models
- Publish research findings in top-tier conferences
- Collaborate with international research teams

## Industry Experience

### Freelance Developer
*2018 - 2020*

#### Hair Transplant Application
- Developed backend API and mobile applications for Android and iOS
- Implemented visualization features for hair transplant procedures
- Managed full-stack development lifecycle

#### Data Analysis for Mambolytics
- Analyzed financial institution data to extract meaningful insights
- Created data visualizations for stakeholder communication
- Completed project under tight three-month timeline

#### Healthcare Portal
- Built responsive front-end using TypeScript
- Developed user-friendly interfaces for healthcare professionals
- Implemented patient-doctor communication features

### Fiware Initiative
*2017*
- Designed and developed the first version of the Encryption layer for Generic Enabler
- Implemented secure data transmission and storage services
- Contributed to IoT infrastructure development

### CODES Developer
*Aug - Dec 2016*
- Developed mobile applications using Xamarin for iOS and Android
- Worked on SIGI project for route and inventory management
- Implemented UI design and API integration

### Research Stay at ITESM
*Jan - May 2016*
- Conducted research on iOS application security
- Worked under Dr. Miguel Mendoza, President of the Mexican Society of AI
- Developed security-focused mobile applications

### CONADEIP FBA iOS Developer
*2015*
- Led development of "Conadeip FBA" iOS application
- Managed complete mobile application lifecycle
- Implemented sports-related features and functionality

## Education

### PhD in Computer Science
*Tecnológico de Monterrey, 2024*
- Thesis: "Enhancing Video-Based Human Action Recognition Model Training through Knowledge Distillation"
- GPA: 99.89/100
- Awards:
  - Second place in "José Negrete" best thesis award
  - Medal of Merit at graduation
  - Outstanding thesis recognition

### Master's in Computer Science
*Tecnológico de Monterrey, 2018*
- Thesis: "Action Recognition by Key Trajectories"
- GPA: 97.38/100
- Graduated with honors
- Highest average grade in December 2018 generation

### Computer Systems Engineering
*Tecnológico de Monterrey, 2016*
- GPA: 94.63/100
- Awards:
  - Honorable mention for outstanding performance
  - Highest average grade award (May 2016 generation)
  - Academic Excellence Acknowledgement

## Professional Development

### Certifications
- Deep Learning Specialization by DeepLearning.AI (2021)
  - Neural Networks and Deep Learning
  - Improving Deep Neural Networks
  - Structuring Machine Learning Projects
  - Convolutional Neural Networks
  - Sequence Models

- OpenCV University Gold Certificates (2022)
  - Deep Learning with PyTorch
  - Computer Vision Fundamentals in Python
  - Computer Vision Fundamentals in C++

- Additional Certifications
  - AWS Machine Learning Foundations
  - Kaggle: Python, Machine Learning (Intro & Intermediate)
  - Web of Science: Peer Review, Citation, and Scientific Review

## Awards & Honors

- Second place in "José Negrete" best thesis award from Mexican Society for AI
- Medal of Merit at PhD graduation (GPA: 99.89/100)
- Outstanding thesis recognition
- Highest average grade in Master's program (December 2018)
- Academic Excellence Award in Bachelor's program
- Multiple conference presentation awards

## Professional Service

### Reviewer
- Journal of Imaging (2023-Present)
- Mathematical and Computational Applications (2022-Present)
- Pattern Analysis and Applications (2021-Present)

### Teaching Assistant
- Advanced Computer Vision (2023)
- Machine Learning Fundamentals (2022)
- Data Structures and Algorithms (2021)
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
