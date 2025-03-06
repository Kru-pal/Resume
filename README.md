# How to Create and Host Your Resume Website

## Purpose
This guide explains how to create a personal resume website using Pelican (a static website generator) and host it on GitHub Pages. This guide is designed to be beginner-friendly, even for those new to Markdown, Git, static site generators, and GitHub. Below is the process step-by-step.

Alignment with Technical Communication:
The purpose statement clearly defines the goal of the document, which aligns with Process Guideline 1: Know Your Purpose and Your Audience

## What You Need
Before starting, make sure you have:

- A resume (in any format; we’ll turn it into a special format called Markdown).
- Git installed on your computer.
- A GitHub account (for hosting the website).
- Pelican installed on your computer.
- Basic knowledge of the terminal/command line (this is where you’ll run some commands).

If you're new to Git or Markdown, I suggest reading some beginner tutorials before getting started.

## Steps to Create and Host Your Resume Website

### 1. Install Git and Set Up Your GitHub Account

#### Install Git:
- Go to [Git's official website](https://git-scm.com/) and download Git.
- Follow the installation instructions.

#### Create a GitHub Account:
- Go to [GitHub](https://github.com/) and sign up for a free account.

#### Create a New Repository on GitHub:
1. Once logged in to GitHub, click the “+” button in the top right corner and select **New repository**.
2. Name it something like `my-resume`.
3. Make sure to set the repository to **public** and click **Create repository**.

Alignment with Technical Communication:
This step follows Instructions Guideline 2: Follow the ABC Format by providing an abstract, a body and a conclusion. The numbered steps and clear commands align with Instructions Guideline 3: Use Numbered Lists in the Body.

---

### 2. Install Pelican and Set Up Your Website

#### Install Pelican:
1. Open the command line (Command Prompt Windows and not powershell).
2. Type this command to install Pelican:

    ```bash
    pip install pelican
    ```

    > *Note: If you don’t have Python installed, follow the instructions on the [Python website](https://www.python.org/downloads/) to install it first.*

#### Create a New Pelican Project:
1. Create a new folder where you want to keep your project.
2. Navigate into the folder using the command line:

    ```bash
    cd my-resume
    ```

3. Run this command to create a new Pelican project:

    ```bash
    pelican-quickstart
    ```

    > You’ll be asked a few questions, but you can just press **Enter** to accept the default values (except for the URL prefix):

    - **Where do you want to create your new website?**: Press **Enter** (use current directory).
    - **What will be the title of this website?**: What title you want your website to have.
    - **Who will be the author of this website?**: Your name.
    - **What will be the default language of this website?**: Press **Enter** (default is English).
    - **Do you want to specify a URL prefix?**: Type `y` and enter `https://username.github.io/my-resume` (replace `username` with your GitHub username).
    - **Do you want to enable article pagination?**: Press **Enter** (default is no).
    - **How many articles per page do you want?**: Press **Enter** (default is 10).
    - **What is your time zone?**: Press **Enter** (default is fine).
    - **Do you want to generate a tasks.py/Makefile to automate generation and publishing?**: Press **Enter** (default is yes).
    - **Do you want to upload your website using FTP?**: Press **Enter** (default is no).
    - **Do you want to upload your website using SSH?**: Press **Enter** (default is no).
    - **Do you want to upload your website using Dropbox?**: Press **Enter** (default is no).
    - **Do you want to upload your website using S3?**: Press **Enter** (default is no).
    - **Do you want to upload your website using Rackspace Cloud Files?**: Press **Enter** (default is no).
    - **Do you want to upload your website using GitHub Pages?**: Press **Enter** (default is yes).

    After this, Pelican will create the necessary files for your project.

---

### 3. Create Your Resume in Markdown

Alignment with Technical Communication:
This step follows Instructions Guideline 6: Lead Off Each Action Step With a Verb by starting each step with a clear action verb. 
It also aligns with Instructions Guideline 7: Remove Extra Information From the Step by keeping the steps concise and focused on the action.

#### Convert Your Resume to Markdown:
1. Open your resume in a text editor (like Notepad or VSCode).
2. Use Markdown to format it.

    Example of a resume in Markdown:

    ```markdown
    # Some One

    ## Contact Information
    - Email: some.one@gmail.com
    - Phone: (123) 456-7890

    ## Experience
    ### Software Developer at XYZ Corp.
    - Worked with a team to build web apps using C++ and JavaScript.

    ## Education
    - B.S. in Computer Science, University of Manitoba
    ```

#### Save the Resume:
- Save your resume as `resume.md` in the `/content` folder of your Pelican project.

---

### 4. Customize the Look (Optional)

#### Find a Theme:
- Go to the [Pelican Themes website](https://github.com/getpelican/pelican-themes) and choose a theme you like.
- Download the theme and move it to the `themes` folder (if there is no `themes` folder, you can create one) in your Pelican project.

#### Activate the Theme:
1. Open the file `pelicanconf.py` in your project folder.
2. Look for the line `THEME = "path_to_your_theme"`, and change the path to the theme you want to use. If this line does not exist, you can add it.
   For example:

    ```python
    THEME = "themes/the-theme"
    ```

---

### 5. Build and View Your Website

#### Build Your Website:
1. In your command line, make sure you’re inside the Pelican project folder.
2. Run this command to create the website:

    ```bash
    pelican content
    ```

    > This will create the website files inside the `output` folder.

#### Preview Your Website Locally:
1. To see your website on your computer before publishing it, run this command:

    ```bash
    pelican --listen
    ```

2. Open your web browser and go to [http://localhost:8000](http://localhost:8000) to see your website.

Alignment with Technical Communication:
This step follows Instructions Guideline 8: Use Bullets or Letters for Emphasis by using bullet points to highlight key actions (e.g., "Run this command"). It also aligns with Instructions Guideline 10: Keep a Simple Style by using short, direct sentences and avoiding unnecessary complexity.

---

### 6. Upload Your Website to GitHub

#### Initialize Git:
1. In your Pelican project folder, open the command line and run:

    ```bash
    git init
    ```

#### Add Files to Git:
1. Add all the files to Git with this command:

    ```bash
    git add .
    ```

#### Commit the Files:
1. Commit your changes with this command:

    ```bash
    git commit -m "Initial commit"
    ```

#### Link Your GitHub Repository:
1. In your GitHub account, go to your new repository and copy the URL (e.g., `https://github.com/yourusername/my-resume.git`).
2. In the command line, link your local folder to the GitHub repository:

    ```bash
    git remote add origin https://github.com/yourusername/my-resume.git
    ```

#### Push Your Files to GitHub:
1. Push your website to GitHub with this command:

    ```bash
    git push -u origin master
    ```

---

### 7. Set Up GitHub Pages

To deploy your site to GitHub Pages, follow these steps:

1. **Commit Your Files to GitHub:**
   - Open the command line in your project folder.
   - Run the following commands to add, commit, and push your changes:

     ```bash
     git add .
     git commit -am "First commit"
     ```

2. **Generate Your Site:**
   - Run this command to generate the website using Pelican:

     ```bash
     pelican content -s publishconf.py
     ```

   - This will create your website in the `output` folder.

3. **Deploy to GitHub Pages:**
   - Use `ghp-import` to move the generated site to the `gh-pages` branch:

     ```bash
     ghp-import output -b gh-pages
     ```

   - Push the changes to GitHub:

     ```bash
     git push origin gh-pages
     ```

4. **View Your Website:**
   - After the push is complete, visit your website at the following URL:

     ```
     https://yourusername.github.io/my-resume/
     ```

   - Replace `yourusername` with your GitHub username and `my-resume` with your repository name.

Your resume website will now be live on GitHub Pages!

---

### 8. View Your Live Website
- After a few minutes, your website will be live! Visit:

    ```markdown
    https://yourusername.github.io/my-resume/
    ```

You’ve now created and hosted your resume as a website using Pelican and GitHub Pages!

Alignment with Technical Communication:
This section follows Instructions Guideline 10: Keep a Simple Style by providing a clear, concise conclusion to the process. It also aligns with Process Guideline 3: Use an Objective Point of View by focusing on the result (the live website) rather than directing the reader to perform additional actions.

---

## Resources
- [Markdown Guide](https://www.markdownguide.org/)
- [Pelican Documentation](https://docs.getpelican.com/en/stable/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)

---

## FAQ

**Q: Why is Markdown better than writing raw HTML for my resume?**

A: Markdown is easier to write and read than HTML. You don’t have to learn complicated tags or code. It helps you focus on your resume content without worrying about all the extra formatting. Also, you can quickly turn Markdown into other formats like HTML, PDF, or Word documents.

**Q: I changed the Markdown version of my resume, so why don’t I see the changes when I refresh the website in my browser?**

A: If you don’t see the changes right away, it’s likely because your browser is showing an old version of the website. Try clearing the cache or doing a hard refresh by pressing `Ctrl + F5` (on Windows) or `Cmd + Shift + R` (on Mac). Also, make sure you’ve saved, committed, and pushed your changes to GitHub, and give it a little time for the updates to show up.

