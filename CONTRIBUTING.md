# Contribution Guidelines
We welcome your contributions! We aim to make the process of contributing to this project as easy and transparent as possible. Here are the ways you can contribute:

- Reporting bugs  
- Discussing code quality  
- Submitting fixes  
- Proposing new features  

## We Develop with GitHub  
We host our code, manage issues and feature requests, and accept pull requests through GitHub.  

## Documentation Writing and Management Guidelines  

### Documentation Tools  
Most design documents use Markdown (*.md) format. Below is a list of tools used to write Markdown documents.  
| Tool               | Purpose                                  | Notes                   |  
| ------------------ | ---------------------------------------- | ----------------------- |  
| Visual Studio Code | Markdown, PlantUML editing, and PDF build |                         |  
| PlantUML           | Writing UML diagrams                     |                         |  
| yEd                | Creating various diagrams including UML  |                         |  

### Diagram Creation Methods  

**- Using PlantUML**  
There are two ways to insert PlantUML diagrams within Markdown:  
1. Create UML in a separate file (*.puml), export it as an image, and import the image into Markdown.  
2. Write the code directly within Markdown.  


**- Using yEd**  
yEd allows you to create diagrams by editing shapes and lines with a mouse, similar to PowerPoint, while PlantUML requires coding to create diagrams. Diagrams created with yEd can be exported in various image formats such as SVG, PNG, or JPG to be inserted into Markdown documents.  

### Document Structure  

The repository contains documentation as .md files corresponding to each directory in the `docs` folder, structured as follows:


```
XXXX.md
 - /graphml - .graphml files created with yEd  
 - /images - Images converted from diagrams created with yEd and PlantUML, such as PNG and SVG files  
 - /plantuml - .puml files created with PlantUML  

```
* Images inserted into the md files are exported with the same file names to manage the history of the files created with graphml and plantuml.  
This means that one image corresponds to one graphml or plantuml file.  

### Document Modification Example  

If changes occur in the `Software Architecture.md of docs/architecture`:  
 1. Write the content for 4.8 Notification Service  
 2. Add the yEd diagram for Notification Service (graphml/308.component_notification_service.graphml)  
 3. Export the .graphml to SVG and add it (images/308.component_notification_service.svg)  
 4. Write the corresponding content in the md file and insert the image

```
### 4.8. Notification Service  
Write a description of the notification service // Write content  
![](images/308.component_notification_service.svg) // Insert image  
```
<br>

## We Use Gitflow, So Code Development Follows a Structured Process
We manage development using [Gitflow](https://nvie.com/posts/a-successful-git-branching-model/). All code changes are integrated through pull requests, and we follow a development workflow using various branches like `develop`, `feature`, and `release`. Here’s how to contribute:

1. **Fork** the `develop` branch of the remote repository into your account.
2. **Develop features** and ensure the code has been tested.
3. If necessary, **update the documentation** to reflect the changes.
4. Ensure all tests pass, and the code adheres to our coding style and linting rules.
5. Once work is complete, submit a **pull request** to the `develop` branch.
6. When creating a pull request, designate appropriate **reviewers** to review the code changes.  
   It’s advisable to choose reviewers who are familiar with the codebase and to consider their availability for providing feedback.
7. Also, assign **assignees** to clarify responsibility for the work.  
   **All maintainers of the repository** should be assigned as **assignees** on the pull request to ensure accountability for the changes and to facilitate a smooth review process.

> **Note**: Assignees are responsible for ensuring that the pull request is reviewed and merged appropriately. Designating all maintainers as assignees is an important step to ensure they are aware of the changes and can respond quickly.

## Reporting Bugs Using GitHub Issues
We track bugs using GitHub issues. You can easily report bugs by [opening a new issue](issues).

### Writing a Good Bug Report
A **good bug report** should include the following:
- A brief summary or background explanation of the issue.
- Steps to reproduce the bug (detailed and specific).
- The expected outcome and the actual result.
- Any additional information or notes that might help identify the problem.

## Contributor License Agreement (CLA)
Before accepting a pull request, you must submit a CLA once. The full CLA can be found here: [Contributor License Agreement](CLA.md).

## Coding Style
Our coding style follows the [OpenDID Coding Style](https://github.com/OmniOneID/did-doc-architecture/blob/main/docs/rules/coding_style.md). Adhering to it ensures that the code is consistent, easy to read, and maintainable.

## Commit Message Guidelines
Our commit messages follow the [OpenDID Commit Rules](https://github.com/OmniOneID/did-doc-architecture/blob/main/docs/rules/git_code_commit_rule.md). Clear commit messages help convey the intent of the changes and make the code history easier to navigate.

