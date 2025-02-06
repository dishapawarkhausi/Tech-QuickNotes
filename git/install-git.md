# 🚀 Tech-QuickNotes

**How to install Git and set up a global username and email**

##### Solution:
Git is a distributed version control system that you need to install before using it. Follow these steps to install Git and configure your global username and email:

1. **Install Git:**
   - **Windows:** Download and install Git from [Git for Windows](https://git-scm.com/download/win).
   - **MacOS:** Install Git using Homebrew:
     ```sh
     brew install git
     ```
   - **Linux:** Install Git using the package manager:
     - **Debian/Ubuntu:**
       ```sh
       sudo apt update
       sudo apt install git
       ```
     - **Fedora:**
       ```sh
       sudo dnf install git
       ```
     - **Arch Linux:**
       ```sh
       sudo pacman -S git
       ```

2. **Verify the Installation:**
   ```sh
   git --version
   ```
   This should display the installed Git version.

3. **Set Up a Global Username and Email:**
   ```sh
   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   ```

4. **Verify the Configuration:**
   ```sh
   git config --global --list
   ```
   This will display your configured username and email.

Now Git is installed and configured successfully! 🎉
