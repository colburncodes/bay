---
layout: post
title: "Automated Deployment with GitHub Actions"
date: 2024-01-13 
blurb: "A guide to automation with the basics."
og_image: /assets/img/content/post-example/Banner.jpg
---

If you're like me, always eager to get your hands dirty with practical 
experience, you'll love this module. 

My goal is to cover the building block of GitHub Actions which allow 
you to define workflows and automate various tasks in your Git repositories.

By the end of this session, my goal is for you to walk away with a solid
foundation in using GitHub Actions and GitHub Pages for deployment.

Here I will describe the basic components of a GitHub Actions workflow file.

<b>Workflow:</b> A workflow is a set of one or more jobs that are executed
when specific events occur in a repository.

```yaml
name: My Workflow
on: 
  push:
    branches:
      -main
jobs:
  build:
    runs-on: ubuntu-latest
    steps: 
      - name: Checkout repo
        uses: actions/checkout@v3
```
<b>Job:</b> A job represents a sequence of steps that run on the same runner. Each
workflow can contain one or more jobs that run in parallel or sequentially. You'll
specify the runner `runs-on` attribute. Here, you're telling the workflow to run this
job on `ubuntu-latest`.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest

    steps: 
      - name: Checkout repo 
        uses: actions/checkout@v3
      - name: use node.js 
        uses: actions/setup-node@v3
        with:
          node-version: '18.x'
```

<b>Step:</b> A step is an individual task within a job. Each step 
performs a specific action, such as running a script or calling some external action.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Step 1
        run: echo "Hello from Step 1"
```

<b>Action:</b> An action is a reusable unit of code that peforms a specific task.
Actions are executed as part of a step for a job.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      # Other steps using custom or pre-built actions
```

[Part 2 - Configure GitHub Actons workflow](#part-2-configure-github-actions)