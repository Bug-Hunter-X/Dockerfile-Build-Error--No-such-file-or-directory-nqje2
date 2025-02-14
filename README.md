# Dockerfile Bug: Missing requirements.txt or Permissions

This repository demonstrates a common error when building Docker images: issues with the `requirements.txt` file or file permissions. The original `Dockerfile` contains this error, and a corrected version (`Dockerfile_fixed`) is provided.

## Bug

The original `Dockerfile` attempts to install dependencies using `pip3 install -r requirements.txt`.  However, it fails if:

1. The `requirements.txt` file is missing from the directory context.
2.  The user doesn't have appropriate permissions to access the file or execute commands.

## Solution

The corrected `Dockerfile_fixed` addresses these issues by:

1. Ensuring the `requirements.txt` file is included correctly.
2. Using a more robust approach to handle potential permission problems. (e.g., using a non-root user).