# TortoiseGit integration for Embedded Workbench users
[TortoiseGit](https://tortoisegit.org/) is a free open-source client for the Git version control system. That is, TortoiseGit manages files over time. Files are stored in a local repository. The repository is much like an ordinary file server, except that it remembers every change ever made to your files and directories. This allows you to recover older versions of your files and examine the history of how and when your data changed, and who changed it. This is why many people think of Git and version control systems in general as a sort of “time machine”.

Some version control systems are also software configuration management (SCM) systems. These systems are specifically tailored to manage trees of source code, and have many features that are specific to software development - such as natively understanding programming languages, or supplying tools for building software. Git, however, is not one of these systems; it is a general system that can be used to manage any collection of files, including source code.

Git is an open source, distributed version control system designed to handle everything from small to very large projects with speed and efficiency. Every Git clone is a full-fledged repository with complete history and full revision tracking capabilities, not dependent on network access or a central server. Branching and merging are fast and easy to do.

This article introduces how to use TortoiseGit with EWARM.

## Typical project development workflow with Git
A git server contains the project repository which, in the Git jargon, is referred as _origin_. Each developer make a local copy by __cloning__ the _origin_ to his PC and starts to perform incremental changes to the source code. Each change must be __commited__ to the local repository. After the developer is finished with the modifications, he __pushes__ the code back to the _origin_.

If you need a general introduction to version control with Git, then we recommend two videos on YouTube: Tech Talk: [Linus Torvalds on git](https://www.youtube.com/watch?v=4XpnKHJAok8) (about design and differences to other VCS) and Tech Talk: Git (more technical). You can also read [Pro Git book](https://git-scm.com/book) (multiple translations as well as downloadable versions available) , the section called “[Git User Manual](https://tortoisegit.org/docs/tortoisegit/apg.html#git_user-manual)”, or the section called “Git Tutorial” which are a short introductions to the Git revision control system, explain the different approaches to version control, and how Git works (with a bunch of examples).

<!-- ![Typical program development flow with Git](https://user-images.githubusercontent.com/54443595/177169038-5a1fc4d2-b788-4d0c-a28f-9730f453066b.png) -->
![git-flow](https://user-images.githubusercontent.com/54443595/177284653-d40e643d-34e9-4258-be67-a452c0b3284c.svg)


## Setup
- Install [TortoiseGit](https://tortoisegit.org/) and setup your __user.name__ and __user.email__ following the TortoiseGit wizard instructions.
- Before launching the Embedded Workbench, deploy [`<install_dir>\common\config\tortoisegit.toolitems`](common/config/tortoisegit.toolitems).
- Launch the Embedded Workbench.


## Examples

### Starting from a local repository
For this example, let's create a project from scratch and make into a git repository within the IDE.
- Select __File__ >> __New Workspace__.
- Select __Project__ >> __Create new project__ >> __C__ >> __main__.
- Save the project in a new empty folder (e.g., `%USERPROFILE%\Documents\project`).
- Build the project (<kbd>F7</kbd>).
- Save the workspace.
- Select __Tools__ >> __Git init__ >> __OK__.
- Select __Tools__ >> __Git generate ignore__ >> __OK__.
- Select __Tools__ >> __Git commit__, enter with `Initial commit` as the commit message, select __All__ files >> __Commit__.

![image](https://user-images.githubusercontent.com/54443595/177304054-ae297fde-8da2-422c-98c8-c09485dea8bd.png)

- Use __Tools__ >> __Git log__ to check the repository status.

![image](https://user-images.githubusercontent.com/54443595/177304496-80fce339-26d2-4f90-8c0c-bf69a6e12849.png)


### Starting from a remote repository
For this, let's use this repository, which contains a workspace, as an example on how to clone an existing repository from a Git server.

- Select __Tools__ >> __Git clone__.
- Set URL to: `https://github.com/felipe-iar/ew-tortoise-integration`.
- Click __OK__ and __Close__ the window.

![image](https://user-images.githubusercontent.com/54443595/177302052-d097500c-3b90-4a72-a38d-5cda5f721128.png)

- Select __File__ >> __Open Workspace__ >> `%USERPROFILE%\Documents\ew-tortoise-integration\project.eww`.

## Tips
- Assign shortcuts for the most commonly used commands at __Tools__ >> __Options__ >> __Key bindings__ >> __Menu: Tools__.
- Modify or expand `tortoisegit.toolitems` with extra commands. The TortoiseGit documentation provides further reference in [Appendix D](https://tortoisegit.org/docs/tortoisegit/tgit-automation.html#tgit-automation-basics).

