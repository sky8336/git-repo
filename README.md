# repo

Repo is a tool built on top of Git.  Repo helps manage many Git repositories,
does the uploads to revision control systems, and automates parts of the
development workflow.  Repo is not meant to replace Git, only to make it
easier to work with Git.  The repo command is an executable Python script
that you can put anywhere in your path.

* Homepage: https://code.google.com/p/git-repo/
* Bug reports: https://code.google.com/p/git-repo/issues/
* Source: https://code.google.com/p/git-repo/
* Overview: https://source.android.com/source/developing.html
* Docs: https://source.android.com/source/using-repo.html
* [Submitting patches](./SUBMITTING_PATCHES.md)

# myrepo
## how to install myrepo
REPO_DIR=${HOME}/bin  
mkdir $REPO_DIR  

curl https://raw.githubusercontent.com/sky8336/git-repo/master/repo > $REPO_DIR/myrepo  
chmod a+x $REPO_DIR/myrepo  

echo "PATH=$PATH:$REPO_DIR" >> $HOME/.bashrc  
echo "PATH=$PATH:$REPO_DIR" >> $HOME/.zshrc  

using myrepo to avoid overwriting your repo in $REPO_DIR  

## repo init & sync
mkdir your-project-root-dir  
cd your-project-root-dir  

myrepo init -u http://github.com/sky8336/manifest --no-repo-verify  
myrepo sync  
