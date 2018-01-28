# Instructions for the Markdown and GitHub Workshop

The Markdown and GitHub workshop was held on 26 January 2018. Participants are invited to get to know GitHub by using these sandbox repository, which will remain available until the end of February 2018.

## Workshop Resources

The Workshop Home Page is [https://whatevery1says.github.io/workshops/markdown-and-github/index.html](https://whatevery1says.github.io/workshops/markdown-and-github/index.html). This contains links to useful GitHub and Markdown tools, a recording of the workshop, and the sandbox repository, as well as the workshop slideshow.

## Exercises

The slideshow contains a couple of exercises to help you to get familiar with GitHub. The instructions are duplicated here so that you can try out anything we were unable to cover during the live workshop.

### Setting Up the GitHub Desktop Client

1. Launch the [GitHub Desktop Client](https://desktop.github.com/).
2. In Windows, `Select File > Options > Accounts`. On the Mac, this is under `GitHub Desktop > Preferences`.
3. Click the `Git` tab and enter the username and email you used for your GitHub account.
4. Click the `Advanced` tab and select VS Code as your external editor.
5. Create a folder called GitHub inside your Documents folder. In Windows, this will have the local path `C:\Users\YourName\Documents\GitHub`. On the Mac it will be `~/Documents/GitHub/`.

For fuller instructions, I recommend the Programming Historian tutorial [An Introduction to Version Control Using GitHub Desktop](https://programminghistorian.org/lessons/getting-started-with-github-desktop).

### Cloning a Repo

There are two easy ways to clone a repo.

1. Alternatively, copy the URL shown there. In the GitHub Desktop client, select `File > Clone repository > URL`. Enter the URL and the local path to your GitHub folder. Try this with the URL for the workshop sandbox repo: https://github.com/whatevery1says/workshop-sandbox.
2. With the GitHub Desktop Client open, click the repo’s `Clone or download` button on the GitHub website and select `Open in Desktop`.

I recommend starting out with the first method.

### Committing and Pushing Changes

1. In your `GitHub/workshop-sandbox` folder, find the file `my_name.md`. Open it in VS Code.
2. Make the changes to the file indicated and save the file as `your_name.md`.
3. Open the GitHub Desktop Client. It should show that you have a new file in the `Changes` tab. In the `Summary` section, type a message like “Added your_name.md.” Click `Commit to Master`.
4. Click the `Push Origin` tab at the top of the screen. Your file will be pushed to the remote repo. Note that you will get an error if you do not have permissions to push to the sandbox repo. If you require access, please contact scott.kleinman@csun.edu.
5. Refresh the repo's webpage on GitHub, and your file should appear.

### Committing and Pushing Changes

When you click `Commit to Master`, your new file is staged for sending to to the remote repository. You can stage multiple files in a single commit.

In the exercise above, you are adding a new file to the repo, but you can also make changes to the file locally, commit it, and then push the changes to the repo. None of the changes enter your **local** repository's history until you commit them. None of the changes enter the **remote** repository's history until you push them.

If multiple contributors are likely to be editing the same files, there is a chance that conflicts will arise. In most cases, `git` is able to "magically" merge competing versions of files. But not all cases. If merging fails, you will get a merge conflict error.

One way to prevent this is to make sure that you **always pull the latest content from the remove repository** before you commit any changes. In the GitHub Desktop Client, do this by clicking the `Pull Origin` tab at the top of the screen.

This is not a guarantee that merge conflicts will be avoided. When you encounter a merge conflict, you need to open the file and fix the problem manually. VS Code makes this process very simple, so we will look at using GitHub with VS Code next before providing an exercise in resolving merge conflicts.

### GitHub and VS Code

VS Code allows you to connect to GitHub and other similar services, so it uses the generic term "source control". To open the Source Control Manager, click `View > SCM`. You can also click the branching (forking) icon in the taskbar or type `Ctrl + Shift + G` (`Command + Shift + G` on the Mac).

If you have open a file in a local GitHub repo, the VS Code Source Control Manager will show a file hierarchy for each file you have open in one of your local repos. Changed files are marked with an “M” (modified). Mouse over the file name and click the Plus icon to stage them for a commit. When all files are staged, type a commit message and click the Check icon. Click the Three Dots icon to see all options, one of which will be `Push`. You can also pull the latest code from this menu.

### Resolving Merge Conflicts

Use the procedure below to create an artificial merge conflict.

1. Make sure that you have a local clone of the `workshop-sandbox` repo. In your web browser, go to the file [resolving_merge_conflicts.md](https://github.com/whatevery1says/workshop-sandbox/blob/master/resolving_merge_conflicts.md) in the workshop-sandbox repo website. Edit this file online by clicking the pencil icon. Change the phrase "This is the original file" at the bottom of this document to "This file was modified online".
2. Add a commit message at the top of the file and click the "Commit changes" button. Your commit will be pushed to the repo automatically by the GitHub website.
3. In VS Code open the `resolving_merge_conflicts.md` file **without pulling from the repo** first. Change "This is the original file" to "This file was locally" and save the file.
4. Open the GitHub Desktop Client. Commit your change and try to pull the code by clicking "Pull Origin". You should get an error that says there is a conflict.

To resolve the conflict follow the procedure below:

1. When you get the error message, VS Code will probably open the file automatically. If it doesn't, use VS Code to open the file in your local repository.
2. You will see that `git` will have injected markers around the merge conflict in the fil. VS Code will give you various options for resolving the conflict between the `HEAD` of your local repository and the remote version. You can choose one of these or manually edit out the code you don't want and the markers injected by `git`.
3. Save the file, re-commit it, and push the file again.
