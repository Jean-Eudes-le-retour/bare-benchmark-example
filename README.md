<span id="title">

# Benchmark organizer template

</span>

[![webots.cloud - Benchmark](https://img.shields.io/badge/webots.cloud-Benchmark-007ACC)](https://benchmark.webots.cloud/run?version=R2022b&url=https://github.com/Jean-Eudes-le-retour/bare-benchmark-example/blob/main/worlds/robot_programming.wbt&type=benchmark)

### Benchmark examples

- https://github.com/cyberbotics/robot-programming-benchmark-disabled 
- https://github.com/cyberbotics/inverted-pendulum-benchmark-disabled 

## Organizer setup

Here is a quick summary of the instructions for somebody who wants to organize a robotics simulation benchmark. The links in the rest of the setup are relative to the repository where the README is, so to be able to use them you should first [create your own repository](../../generate) from this template and go to its main page to continue reading the instructions.

You will then need to follow those steps:

### GitHub settings
1. Go to the ![Settings tab](../../settings):
   1. Under the General section, tick the "Template repository" box so that the competitors can easily make a copy of the simulation files
   1. Go to ![Actions settings tab](../../settings/actions) and make sure that the "Allow all actions and reusable workflow" permission is activated. This allows the different automation scripts to do their job. If it is not the case, set it correctly and save the setting
1. You will need to setup a GitHub secret to be able to fetch your competitors' controllers:
   1. ![Create a new Personal Access Token](../../../../settings/tokens/new). Give it a name to remember what it is for and set its "Expiration" to the end of the tournament. You can always set it to "No expiration" or recreate a token when it expires to allow the automated scripts to continue working. Tick the "repo" scope box, click "Generate token" and copy the generated code to your clipboard
   1. Go to the repo's ![secrets settings](../../settings/secrets/actions/new) to create a new repository secret. Name it "REPO_TOKEN", paste in the Personal Access Token you just created and finally click the "Add secret" button
1. You will also need to add three custom labels for the automation scripts: "registration", "pending" and "accepted"
   1. Go to the ![Generate new labels action](../../actions/workflows/generate_labels.yml) page under the Actions tab. Click on "Run workflow" to create automatically the needed labels

### Webots files

Replace/add all the files needed for your Webots simulation at the root of the repository, notably the folders "worlds", "controllers" and the folder "plugins" needed for the robot window. ![Click here](../../upload/main) to upload the new files from the web interface if it is more convenient for you. Note that on webots.cloud, the list title of the benchmark and its hover description are defined by the Webots world file: more specifically, the WorldInfo node has a "title" and an "info" field which are read at the submission of the site.

### Benchmark specific files
1. Update the fields inside ![webots.yml](../../edit/main/webots.yml):
   1. file: put the relative path to your world file
   1. maximum-duration: the maximum duration of an evaluation in seconds. Set it not large to avoid long evaluations of broken controllers but not too short to have enough time to finish the task
   1. metric: should be one of "percent", "time-speed", "time-duration" or "distance". It depends on how the performance is evaluated
   1. dockerCompose: it is a special path used by the integrated IDE and GitHub actions to locate the default controller. Change "edit_me" to the name of your main controller
   1. Don't forget to commit your changes to save them
1. Replace the three files of the ![preview folder](/preview) with an example animation of your benchmark [recorded from Webots](https://cyberbotics.com/doc/guide/web-animation). Keep the same names for the files: animation.json, scene.x3d and thumbnail.jpg. ![Click here](../../upload/main/preview) to upload the new files from the web interface if that is more convenient for you. 

### README update

Some sections from the README file are used to generate the webots.cloud benchmark page: the title, the description and an information table. Make sure to edit them while keeping them inside their respective \<span\> tags.

Update the ![README file](../../edit/main/README.md):
1. Change the title and the description section to fit your new scenario.
1. Update the different fields of the information section
   1. Difficulty: an idea of the benchmark's complexity (for example: Middle School, High School, Bachelor, Master, PhD...)
   1. Robot: the name of the robot used in the benchmark
   1. Language: the programming language of the example controller
   1. Commitment: an idea of the time required to complete the benchmark (a few minutes, a couple of hours, a couple of days...)
1. Replace the two occurrences of "ORGANIZER_NAME" in the "How to participate" section with your GitHub username and one "ORGANIZER_REPOSITORY" with your repository name
1. Don't forget to commit your changes to save them

You can submit your benchmark to [webots.cloud](https://benchmark.webots.cloud/benchmark) to share it with other people. Then you are on the website on the "Benchmark" tab, click on "Add a new benchmark" and enter the URL to your .wbt world file located in the ![worlds folder](./worlds/)
1. When you have submitted your benchmark to webots.cloud, change the link of the shield badge at the top of the ![README file](../../edit/main/README.md) to the correct webots.cloud page. You will then be able to easily go to the webots.cloud site to see your updated changes and your competitors will have a handy link to the current leaderboard

Finally, when all the previous steps have been made, you can remove this "Organizer setup" section from the README file and your benchmark should be good to go!

---

## Description

<span id="description">

Write here a short description of your benchmark.

</span>

<img src="./preview/thumbnail.jpg" width="75%">

## Information

<span id="information">

- Difficulty: Middle School, High School, Bachelor, Master or PhD
- Robot: robot name
- Language: programming language of controller template
- Commitment: amount of time needed to program controller

</span>

---

## How to participate

### Create your own entry repository from the template
1. [Click here](../../generate) to create your own repository or do it manually by clicking on the green "Use this template" button.
1. Fill the "Repository name" field with a name for your controller.
Choose the visibility of your controller, keep it "Public" if you don't care about people looking at your controller code otherwise set it to "Private".
Finally, click on the green "Create repository from template".

You should now be on your own repository page. The URL should look like this: "https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME".  If it is not the case, go to your repositories and click on the first one from the list.

#### If you set your repository as private, add the organizer as collaborator:
1. ![Click here](../../settings/access) to go to the "Collaborators" setting page
   1. You might need to confirm the access by re-entering your GitHub password.
1. You should see a "Manage access" box where you will see the current collaborators of the repo.
Click on the "Add people" and search for "ORGANIZER_NAME". When you found the organizer, add them to the repository.

### Register yourself by using posting an issue
1. Go back to the main page of your repository if that is not the case and copy the repository URL from the address bar to your clipboard.
1. ![Click here](https://github.com/ORGANIZER_NAME/ORGANIZER_REPOSITORY/issues/new?assignees=&labels=registration&template=registration_form.yml&title=Registration+to+benchmark) to go to the organizer repository and start your registration. If it doesn't work, you can do it manually by going to the organizer's repository, then to the "Issues" tab, creating a new issue and choosing "Registration to benchmark".
1. Paste your repository URL in the URL field and click the "Submit new issue" button.

A series of automated actions will take place in a few seconds. If everything went well, you should get a message saying that you are successfully registered to the benchmark. If there was a problem, read the feedback message to fix what went wrong. When you finished fixing your repository, you can post a "retry" comment on the registration issue to re-run the automated verifications.

### Modify the template controller and/or create your own one

Everything should be good to go, you can modify the main controller files in the controllers folder.

The supervisor controller is the special controller that is used to evaluate your controller's performance.

Webots supports multiple programming languages, see the [Webots documentation](https://www.cyberbotics.com/doc/guide/language-setup) if you are interested.
Be sure to name your main controller like the default controller (except for the file extension) for it to be used in the leaderboard evaluation.
