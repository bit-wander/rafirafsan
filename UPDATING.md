# Guide: Updating Your Academic Website

This website is designed to be extremely easy to maintain. Since it is hosted on GitHub and built automatically via GitHub Actions, you can make updates **directly in your web browser on GitHub**—no coding tools or terminal commands required on your local machine.

Any changes you push to the `main` branch will automatically build and deploy, going live in about **2 minutes**.

---

## 1. Updating Your Biography & Tagline

### To update your tagline or social links:
1. Open [hugo.yaml](file:///home/rafsan/Projects/portfolio/hugo.yaml) on GitHub.
2. Click the pencil icon to edit the file.
3. Update the fields under `params`:
   ```yaml
   params:
     description: "Computer Science Graduate | Computational Social Science"
     author: "Rafi Rafsan"
     email: "rafi.rafsan.contact@gmail.com"
     tagline: "Your new one-line tagline goes here."
     github: "https://github.com/bit-wander"
     linkedin: "https://www.linkedin.com/in/your-profile"
   ```
4. Commit and save the changes.

### To update your bio paragraphs or research interests:
1. Open [content/_index.md](file:///home/rafsan/Projects/portfolio/content/_index.md).
2. Click edit and update the text.
3. To add/change research interests, modify the list at the top (front matter):
   ```yaml
   research_interests:
     - "Computational Social Science"
     - "Autonomous Systems"
     - "UAV / Drone Systems"
     - "New Interest Here"
   ```
4. Update the biography paragraphs below the `---` line.
5. Commit and save the changes.

---

## 2. Adding a New Paper, Project, or Talk

All your research and presentations are stored in [data/papers.yaml](file:///home/rafsan/Projects/portfolio/data/papers.yaml).

### To add a new paper or talk:
1. If you have a PDF, upload it to the `static/files/` directory (e.g., `static/files/my_new_paper.pdf`).
2. Open [data/papers.yaml](file:///home/rafsan/Projects/portfolio/data/papers.yaml) and click edit.
3. Append a new block at the bottom following this format:
   ```yaml
   - title: "Title of Your New Paper"
     authors: ["Rafi Rafsan", "Coauthor Name"]
     year: 2026
     status: "under review" # Options: "published", "accepted", "under review", "working paper", "academic project"
     venue: "Journal or Conference Name"
     pdf: "files/my_new_paper.pdf" # Path to the uploaded PDF
     abstract: "A one-paragraph abstract summarizing your work."
     job_market_paper: false # Set to true if you want to feature it at the top
     tags: ["Machine Learning", "Computational Science"]
   ```
4. Commit and save.

### To mark a paper as published:
Change its `status` from `"working paper"` or `"under review"` to `"published"`, and fill in the `venue` (journal/conference name) and `year`.

### To highlight a paper at the top (Featured):
Change `job_market_paper: true` on that paper, and make sure all other papers have `job_market_paper: false`.

---

## 3. Adding or Updating Software Projects

Your software projects are stored in [data/projects.yaml](file:///home/rafsan/Projects/portfolio/data/projects.yaml).

### To add a software project:
1. Open [data/projects.yaml](file:///home/rafsan/Projects/portfolio/data/projects.yaml) and click edit.
2. Append a new block at the bottom:
   ```yaml
   - name: "NewProject"
     description: "A short, one-sentence description of what your software does."
     url: "https://github.com/bit-wander/new-project"
     language: "Python / PyTorch"
   ```
3. Commit and save.

---

## 4. Updating Your CV / Resume
When you have an updated CV:
1. Save your CV as a PDF named `cv.pdf`.
2. Upload and overwrite the file at `static/files/cv.pdf`.
3. The download button on the homepage and in the navigation bar will automatically point to your new CV.

---

## 5. Changing Your Profile Photo
To update your profile picture:
1. Crop your new photo to a square ratio (for a clean circular display).
2. Save it as a JPEG named `photo.jpg`.
3. Upload and overwrite the file at `static/images/photo.jpg`.

---

## 6. Adding Teaching Experience (Optional)
If you gain teaching or TA roles in the future:
1. Open [data/teaching.yaml](file:///home/rafsan/Projects/portfolio/data/teaching.yaml) (currently empty `[]`).
2. Replace the contents with your roles:
   ```yaml
   - course: "CSE 101: Introduction to Computer Science"
     role: "Teaching Assistant"
     institution: "Rajshahi University of Engineering & Technology"
     term: "Fall 2025"
   ```
3. Make sure to update the menu in `hugo.yaml` and the homepage layout to display it if you decide to add a teaching section.
