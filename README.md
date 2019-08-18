# bioboot-demo-2019
Live demo material for Biocomputing Bootcamp in 2019

> Side-Note: This README.md file was written as a Markdown format text file. These are often used for documentation purposes as they allow easy text formatting and are rendered nicely by both GitHub and Bitbucket. To learn more about markdown on your own time visit [markdown-basics](https://help.github.com/en/articles/basic-writing-and-formatting-syntax) and optionally [mastering-markdown](https://guides.github.com/features/mastering-markdown).

### Directions
For this second _hands-on_ GitHub demo please complete the steps in each of the sections below and remember to feel free to talk to your neighbors and ask questions as you go: 

## Collaborating on GitHub
There are two basic models for collaborating on GitHub. These are known as the **Shared repository model** and the **Fork & pull model** (often just referred to as **Pull requests**).


1. The **shared repository model** is more prevalent with small teams and organizations collaborating on private projects. Everyone is granted **push** access to a single shared repository and different branches are primarily used to isolate major changes whilst small changes typically get pushed directly to the default **master** branch as you have already done in **demo1**.


2. The **fork & pull model** lets anyone fork an existing repository and push changes to their personal fork without requiring access be granted to the source repository. The changes must then be pulled into the source repository by the project maintainer. This model reduces the amount of friction for new contributors and is very popular with open source projects because it allows people to work independently without upfront coordination.


You already have a cone of this repo on your local machine from step one above that you can modify locally and also use `git pull origin master` to sync with any subsequent changes in the original GitHub repo. **However, you don't have permissions to actually `push` your changes to this original GitHub repo**. Go ahead and try if you like… 

> Side-Note: If you were added as a 'collaborator' on the repo then you would be able to **git push origin master**, in the same way you did for your own repo in demo1, and contribute your changes directly. This is simply the **shared repository model** and you can create your own by adding 'collaborators' to your own GitHub repos under the *Settings* link. For now we focus on the more complicated but common **fork and pull** approach. 

Below we will explore the **fork & pull** approach as it can be used with any public repo on GitHub.

## Try Shared Repository Model

- Now partner with the person next to you. 
  - If your table has an odd number of people, three people can team up
  as one.
- Determine who will be the **owner** of the repository. Only one
  person per team can be the owner, and each team will be working with
  only **one repo**.

#### If you are owner of this **one repo**
- Create a GitHub repo, for example, **bioboot-share-2019**, with your
  GitHub account. 
  - Make sure to create a README file so that the repo is not empty.
  - If you want, feel free to make a simple change, such as editing
    README or adding another file.
- Add the other person as a collaborator to your GitHub repo.
  - Ask for the **username** of the person you're adding as a collaborator. 
  - On GitHub, navigate to the main page of the repository.
  - In the repository's right sidebar, click  **Settings** (it looks like a little gear icon)
  - Click the "**Collaborators**" tab.
  - Start typing the collaborator's username.
  - Select the user from the drop-down menu.
  - Click **Add**.
- Wait for your collaborator to make changes

#### If you are the collaborator to this repo
- Accept invitation as collaborator by checking your email and
  responding to the invitation.
- Visit the owner's github repo
  (e.g. https://github.com/OWNER-USERNAME/bioboot-share-2019), and
  make changes in the README or other file(s).
- Clone your partners repo by getting the URL from your partners GitHub page (`git clone <URL>`).
- Modify some of the files (for example add some content to the **ToDo.md** file)
- Go through the regular git add/git commit cycle.
- Commit and push these changes to GitHub with `git commit` and `git push`

Congratulations! you have now contributed to a shared collaborative repo! 

### Working together, fixing conflicts

- Now together with your partner pick a common line and edit it in different ways so you will have two distinct versions.
- First `git pull origin master` to sync with remote repo.
- Then `add/commit/push` your changes to GitHub.
- What happened?

Can you fix your first **conflict**?
See [Github
Help](https://help.github.com/en/articles/resolving-a-merge-conflict-using-the-command-line)
to fix the conflict. 


## 3. Fork and pull

To get your changes incorporated into someone else's repo that you are not an official *collaborator* on requires us to first **fork** the original repo, then **clone** it to your local computer, make and commit your changes and finally submit something called a **pull request**.

Like many things in the computing world this sounds more complicated than it really is so lets start by **forking** this repo - All this does is create a completely separate copy of the repo under **YOUR** GitHub account.

- To do this click the **Fork** button towards the very top right of THIS original GitHub repo 
![img1](https://help.github.com/assets/images/help/repository/fork_button.jpg)

- Now after a short time you should be taken to a new webpage displaying your OWN fork (i.e. your personal copy) of the repo under your GitHub account.

- Examine this forked repo. It should look excately the same as the origional but with the subtle "forked from hyunminkang/bioboot-demo-2019" note under the title.

- We will now clone this forked repo to your local computer by using the link provided from clicking the somewhat obscure **copy icon** (see image below for an example of the clipboard like icon GitHub like to use).

![im2](https://help.github.com/assets/images/help/repository/clone-repo-clone-url-button.png)

-  When cloning on your computer this time we will add a different destination name of **"myForkedCopy"** after the https address so as to help avoid potential confusion with the repo from step one above. For example:  

```
    git clone https://github.com/YOUR-USERNAME/bioboot-demo-2019.git
```

- Now, you have a local clone of the forked repo on your computer in a new directory named **myForkedCopy**.

- Lets cd into this directory and edit the file **JustOneThing.md** with nano or other means to add your name and a comment (see below). 

```
    cd bioboot-demo-2019
    # echo “**Hyun Min Kang**:  Git and GitHub has a step learning curve” >> JustOneThing.md
```

For example, add **YOUR first and last name** in bold (i.e. surrounded by
two starts on either side), instead of _Hyun Min Kang_ and one thing that was not completely clear from todays class thus far (e.g. "staging area", "remote repos" or "where is the coffee?").


- Once you have edited your file in nano go through the regular **git add/commit/push** steps, e.g.

```
    git add JustOneThing.md
    git commit -m “Edit in my fork of JustOneThing.md"
    git push origin master
```

- Check that your changes are online in YOUR GitHub forked copy.

- Do a final check that your repo is uptodate with the origional repo from which you forked by doing a regular git pull but directed to the origional repo.

```
    # First set the original repo as a remote with the name "upstream" 
    git remote add upstream https://github.com/hyunminkang/bioboot-demo-2019.git

    # List the location/address of your remotes
    git remote -v
    git pull upstream master
```    

- Now on YOUR GitHub forked copy click the little green **Compare, Review and create pull request** button toward the top left of the page. This looks a bit like a small icon that has the two little curved white arrows (see below).

![pull request button](https://help.github.com/assets/images/help/pull_requests/pull-request-start-review-button.png)

- On the subsequent **Comparing changes** page you may need to select the **base fork** as `hyunminkang/bioboot-demo-2019` (this is the original repo) and the **head fork** as your **YourUserName/bioboot-demo-2019** (YOUR forked repo with your committed change). 

![merge across forks](https://raw.githubusercontent.com/bioboot/demo2-github/master/pullrequest.png)  

- Typically, however you will not need to change settings and will see a note saying that **These branches can be automatically merged**. 

Click the large **Create pull request** button (see below)

![create pull request button](https://help.github.com/assets/images/help/pull_requests/pull-request-click-to-create.png)

- Add a note describing your changes such as “Eva's name and sentence changes from fork” and click the final **Create pull request** button to submit your changes for review to the original repo.

![Final create pull request button](https://help.github.com/assets/images/help/pull_requests/pullrequest-send.png)


Thats it, you can leave this page as your changes have been sent to the original package maintainers (basically everyone who has push access to the original repo). 

At this stage please put your hand up or use the GREEN POST-IT NOTE from the first day to let me know that you have done this so I can demo merging your pull request on the projector for the class.

#### Congratulations

Congratulations! You have just contributed to this open source project ;)
