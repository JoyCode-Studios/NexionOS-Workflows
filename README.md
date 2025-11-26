# NexionOS Workflows

This repository contains the GitHub Actions workflows used to build, test, and package the NexionOS operating system.  
Instead of compiling locally — which can be slow on WSL or limited hardware — these workflows run on GitHub’s cloud runners, producing fast, reliable builds in minutes.

## What This Repository Does

- Stores all CI/CD workflows for NexionOS  
- Builds the OS image automatically on every push  
- Uploads compiled artifacts (e.g., `.img`, `.iso`)  
- Ensures reproducible builds across machines  
- Keeps the main NexionOS repo clean and lightweight  

This repo is **not** the OS source code itself — only the automation that builds it.

## How It Works

Whenever you push changes to the main NexionOS source repository:

1. GitHub Actions checks out the code  
2. Installs all required dependencies  
3. Installs Rust  
4. Builds the OS image  
5. Uploads the result as a downloadable artifact  

This allows you to compile NexionOS without waiting for long local builds.

## Workflow Files

All workflows live in:

```
.github/workflows/
```

Typical workflows include:

- `build.yml` — builds the OS image  
- `release.yml` (optional) — creates versioned releases  
- `test.yml` (optional) — runs automated checks  

## Using the Workflows

To trigger a build:

- Push to the main NexionOS repo  
- Or manually run the workflow from the **Actions** tab  

Once complete, download the artifact from the workflow run.

## Why a Separate Repository?

Keeping workflows in their own repo:

- Makes CI/CD modular  
- Keeps the main OS repo clean  
- Allows workflow updates without touching OS code  
- Lets you version and experiment with automation independently  

## License

This repository follows the same license as the main NexionOS project.
