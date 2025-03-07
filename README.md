# Resume Website README

## Purpose
This README provides a step-by-step guide for creating and hosting a static resume website using Pelican, a Python-based static site generator. The goal is to help users build a professional, easily updatable online resume hosted on GitHub Pages. This guide is designed for individuals with basic knowledge of Markdown and the command line but who are new to static site generators and web hosting.

The instructions in this README are structured to align with principles from Andrew Etter’s *Modern Technical Writing*, emphasizing clarity, simplicity, and user-centered design. By following this guide, you will create a clean, accessible, and maintainable resume website that adheres to modern technical writing standards.

---

## Prerequisites
Before starting, ensure you have the following tools and resources:

1. **Basic Command-Line Knowledge**: Familiarity with basic terminal commands like `cd`, `mkdir`, and `ls`. If you're new to the command line, consider reviewing a beginner’s guide.
2. **Git**: Git is essential for version control and deploying your site. Install Git from [git-scm.com](https://git-scm.com/).
3. **GitHub Account**: A free GitHub account is required to host your site. Sign up at [github.com](https://github.com/).
4. **Pelican**: Pelican is a static site generator that converts Markdown files into HTML. Install it using Python’s package manager, pip. Follow the [Pelican documentation](https://docs.getpelican.com/en/stable/) for installation instructions.
5. **Markdown**: A lightweight markup language for formatting your resume. Learn Markdown basics at [The Markdown Guide](https://www.markdownguide.org/).
6. **Text Editor**: Use a code editor like Visual Studio Code, Sublime Text, or Atom for editing Markdown files.

---

## Instructions
### 1. Setting Up Your Project
As Andrew Etter emphasizes in *Modern Technical Writing*, “organization is the bedrock of effective documentation.” A well-structured project directory ensures clarity and ease of use throughout the development process.

#### Create a GitHub Repository
1. Go to GitHub: [Create a New Repository](https://github.com/new).
2. **Repository name**: Choose a name for your project (e.g., `resume`).
3. Set the repository to **Public**.
4. **DO NOT** check “Add a README” (Pelican will generate files for us).
5. Click **Create repository**.

#### Clone the Repository to Your Computer
1. Copy the repository URL from GitHub (e.g., `https://github.com/your-username/resume.git`).
2. Open Git Bash and run:
   ```
   git clone https://github.com/your-username/resume.git
   cd resume

This downloads the repository to your local machine and moves into the project folder.

#### Set Up Pelican

1.  Run the following command to initialize Pelican:
```
    pelican-quickstart
```    
3.  Follow the prompts:
    
    -   **Where should I create your new Pelican site?**  → Press Enter (use the current directory).
        
    -   **Site title**: Enter your website name.
        
    -   **Author name**: Enter your name.
        
    -   **Site URL**: Use  `https://your-username.github.io/resume`.
        
    -   **Time zone**: Choose your time zone (e.g.,  `UTC`,  `America/Winnipeg`).
        
    -   **Do you want to generate a Fabfile/Makefile?**  → No.
        
    -   **Do you want an auto-reload script?**  → No.
        
    -   **Do you want to upload using FTP?**  → No.
        
    -   **Do you want to use GitHub Pages?**  → Yes.
        

This creates the necessary Pelican project files inside your repository, maintaining a clean and structured workflow, as recommended by Etter.

---

### 2. Creating Your Resume Page
Pelican generates websites from Markdown files, making it an ideal tool for creating a resume website. As Etter notes, “technical writing should focus on clarity,” and Markdown’s simplicity ensures that your content is easy to read and maintain.

1. Navigate to the `content` directory and create a new Markdown file for your resume:
   ```
   cd content
   touch resume.md
   ```

2. Open `resume.md` in your text editor and add your resume content using Markdown formatting. Here’s an example structure:
   ```
   # John Doe

   ## Contact Information
   - **Email**: john.doe@example.com
   - **Phone**: (555) 555-5555
   - **LinkedIn**: [John's LinkedIn](https://www.linkedin.com/in/johndoe)

   ## Objective
   A results-driven software developer with experience in building web applications and a passion for learning new technologies.

   ## Education
   - **University of XYZ** — B.S. in Computer Science, 2024
       - Relevant Coursework: Data Structures, Algorithms, Web Development

   ## Experience
   - **Company ABC** — Software Developer, 2023–2024
       - Developed web applications using React.js, improving load times by 20%.
       - Led a team of 3 developers in building a new feature for the company’s flagship product.

   ## Skills
   - **Languages**: Python, JavaScript, Java
   - **Frameworks**: React.js, Node.js
   - **Tools**: Git, Docker, Jenkins
   ```

   When writing your resume, keep Etter’s advice in mind: “write for your audience.” Structure your content to highlight the most important information (e.g., contact details, skills, and experience) at the top.

---

### 3. Linking Your Resume Page
To ensure your resume is accessible from the homepage, you need to link it in the `index.md` file. Etter emphasizes the importance of clear navigation, stating that users should be able to find key information quickly.

1. Open or create `index.md` in the `content` directory:
   ```
   touch index.md
   ```

2. Add a link to your resume in `index.md`:
   ```
   # Welcome to My Resume Website

   This is my personal online resume. Click the link below to view my full resume:

   [Resume](resume.html)
   ```

   This creates a clear and intuitive navigation path for users, aligning with Etter’s principle of user-centered design.

---

### 4. Customizing the Theme (Optional)
Pelican allows you to customize the appearance of your site using themes. While the default theme is functional, a personalized theme can enhance the professionalism of your website. As Etter notes, “consistency is key to effective documentation.”

1. Browse the [Pelican Themes](https://github.com/getpelican/pelican-themes) repository to find a theme you like.
2. Download the theme and specify its path in `pelicanconf.py`:
   ```
   THEME = "/path/to/your/theme"
   ```

   Using a theme ensures a cohesive and professional design, which reflects well on your personal brand.

---

### 5. Building and Serving the Site Locally
Before deploying your site, it’s important to preview it locally to ensure everything looks correct. Etter highlights the importance of verification in technical writing.

1. Build the site using Pelican:
   ```
   pelican content
   ```

2. Serve the site locally using Python’s built-in HTTP server:
   ```
   cd output
   python3 -m http.server
   ```

3. Open your browser and navigate to `http://localhost:8000` to preview your site.

---

### 6. Deploying the Site to GitHub Pages
GitHub Pages is a free hosting service for static websites. Deploying your site ensures it’s accessible to anyone online. Etter emphasizes the importance of making documentation (or in this case, your resume) easily accessible.

1. Generate the static files using Pelican:
   ```
   pelican content -s publishconf.py
   ```

This builds the site based on your Markdown content.

2.  Use the  `ghp-import`  tool to push your site to the  `gh-pages`  branch:
    
   ```
    ghp-import output -b gh-pages
    git push origin gh-pages
   ```
    
   This moves the generated static files to the  `gh-pages`  branch, which GitHub Pages will serve as your website.
    
3.  View your live website:
```
    https://your-username.github.io/resume
```    
Replace  `your-username`  with your actual GitHub username.

----------

### 7. Maintaining and Updating Your Website

Etter advises that technical documents should be easy to update. To update your resume:

1.  Edit the  `resume.md`  file inside the  `content`  directory.
    
2.  Regenerate the site using Pelican:
```
pelican content -s publishconf.py
   ```
This converts your Markdown file into HTML again.
    
4.  Deploy the updated version to GitHub Pages:
```
    ghp-import output -b gh-pages
    git push origin gh-pages
   ``` 
   Your website will now reflect the changes.

---

## Further Resources/Readings
Here are some additional resources to deepen your understanding:

1. [Pelican Documentation](https://docs.getpelican.com/en/stable/)
2. [Markdown Guide](https://www.markdownguide.org/)
3. [GitHub Pages Documentation](https://docs.github.com/en/pages)
4. [Modern Technical Writing by Andrew Etter](https://www.amazon.com/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS)

---

## FAQ

### Q: Why is Markdown better than writing raw HTML?
Markdown is simpler and more readable than raw HTML, especially for technical documentation. It allows you to focus on the content without worrying about the details of HTML tags. It’s also easily convertible into other formats, including HTML, PDF, and DOCX.

### Q: I changed the Markdown version of my resume, but why don’t I see the changes when I refresh the website in my browser?
Changes might not appear immediately due to browser caching. Try clearing your browser cache or using a hard refresh (Ctrl + F5) to load the latest version of the page.

---

## Credits
- **Darab Khan** – Creator of the Resume Website and Contributor to README
- **Andrew Etter** – For the insights shared in *Modern Technical Writing*
- **Pelican Themes** – Custom theme used from Pelican Themes
- **Markdown Guide** – For assisting with formatting resume content in Markdown


















