# Mathilde Badufle Academic Website

This project is a minimal academic personal website built with Hugo and HugoBlox, based on the Academic CV / researcher-style template.

## Project Structure

```text
website/
├── .github/workflows/hugo.yml
├── .gitignore
├── package.json
├── config/_default/
│   ├── hugo.yaml
│   ├── languages.yaml
│   ├── menus.yaml
│   └── params.yaml
├── content/
│   ├── _index.md
│   ├── authors/admin/_index.md
│   ├── events/_index.md
│   ├── talks/_index.md
│   ├── teaching/_index.md
│   └── working-papers/_index.md
├── layouts/partials/hooks/head-end/site-style.html
├── static/uploads/README.md
├── go.mod
└── hugoblox.yaml
```

## What Is Already Configured

- Homepage sections for Hero, About, Research Interests, Research in Progress, CV, Teaching, Talks / Presentations, and Contact
- Author profile with your affiliations, research fields, and contact details
- Minimal academic styling with light colors, restrained typography, and responsive spacing
- A placeholder CV link at `/uploads/CV_Mathilde_Badufle.pdf`
- GitHub Pages deployment workflow
- Placeholder folders for future teaching, talks, and working papers

## Run Locally

Prerequisites:

- Hugo Extended
- Go
- Node.js and npm

1. Open a terminal in the `website/` folder.
2. Install the frontend dependency used by HugoBlox:

```bash
cd website
npm install
```

3. Initialize and download Hugo modules:

```bash
hugo mod tidy
```

4. Start the development server:

```bash
npm run dev
```

5. Open the local site:

```text
http://localhost:1313/
```

## Before Deployment

Update these values first:

1. Edit `go.mod` and replace `your-github-username` with your GitHub username.
2. Edit `config/_default/hugo.yaml` and replace:

```yaml
baseURL: 'https://your-github-username.github.io/'
```

3. Add your actual CV PDF at:

```text
static/uploads/CV_Mathilde_Badufle.pdf
```

4. Replace the placeholder links in:

```text
content/_index.md
content/authors/admin/_index.md
```

## Deploy To GitHub Pages

### Option A: User site

Use this if the repository will be named `your-github-username.github.io`.

1. Create a new GitHub repository named `your-github-username.github.io`.
2. Copy the contents of the `website/` folder into that repository.
3. Push to the `main` branch.
4. In GitHub, go to `Settings -> Pages`.
5. Under `Source`, select `GitHub Actions`.
6. Wait for the workflow in `.github/workflows/hugo.yml` to finish.

Your site will publish at:

```text
https://your-github-username.github.io/
```

### Option B: Project site

Use this if the repository has another name, such as `academic-website`.

1. Create the GitHub repository.
2. Update `config/_default/hugo.yaml` so the `baseURL` includes the repository name:

```yaml
baseURL: 'https://your-github-username.github.io/academic-website/'
```

3. Push to `main`.
4. In `Settings -> Pages`, select `GitHub Actions`.
5. Let the workflow deploy the site.

Your site will publish at:

```text
https://your-github-username.github.io/academic-website/
```

## Useful Commands

```bash
cd website
npm install
hugo mod tidy
npm run dev
npm run build
```

## Notes For Future Editing

- Add working papers later under `content/working-papers/`
- Add talks later under `content/talks/` or `content/events/`
- Replace the CV placeholder file in `static/uploads/`
- Update homepage text in `content/_index.md`
- Update profile metadata in `content/authors/admin/_index.md`
