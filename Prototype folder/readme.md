# Contribution Guidance

If you'd like to contribute to this repository, please read the following guidelines. Contributors are more than welcome to share their learnings with others in this centralized location.

## Code of Conduct

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information, see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Question or Problem?

Please do not open GitHub issues for general support questions as the GitHub list should be used for feature requests and bug reports. This way we can more easily track actual issues or bugs from the code and keep the general discussion separate from the actual code.

## Typos, Issues, Bugs and contributions

Whenever you are submitting any changes to the Microsoft Cloud repositories, please follow these recommendations.

* Always fork the repository to your own account before making your modifications
* Do not combine multiple changes to one pull request. For example, submit any tutorial and documentation updates using separate PRs
* If your pull request shows merge conflicts, make sure to update your local main to be a mirror of what's in the main repository before making your modifications
* If you are submitting multiple tutorials, please create a specific PR for each of them
* If you are submitting a typo or documentation fix, you can combine modifications to a single PR where suitable

## Contributing Steps

* [Step 1: Fork this Repository](#step-1-fork-this-repository)
* [Step 2: Setup your Work Environment](#step-2-setup-your-work-environment)
  * [Step 2.1: Install Git](#step-21-install-git)
  * [Step 2.2: Install VS Code](#step-22-install-vs-code)
  * [Step 2.3: Install VS Code Extensions](#step-23-install-vs-code-extensions)
* [Step 3: Clone the Repository Locally](#step-3-clone-the-repository-locally)
* [Step 4: Add your Tutorial](#step-4-add-your-tutorial)
  * [Step 4.1: Destructure your Tutorial](#step-41-destructure-your-tutorial)
  * [Step 4.2: Add Overview Exercise](#step-42-add-overview-exercise)
  * [Step 4.3: Add Tips, Notes, and Warnings](#step-43-add-tips-notes-and-warnings)
  * [Step 4.4: Add Congratulations Exercise](#step-44-add-congratulations-exercise)
  * [Step 4.5: Edit Your Tutorial .yml File](#step-45-edit-your-tutorial-yml-file)
  * [Step 4.6: Add Reference to Your Tutorial](#step-46-add-reference-to-your-tutorial)
* [Step 5: Push your Changes to GitHub](#step-5-push-your-changes-to-github)
* [Step 6: Create a Pull Request](#step-6-create-a-pull-request)

### Step 1: Fork this Repository

* Open the repository [main landing page](https://github.com/leestott/microsoft-cloud-pr).
* From the top-right corner select **Fork**.

(Learn more: [here](https://docs.github.com/en/get-started/quickstart/fork-a-repo#forking-a-repository))

### Step 2: Setup your Work Environment

#### Step 2.1: Install Git

* Go to [git-scm.com/downloads](https://git-scm.com/downloads)
* Download the suitable version of Git.
* Install it on your local machine.

Alternatively, you can use Codespaces.

#### Step 2.2: Install VS Code

* Go to [code.visualstudio.com](https://code.visualstudio.com)
* Download the suitable version of VS Code.
* Install it on your local machine.

Alternatively, you can use Codespaces.

#### Step 2.3: Install VS Code Extensions

Install Learn Authoring Pack:

* Go to [Learn Authoring Pack Extension](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)
* Select **Install**.
* For the first time you use the extension, you will be asked to choose your user type between Microsoft employee and Public contributor.
* Select **Public Contributor**.

This extension will help you validate what you write according to Microsoft Learn guidelines.

Install Read Time Extension:

* Go to [Read Time Extension](https://marketplace.visualstudio.com/items?itemName=johnpapa.read-time)
* Select **Install**.

This extension will help you estimate the time it takes to read your tutorial steps.

Install Code Spell Checker:

* Go to [Code Spell Checker Extension](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)
* Select **Install**.

This extension will help you make fewer typos as it will highlight mistyped words.

### Step 3: Clone the Repository Locally

> [!NOTE]
> Skip this step if you are using Codespaces.

* Open Git Bash locally.
* Run the following command to clone the forked [Microsoft Cloud GitHub Repository](https://github.com/YOUR-GITHUB-USERNAME/microsoft-cloud-pr) to your machine.

```bash
git clone https://github.com/YOUR-GITHUB-USERNAME/microsoft-cloud-pr
```

### Step 4: Add your Tutorial

> [!IMPORTANT]
> You are only going to work inside the *docs/dev/* folder
>
> **DO NOT MODIFY** any other folder

#### General Guidance

Regarding Text:

* Always follow the Learn Markdown extension guidelines.
* Always use the word Select instead of Choose or Click while guiding the user to perform tasks with UI elements.
* Any UI text being referred to should be **Bold**. (double asterisk on each side of the value)
* Any files, folders, etc. should use *filename.txt*. (single asterisk on each side of the value)
* Add a carriage return before and after images, lists, notes, warnings, and tips. (newline before and after them)
* Add alt text to describe the content of the image.
* Try to add direct links when possible.
* Always add relative links when possible (links that start with *learn.microsoft.com* for example, *learn.microsoft.com/azure* becomes */azure* without the domain name)

Regarding Images:

* Never use a full desktop screenshot instead try to zoom in on the object of interest.
* Use overlay boxes to highlight the area of interest in each image.

#### Step 4.1: Destructure your Tutorial

* Create a folder for your repository inside *docs/dev/tutorials/*.
* Name the folder with a descriptive short lowercase name separated by a dash. (ex. *openai-acs-msgraph/* represents **OpenAI - Azure Communication Service - Microsoft Graph** tutorial)
* Create a *YOUR-TUTORIAL-NAME.yml* file inside *docs/dev/tutorials/*. (ex. *openai-acs-msgraph.yml* the same name as your tutorial folder name)
* Create *includes/* folder and *media/* folder inside your tutorial folder.

Complete folder structure:

```markdown
└── docs
    └── dev
        └── tutorials
            ├── YOUR-TUTORIAL-NAME.yml
            └── YOUR-TUTORIAL-NAME
                ├── includes
                └── media
```

Regarding *includes/* folder:

* All the steps should be inside the *docs/dev/tutorials/YOUR-TUTORIAL-NAME/includes/* folder.
* All the steps should be saved in a markdown file. (uses .md file extension)
* All the markdown files' names should start with a two-digit number. (00 followed by 01 and so on)
* The first file of the tutorial should be named *00-Overview.md*.
* The last file of the tutorial should be named *0X-Congratulations.md* where x denotes a number.
* Add this line to the beginning of each exercise file `<!-- markdownlint-disable MD041 -->` to disable unnecessary warnings.
* After adding the exercises, right-click on the includes folder name and select **Validate this folder** to reveal problems that your tutorial has and needs to be fixed.

Complete folder structure:

```markdown
└── docs
    └── dev
        └── tutorials
            ├── YOUR-TUTORIAL-NAME.yml
            └── YOUR-TUTORIAL-NAME
                ├── media
                └── includes
                    ├── 00-Overview.md
                    ├── 01-Exercise.md
                    ├── ...
                    └── 06-Congratulations.md
```

Regarding *media/* Folder:

* All the images should be inside the *docs/dev/tutorials/YOUR-TUTORIAL-NAME/media/* folder.
* Make sure to add descriptive names for each image file.
* After adding your image right-click on the image name and select from the pop-up menu **Compress image**. (Alternatively, right-click on the folder and select **Compress all images in folder**)

Complete folder structure:

```markdown
└── docs
    └── dev
        └── tutorials
            ├── YOUR-TUTORIAL-NAME.yml
            └── YOUR-TUTORIAL-NAME
                ├── includes
                └── media
                    ├── descriptive-image-name.png
                    ├── another-descriptive-name.png
                    ├── ...
                    └── another-descriptive-name.png
```

#### Step 4.2: Add Overview Exercise

This is the first exercise in any tutorial. (Example: [here](https://github.com/leestott/microsoft-cloud-pr/blob/main/docs/dev/tutorials/openai-acs-msgraph/includes/00-Overview.md))

* Add the level of your tutorial at the beginning of the file.
* Start with a small paragraph to give the reader a high-level overview of your tutorial.
* Give a brief introduction about each Microsoft Cloud service used in your tutorial.
* Add an image that includes your full solution architecture.
* Add prerequisites that need to be installed or done before starting the tutorial.
* Add Microsoft Cloud Technologies used in this Tutorial section.

After that, you can continue by adding the other exercises of your tutorial one by one following the mentioned guidelines. (Example: [here](https://github.com/leestott/microsoft-cloud-pr/blob/main/docs/dev/tutorials/openai-acs-msgraph/includes/02-OpenAI-Create-Resource.md))

#### Step 4.3: Add Tips, Notes, and Warnings

Whenever possible add tips, notes, and warnings to facilitate the learning experience.

Example Tip:

> [!TIP]
> If you're using Visual Studio Code, you can open files directly by selecting:
>
>* Windows/Linux: Ctrl + P
>* Mac: Cmd + P
>
> Then type the name of the file you want to open.

Example Note:

> [!NOTE]
> The goal of this exercise is to show what's possible with natural language to SQL functionality and demonstrate how to get started using it. As mentioned earlier, it's important to discuss if this type of AI is appropriate for your organization before proceeding with any implementation. It's also **imperative to plan for proper prompt rules and database security measures** to prevent unauthorized access and protect sensitive data.

Example Warning:

> [!WARNING]
> Selecting a large **Virtual machine** will incur more charges and increasing the number of instances from the selected machine will also contribute to that.
> This may increase the speed and/or availability of your model but at the cost of paying more money.

#### Step 4.4: Add Congratulations Exercise

This is the last exercise in any tutorial. (Example: [here](https://github.com/leestott/microsoft-cloud-pr/blob/main/docs/dev/tutorials/openai-acs-msgraph/includes/20-Congratulations.md))

* Start by Congratulating the reader for finishing the tutorial.
* Add a paragraph to recap everything that has been done in this tutorial.
* Add clean-up instructions for each resource that has been created.
* Add the next steps section which includes documentation, and training on Microsoft Learn.

#### Step 4.5: Edit Your Tutorial *.yml* File

You need to edit the following:

* title: This is the title that will be used for your tutorial.
* metadata:
  * title: This is the title that will be used for your tutorial.
  * description: This is a summary of the content included in your tutorial.
  * level: This is the difficulty level of this tutorial. (can be one of the following: Beginner, Intermediate, Advanced)
  * author: This is the GitHub username of the tutorial author. (your GitHub username)
  * ms.service: This is the Microsoft cloud service the content is most closely associated with.
* items
  * title: This is the title of the tutorial's exercise.
  * durationInMinutes: This is the time in minutes it takes to finish a specific exercise.
  * content: This is the relative link to your tutorial *include/* folder exercises.

Example *.yml* file [here](https://github.com/leestott/microsoft-cloud-pr/blob/main/docs/dev/tutorials/openai-acs-msgraph.yml):

```yml
### YamlMime:Tutorial
title: YOUR TUTORIAL TITLE
metadata:
  title: YOUR TUTORIAL TITLE
  description: YOUR TUTORIAL DESCRIPTION
  audience: Developer
  level: YOUR TUTORIAL LEVEL
  displayType: one-column
  ms.date: 09/10/2023
  author: YOUR-GITHUB-USERNAME 
  ms.author: dwahlin 
  ms.topic: tutorial
  ms.custom: scenarios:microsoft-cloud
  ms.service: MICROSOFT SERVICES USED IN YOUR TUTORIAL

items:
  - title: |
      Overview
    durationInMinutes: 2
    content: |
      [!INCLUDE [](YOUR-TUTORIAL-NAME/includes/00-Overview.md)]

  - title: |
      EXERCISE TITLE
    durationInMinutes: 10
    content: |
      [!INCLUDE [](YOUR-TUTORIAL-NAME/includes/01-Exercise.md)]

  - title: |
      Congratulations!
    durationInMinutes: 2
    content: |
      [!INCLUDE [](YOUR-TUTORIAL-NAME/includes/06-Congratulations.md)]
```

#### Step 4.6: Add Reference to Your Tutorial

Once you finish adding your tutorial you need to edit the following two files:

* *docs/dev/index.yml*
* *docs/dev/TOC.yml*

For *docs/dev/index.yml*:

> [!NOTE]
>There are two categories **Azure and Microsoft 365 Tutorials** and **Azure and Power Platform Tutorials**.
>
Add your tutorial under the appropriate category.

> Add text and url to the end of the tutorials links.
>
> Example:
>
> ```yml
>  - text: Deploying a Large Language Model (GPT-2) on Azure Using Power Automate 
>    url: /microsoft-cloud/dev/tutorials/aml-powerapps-powerautomate 
> ```

For *docs/dev/TOC.yml*:

> Add name, and href at the end of the Tutorials items.
>
> Example:
>
> ```yml
>  - name: Deploying a Large Language Model (GPT-2) on Azure Using Power Automate 
>    href: /microsoft-cloud/dev/tutorials/aml-powerapps-powerautomate 
> ```

Notes:

* Be careful with the spaces don't add extra spaces or empty spaces at the end of lines.
* Make sure to match the above-given examples.
* Your url or href should start with */microsoft-cloud/dev/tutorials/YOUR-TUTORIAL-NAME*

### Step 5: Push your Changes to GitHub

Inside Git Bash:

* Run the following commands when you're ready to submit your changes, stage and commit your changes. (Learn more: [here](https://docs.github.com/get-started/quickstart/contributing-to-projects#making-and-pushing-changes))

    ```bash
    git add .
    git commit -m "a short description of the change"
    ```

* Run the following command to send the changes from your local machine to the online GitHub repository fork you created.

    ```bash
    git push
    ```

### Step 6: Create a Pull Request

* Open the forked GitHub repository [github.com/YOUR-GITHUB-USERNAME/microsoft-cloud-pr](https://github.com/YOUR_GITHUB_USERENAME/microsoft-cloud-pr).
* Select **Sync fork** to get the latest changes from the original repository.
* Select **Contribute** to add your changes to the original repository.
* Select Open pull request to create a new pull request. (Learn more: [here](https://docs.github.com/get-started/quickstart/contributing-to-projects#making-a-pull-request))
* Add a title for your tutorial pull request.
* Fill in the pull request template with the needed information about your tutorial.
* Select **Create pull request** to submit everything for review.

Congratulations! You can wait for now and we will get back to you as soon as possible with feedback about your tutorial.
