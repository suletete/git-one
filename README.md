# Hands-On: Version Control System & Why It Is Needed

## What is a Version Control System (VCS)?
A Version Control System (VCS) is a vital tool in software development, designed to track and manage changes to code or documents over time. It enables multiple developers to collaborate on the same project efficiently by controlling and merging changes made by different team members.

Imagine you're working in a team on a project to create a website for an AI startup company. The website includes various sections like Home, About Us, Services, and Contact Information. Each member of your team is responsible for a different section of the site. Without a Version Control System (VCS), managing this collaboration efficiently would be challenging.

## Challenges Without a VCS

### Overwriting Work
If a team member, Tom, makes changes to the home page file `index.html` to update the navigation, and at the same time, another team member, Jerry, makes changes to add contact information to the footer of the same `index.html` file, there will be a conflict. Without VCS, the last person to upload their version of the file to the shared folder or server would overwrite the other person's changes, resulting in lost work.

## How VCS Solves These Problems

### Concurrent Development
With a VCS, each team member can work on their sections simultaneously without fear of overwriting each other's work. The VCS tracks all changes and manages different versions of the files, allowing changes to be merged together eventually.

## Introducing Git: A Leading Version Control System
Git is a tool that helps teams collaborate on projects like building a website. It keeps track of all changes, allowing developers to revert to a working version if something goes wrong. It also enables multiple people to work on the same project without conflicts.

## Git Setup with Tom and Jerry

### Initial Setup:
1. Both Tom and Jerry install Git on their computers.
2. They clone (download) the project repository from a central repository (e.g., GitHub, GitLab, or Bitbucket) to their local machines. This gives them each a complete copy of the project, including all its files and version history.

```sh
# Clone the repository
 git clone https://github.com/example/repository.git
```

### Tom and Jerry Start Working:
1. They pull the latest changes from the central repository to ensure they start with the most current version of `index.html`.
2. They each create a new branch:
   - Tom names his branch `update-navigation`.
   - Jerry names his branch `add-contact-info`.

```sh
# Tom creates and switches to his branch
 git checkout -b update-navigation

# Jerry creates and switches to his branch
 git checkout -b add-contact-info
```

### Making Changes:
1. Tom updates the navigation bar in `index.html`.
2. Jerry adds contact information to the footer of `index.html`.
3. They commit their changes to their respective branches.

```sh
# Tom commits his changes
 git add index.html
 git commit -m "Updated navigation bar"

# Jerry commits his changes
 git add index.html
 git commit -m "Added contact info to footer"
```

### Merging Changes:
1. Tom pushes his branch to the central repository and creates a Pull Request (PR) for `update-navigation`.

```sh
# Push Tom's branch
 git push origin update-navigation
```

2. The team reviews Tom's changes and merges his PR into the main branch.
3. Jerry pulls the latest updates from the main branch to include Tom’s changes.

```sh
# Switch to main and pull latest changes
 git checkout main
 git pull origin main
```

4. Jerry resolves any conflicts if they arise, then pushes his updated branch and creates a PR for `add-contact-info`.

```sh
# Push Jerry's branch
 git push origin add-contact-info
```

5. Once approved, Jerry’s changes are merged into the main project.

