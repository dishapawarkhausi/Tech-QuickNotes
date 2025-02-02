# 🚀 Tech-QuickNotes

**How to clone a subfolder of a GitHub repository**

##### Solution:
Git does not support cloning a specific subfolder directly, but you can achieve this using `svn`:

```sh
svn checkout https://github.com/<user>/<repo>/trunk/<subfolder> --depth infinity
```

Replace `<user>`, `<repo>`, and `<subfolder>` with the respective repository owner, repository name, and the subfolder path you want to clone.

Alternatively, you can use sparse checkout with Git:

```sh
git clone --no-checkout https://github.com/<user>/<repo>.git
cd <repo>
git sparse-checkout init --cone
git sparse-checkout set <subfolder>
git checkout
```

This method allows cloning only the required subfolder while keeping the repository structure intact.

---
