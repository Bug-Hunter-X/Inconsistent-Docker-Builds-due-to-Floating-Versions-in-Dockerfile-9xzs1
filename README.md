# Inconsistent Docker Builds due to Floating Versions

This repository demonstrates a common Dockerfile error that leads to inconsistent builds due to the use of floating versions for the base image and dependencies.  The `Dockerfile` showcases the error, and `Dockerfile_fixed` provides a corrected version.

## Problem
The original Dockerfile uses `ubuntu:latest` and installs Python and its dependencies without specifying versions. This can result in builds failing or producing unexpected results over time, as updates to `ubuntu:latest`, Python, or packages might introduce breaking changes.

## Solution
The corrected Dockerfile, `Dockerfile_fixed`, addresses these issues by:

1.  Using a specific Ubuntu version instead of `latest`.
2.  Specifying exact versions of Python and the dependencies using `python3.9` and pinning package versions in `requirements.txt`

This ensures reproducibility and prevents unexpected build failures in the future.  Always use specific versions to maintain consistency and stability in your Docker images.