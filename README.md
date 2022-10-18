<span id="title">

# Benchmark name

</span>

[![webots.cloud - Page](https://img.shields.io/badge/webots.cloud-Page-007ACC)](https://benchmark.webots.cloud/run?version=R2022b&url=https://github.com/Jean-Eudes-le-retour/bare-benchmark-example/blob/main/worlds/robot_programming.wbt&type=benchmark)

## Description

<span id="description">

Write here a short description of your benchmark.

Are script injection possible?
<script>alert("test")</script>

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

## Organizer setup

Here is a quick summary of the instructions for somebody who wants to organise a robotics simulation benchmark:

### GitHub settings
- [Create your own repository](../../generate) from this template

- In the [settings tab](../../settings), tick the "Template repository" box.

- You need to setup a secret to be able to fetch your competitors' controllers:
  - [Create a new Personal Access Token](../../../../settings/tokens/new). Give it a name to remember what it is for and set the "Expiration" to the duration of the tournament. You can always set it to "No expiration" or recreate a token when it expires. Tick the "repo" scope box, click "Generate token" and copy the generated code
  - Then go to the repo's [secrets settings](../../settings/secrets/actions/new) to create a new repository secret. Name it "REPO_TOKEN", paste in the Personal Access Token you just created and finally click the "Add secret" button.

### README update

Update [README](../../edit/main/README.md):

- Change the title and the description section to fit your new scenario
- Update the different fields of the information section that are also used on webots.cloud:
  - Difficulty: an idea of the benchmark's complexity (for example: Middle School, High School, Bachelor, Master, PhD...)
  - Robot: Name of the robot used in the benchmark
  - Language: the programming language of the example controller
  - Commitment: an idea of the time required to complete the benchmark (a few minutes, a couple of hours, a couple of days...)

- Replace "ORGANIZER_NAME" in the "How to paricipate" section with your GitHub username
- Remove the organizer setup section
- When everything is ready and you have submitted your benchmark to [webots.cloud](https://benchmark.webots.cloud/benchmark), change the badge link to the correct webots.cloud page

### Metadata update

- Update the fields inside [webots.yml](../../edit/main/webots.yml):
  - file: put the relative path to your world file
  - maximum-duration: the maximum duration of an evaluation. Set it not too big to avoid long evaluation of broken controllers.
  - metric: should be one of "percent", "time-speed", "time-duration" or "distance". It depends on how the perfomance is evaluated.
  - dockerCompose: it is a special path used by the integrated IDE and GitHub actions to locate the default controller. Change "edit_me" to the name of your main controller.
- Replace the files of the [preview folder](/preview) with an example animation of your benchmark (keep the same file names)

### Webots files

Replace/add all the files needed for your Webots simulation at the root of the repository, notably the folders "worlds", "controllers" and the folder "plugins" needed for the robot window.

<!-- <details>
<summary style="font-size:1.25em">Detailed step-by-step guide</summary>

TODO: Detailed step-by-step guide if needed

</details>
-->

---

## How to participate

### Create your own entry repository from the template

[Click here](../../generate) to create your own repository or do it manually by clicking on the green "Use this template" button.

Fill the "Repository name" field with a name for your controller.
Choose the visibility of your controller, keep it "Public" if you don't care about people looking at your controller code otherwise set it to "Private".
Finally, click on the green "Create repository from template".

### Add the organizer as collaborator if you set your repository as private

Go to your personal repository page (https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME) and go to the "Settings" tab.

Under "Access" click on the "Collaborators" section.
You will then need to confirm the access by re-entering your GitHub password.

When this is done you should see a "Manage access" box where you will see the current collaborators of the repo.
Click on the "Add people" and search for "ORGANIZER_NAME". When you found the organizer, add them to the repository.

### Submit your entry by using posting an issue using the provided template

After you added the organizer as a collaborator, go back to the main page of your repository and copy your full repository URL.

Come back to this page and [click here](../../issues/new?assignees=&labels=registration&template=registration_form.yml&title=Registration+to+benchmark) to start your registration. If it doesn't work, you can do it manually by going to the "Issues" tab, creating a new issue and choosing the "Registration to benchmark" template.

Paste your repository URL in the URL field and click the "Submit new issue" button.

A series of automated actions will take place. If everything went well, you should get a message saying that you are successfully registered to the benchmark.

### Modify the template controller and/or create your own one

Everything should be good to go, you can modify the files in the controllers folder.

The supervisor controller is a special controller that is used to evaluate your controller's performance.

Webots supports multiple programming languages, see the [Webots documentation](https://www.cyberbotics.com/doc/guide/language-setup) if you are interested.
Be sure to name your main controller like the default controller (except for the file extension) for it to be used in the leaderboard evaluation.
