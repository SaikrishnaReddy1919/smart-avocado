---
title: How to create a pull request in Github?
date: 2020-10-07T04:09:36.255Z
thumb_img_path: /images/introduction-to-github-slideshare-7-638.jpg
template: post
---
![github-workflow-image](https://image.slidesharecdn.com/introductiontogithubslideshare-150913080822-lva1-app6892/95/introduction-to-github-slideshare-7-638.jpg?cb=1442131732)
### If you ever want to contribute to a project on github the first step is to fork that project. Below are the simplest steps that you can follow to contribute to an open source project.

Go to the repo that you want to work on. Once you are there there, click on the Fork button in the top-right corner. This creates a new copy of that project(say:demoProject) under your GitHub user account with a URL like:

**`https://github.com/<YourUserName>/demoProject`**

This copy under your account includes all the code, branches, and commits from the original repo.

Next, clone the repo to your local machine by opening the terminal on your computer and running the command:

**`git clone https://github.com/<YourUserName>/demoProject`**

Once the repo is cloned, you need to do two things:

You have to create a new branch by using the command:

**`git checkout -b new_branch`**

Create a new remote for the upstream repo with the command:(this is to create a pull request after you made changes to the cloned repo and you want to submit changes for review.)

**`git remote add upstream https://github.com/<Actual-user>/<Original-repo>`**

In this case, "upstream repo" refers to the original repo you created your fork from.

Now you can make changes to the code. The following code creates a new branch, makes an arbitrary change, and pushes it to new_branch:

<iframe
  src="https://carbon.now.sh/embed?bg=rgba(74%2C144%2C226%2C1)&t=material&wt=sharp&l=auto&ds=true&dsyoff=20px&dsblur=68px&wc=true&wa=true&pv=12px&ph=25px&ln=false&fl=1&fm=Droid%20Sans%20Mono&fs=14px&lh=152%25&si=false&es=2x&wm=false&code=%2524%2520git%2520checkout%2520-b%2520new_branch%250ASwitched%2520to%2520a%2520new%2520branch%2520%25E2%2580%2598new_branch%25E2%2580%2599%250A%2524%2520echo%2520%25E2%2580%259Csome%2520test%2520file%25E2%2580%259D%2520%253E%2520test%250A%2524%2520cat%2520test%250ASome%2520test%2520file%250A%2524%2520git%2520status%250AOn%2520branch%2520new_branch%250ANo%2520commits%2520yet%250AUntracked%2520files%253A%250A%2520%2520(use%2520%2522git%2520add%2520%253Cfile%253E...%2522%2520to%2520include%2520in%2520what%2520will%2520be%2520committed)%250A%2520%2520%2520%2520test%250Anothing%2520added%2520to%2520commit%2520but%2520untracked%2520files%2520present%2520(use%2520%2522git%2520add%2522%2520to%2520track)%250A%2524%2520git%2520add%2520test%250A%2524%2520git%2520commit%2520-S%2520-m%2520%2522Adding%2520a%2520test%2520file%2520to%2520new_branch%2522%250A%255Bnew_branch%2520(root-commit)%25204265ec8%255D%2520Adding%2520a%2520test%2520file%2520to%2520new_branch%250A%25201%2520file%2520changed%252C%25201%2520insertion(%252B)%250A%2520create%2520mode%2520100644%2520test%250A%2524%2520git%2520push%2520-u%2520origin%2520new_branch%250AEnumerating%2520objects%253A%25203%252C%2520done.%250ACounting%2520objects%253A%2520100%2525%2520(3%252F3)%252C%2520done.%250AWriting%2520objects%253A%2520100%2525%2520(3%252F3)%252C%2520918%2520bytes%2520%257C%2520918.00%2520KiB%252Fs%252C%2520done.%250ATotal%25203%2520(delta%25200)%252C%2520reused%25200%2520(delta%25200)%250ARemote%253A%2520Create%2520a%2520pull%2520request%2520for%2520%25E2%2580%2598new_branch%25E2%2580%2599%2520on%2520GitHub%2520by%2520visiting%253A%250ARemote%253A%2520%2520%2520%255BUpstream%2520repo%2520link%2520%253A%2520original%2520repo%2520that%2520you%2520forked%2520from%255D%250ARemote%253A%250A%2520*%2520%255Bnew%2520branch%255D%2520%2520%2520%2520%2520%2520%2520%2520%2520new_branch%2520-%253E%2520new_branch"
  style="width: 727px; height: 644px; border:0; transform: scale(1); overflow:hidden;"
  sandbox="allow-scripts allow-same-origin">
</iframe>


Once you push the changes to your repo, the **Compare & pull request** button will appear in GitHub.
![GitHub's Compare & Pull Request button](https://i.stack.imgur.com/7yscx.png)

Click it and you'll be taken to this screen:

![](https://opensource.com/sites/default/files/uploads/open-a-pull-request_crop.png)

GitHub's Open pull request button
Open a pull request by clicking the Create pull request button. This allows the repo's maintainers to review your contribution. From here, they can merge it if it is good, or they may ask you to make some changes.

### In Short:
If you want to contribute to a project, the simplest way is to:

Find a project you want to contribute to

-> Fork it

-> Clone it to your local system

-> Make a new branch

-> Make your changes

-> Push it back to your repo

-> Click the **Compare & pull request button**

-> Click **Create pull request** to open a new pull request

If the reviewers ask for changes, repeat steps 5 and 6 to add more commits to your pull request.