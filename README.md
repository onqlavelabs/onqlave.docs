# To start making changes to the repo + basic usage of GIT
- Install [git](https://github.com/git-guides/install-git#install-git-on-mac)
- Install [git cli](https://cli.github.com/manual/installation) 
- Clone the repository  <code>gh repo clone onqlavelabs/onqlave.docs</code>
- Change to the new directory created  <code>cd onqlave.docs</code>
- Make your changes (add, remove, change files and folder)
- Add changes to the commit  <code>git add -A</code>
- Commit changes  <code>git commit -m"your description about the change"</code>
- Push changes <code>git push</code>
- You should be able to see the changes in upstream repo
- To get the latest changes from upstream repo <code>git pull</code>


# To run the mkdocs engine on your local machine:

**1. Have your python && pip installed and ready**

**2. Instal mkdocs and mkdocs-material theme:**
```
pip install mkdocs-material
```
**3. Navigate to the root of _onqlave.docs_ and run**
```
mkdocs serve
```
