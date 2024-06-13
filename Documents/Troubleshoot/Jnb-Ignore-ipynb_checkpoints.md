# How to Delete and Ignore All .ipynb_checkpoints in GitHub Repositories

| FROM | DATE | URLs |
| :---: | :---: | :---: |
| Hongtao Hao | 2022-03-05 | [Main Webpage](https://hongtaoh.com/en/2022/03/05/delete-ipynb-checkpoints/)  &  [GitHub-Repo](https://github.com/hongtaoh/hongtaoh.github.io/blob/sources/content/en/blog/2022-03-05-delete-ipynb-checkpoints.md)|

The procedure is very similar to [delete .DS_Store File](/en/2020/11/03/delete-ignore-ds-store/).

You can delete `.ipynb_checkpoints` folder this way:

```bash
find . -name .ipynb_checkpoints -print0 | xargs -0 git rm -rf --ignore-unmatch
git add .
git commit -m "Remove .ipynb_checkpoints from everywhere"
git push
```

Then you can ignore all future `.ipynb_checkpoints` this way:

```bash
touch .gitignore
echo \.ipynb_checkpoints >> .gitignore
git add .
git commit -m "Creating .gitignore and ignore .ipynb_checkpoints"
git push
```
