# How to Create and Host Your Resume Website

## Purpose
This guide explains how to create a personal resume website using Pelican (a static website generator) and host it on GitHub Pages. This guide is designed to be beginner-friendly, even for those new to Markdown, Git, static site generators, and GitHub. Below is the process step-by-step.

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

---

### 2. Install Pelican and Set Up Your Website

#### Install Pelican:
1. Open the command line (Terminal on Mac, Command Prompt or PowerShell on Windows).
2. Type this command to install Pelican:

    ```bash
    pip install pelican
    ```

    > *Note: If you don’t have Python installed, follow the instructions on the [Python website](https://www.python.org/downloads/) to install it first.*

#### Create a New Pelican Project:
1. Create a new folder where you want to keep your project (you can do this in your file explorer or by running `mkdir my-resume` in the command line).
2. Navigate into the folder using the command line:

    ```bash
    cd my-resume
    ```

3. Run this command to create a new Pelican project:

    ```bash
    pelican-quickstart
    ```

    > You’ll be asked a few questions, like the name of your site (you can just press **Enter** to accept the default).

---

### 3. Create Your Resume in Markdown

#### Convert Your Resume to Markdown:
1. Open your resume in a text editor (like Notepad or VSCode).
2. Use Markdown to format it. For example:

    - `#` for the title (like your name).
    - `##` for subheadings (like "Experience" or "Education").
    - `-` for bullet points.

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
2. Look for the line `THEME = "path_to_your_theme"`, and change the path to the theme you want to use. If this line does not exist, you can put it anywhere, but just not within the other code lines. For example:

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

**Q: I’ve uploaded my files to GitHub, but my website isn’t showing up. What did I do wrong?**

A: Make sure you’ve enabled **GitHub Pages** in the repository settings. Go to the **Settings** tab, scroll down to the **GitHub Pages** section, and select the **branch** (usually main or master) and set it to root. Then click **Save**. If you’ve done this and it’s still not showing, give it a few minutes for the changes to take effect.
