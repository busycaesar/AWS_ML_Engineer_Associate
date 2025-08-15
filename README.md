# Docusaurus Boilerplate Code

## Description

This is the Boilerplate Code to create a static website to publish notes, blogs etc. It uses markdown files to generate website content.

## Tech Stack
![Image Alt](https://skillicons.dev/icons?i=md)

## How it looks?

## Features

- Converts markdown files into static website.

## How to run the project?

Follow these steps to set up and deploy your Docusaurus-based documentation website:

1. Clone the Repository

```bash
git clone <repository-url>
cd <project-directory>
```

2. Install Dependencies

```bash
npm install
```

3. Add Documentation Content

- Place your Markdown files in the `docs/` directory.

4. Configure Site Metadata

- Update site title, description, and other metadata in `docusaurus.config.js`.

5. Preview the Website Locally

```bash
npm run serve
```

6. Set Custom Domain (Optional)

- Create a `CNAME` file inside the `static/` directory with your custom domain:

```txt
example.com
```

7. Deploy Changes

- Use the provided script to commit and deploy:

```bash
./push-changes.sh "Your commit message here"
```

- If no message is provided, a default will be used.

## Author
[Dev J. Shah](https://github.com/busycaesar)
