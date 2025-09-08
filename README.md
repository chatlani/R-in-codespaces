This is a template repository for using R in Rstudio interface in GitHub Codespaces

To start this container, you should use the Dev Containers feature in VS Code. Here’s how:

1. Open the workspace folder (R-in-codespaces) in VS Code.

If prompted, select "Reopen in Container / codespaces: rebuild the container" or use the Command Palette (Ctrl+Shift+P) and run: codespaces: rebuild the container.

VS Code will build the container using the Dockerfile and settings in devcontainer.json.

After the container starts, the postAttachCommand (sudo rstudio-server start) will automatically run, starting RStudio Server inside the container.

 You do not need to manually run Docker commands; VS Code handles the build and start process for you.

 -------------------------------------------------------------------------------------------------------------------------------------
//Add a user with sudo privileges
sudo useradd -m -s /bin/bash aembaye2

su - aembaye2



 -------------------------------------------------------------------------------------------------------------------------------------
 Troubleshooting Common Errors

 1. User Switching Issues
If `su - aembaye2` fails, set `"remoteUser": "aembaye2"` in `.devcontainer/devcontainer.json` and rebuild the container.

 2. Git Dubious Ownership Error
Run: `git config --global --add safe.directory /workspaces/R-in-codespaces`

 3. GPG Signing Error on Commit
Run: `git config --global commit.gpgSign false`

 4. Push Fails Due to Git LFS Hook
If you see LFS warnings and push fails, remove the hook: `rm .git/hooks/pre-push`

# how to save your work and push to GitHub


git add .
git commit -m "your commit message"
git push origin main


