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
## how to install myrepo [First time setup]
REPO_DIR=${HOME}/bin  
mkdir $REPO_DIR  

curl https://raw.githubusercontent.com/sky8336/git-repo/master/repo > $REPO_DIR/myrepo  
chmod a+x $REPO_DIR/myrepo  

echo "PATH=$PATH:$REPO_DIR" >> $HOME/.bashrc  
echo "PATH=$PATH:$REPO_DIR" >> $HOME/.zshrc  

using myrepo to avoid overwriting your repo in $REPO_DIR  

NOTE: mostly, you just need do it once.  

##### get repo from gitlab with your private token
curl 121.196.xxx.xxx:8080/Boardx/git-repo/raw/master/repo?private_token=G5NUJ9Hxxxxxxxxxxxxx > myrepo  

## repo init & sync
mkdir your-project-root-dir  
cd your-project-root-dir  

myrepo init --no-repo-verify -u http://github.com/sky8336/manifest  
myrepo sync  

### vimcfg_bundle.xml
myrepo init --no-repo-verify -u http://github.com/sky8336/manifest --manifest-name=vimcfg_bundle.xml  
myrepo sync  

### wowotechX.xml
myrepo init --no-repo-verify -u http://github.com/sky8336/manifest -m wowotechX.xml  
myrepo sync  

## OpenEmbedded/Yocto Linux BSP for NXP Auto platforms
### required tools
sudo apt-get install chrpath texinfo  

### Download the Yocto Project Environment into your directory:
mkdir fsl-auto-yocto-bsp  
cd fsl-auto-yocto-bsp  
myrepo init -u https://source.codeaurora.org/external/autobsps32/auto_yocto_bsp -b alb/master  
myrepo sync  

This will download the sources for the latest NXP Auto Linux BSP (from the branch alb/master),  
structured ontop of the Yocto rocko release and upstream NXP QorIQ SDK.  

Build an image ...:  
refer to helpme/fsl_autoyocto_bsp_README  

