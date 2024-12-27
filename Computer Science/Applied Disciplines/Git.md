## What is Git?
- The stupid content tracker.
- _Git_ is a distributed version control system that tracks versions of files. It is often used to control source code by programmers who are developing software collaboratively.
- _Git_ goals is to include speed, data integrity, and support for distributed, non-linear workflows - thousands of parallel branches running on different computers.
- _Git_ is a fast, scalable, distributed revision control system with an unusually rich command set that provides both high-level operations and full access to internals.
## Why was Git created?

- _Git_ was created for use in the development of the [[Linux Kernel]] by Linus Torvalds and others developing the kernel.
## [About version control and Git](https://docs.github.com/en/get-started/using-git/about-git#about-version-control-and-git)

A version control system, or VCS, tracks the history of changes as people and teams collaborate on projects together. As developers make changes to the project, any earlier version of the project can be recovered at any time.

Developers can review project history to find out:

- Which changes were made?
- Who made the changes?
- When were the changes made?
- Why were changes needed?

VCSs give each contributor a unified and consistent view of a project, surfacing work that's already in progress. Seeing a transparent history of changes, who made them, and how they contribute to the development of a project helps team members stay aligned while working independently.

In a distributed version control system, every developer has a full copy of the project and project history. Unlike once popular centralized version control systems, DVCSs don't need a constant connection to a central repository. Git is the most popular distributed version control system. Git is commonly used for both open source and commercial software development, with significant benefits for individuals, teams and businesses.

- Git lets developers see the entire timeline of their changes, decisions, and progression of any project in one place. From the moment they access the history of a project, the developer has all the context they need to understand it and start contributing.
    
- Developers work in every time zone. With a DVCS like Git, collaboration can happen any time while maintaining source code integrity. Using branches, developers can safely propose changes to production code.
    
- Businesses using Git can break down communication barriers between teams and keep them focused on doing their best work. Plus, Git makes it possible to align experts across a business to collaborate on major projects.
## [About repositories](https://docs.github.com/en/get-started/using-git/about-git#about-repositories)

A repository, or Git project, encompasses the entire collection of files and folders associated with a project, along with each file's revision history. The file history appears as snapshots in time called commits. The commits can be organized into multiple lines of development called branches. Because Git is a DVCS, repositories are self-contained units and anyone who has a copy of the repository can access the entire codebase and its history. Using the command line or other ease-of-use interfaces, a Git repository also allows for: interaction with the history, cloning the repository, creating branches, committing, merging, comparing changes across versions of code, and more.

Through platforms like GitHub, Git also provides more opportunities for project transparency and collaboration. Public repositories help teams work together to build the best possible final product.
### [Basic Git commands](https://docs.github.com/en/get-started/using-git/about-git#basic-git-commands)

To use Git, developers use specific commands to copy, create, change, and combine code. These commands can be executed directly from the command line or by using an application like GitHub Desktop. Here are some common commands for using Git:

- `git init` initializes a brand new Git repository and begins tracking an existing directory. It adds a hidden subfolder within the existing directory that houses the internal data structure required for version control.
    
- `git clone` creates a local copy of a project that already exists remotely. The clone includes all the project's files, history, and branches.
    
- `git add` stages a change. Git tracks changes to a developer's codebase, but it's necessary to stage and take a snapshot of the changes to include them in the project's history. This command performs staging, the first part of that two-step process. Any changes that are staged will become a part of the next snapshot and a part of the project's history. Staging and committing separately gives developers complete control over the history of their project without changing how they code and work.
    
- `git commit` saves the snapshot to the project history and completes the change-tracking process. In short, a commit functions like taking a photo. Anything that's been staged with `git add` will become a part of the snapshot with `git commit`.
    
- `git status` shows the status of changes as untracked, modified, or staged.
    
- `git branch` shows the branches being worked on locally.
    
- `git merge` merges lines of development together. This command is typically used to combine changes made on two distinct branches. For example, a developer would merge when they want to combine changes from a feature branch into the main branch for deployment.
    
- `git pull` updates the local line of development with updates from its remote counterpart. Developers use this command if a teammate has made commits to a branch on a remote, and they would like to reflect those changes in their local environment.
    
- `git push` updates the remote repository with any commits made locally to a branch.

## SYNOPSIS

_git_ \[-v | --version] \[-h | --help] \[-C \<path>] \[-c <\name>=\<value>]
    \[--exec-path\[=\<path>]] \[--html-path] \[--man-path] \[--info-path]
    \[-p | --paginate | -P | --no-pager] \[--no-replace-objects] \[--no-lazy-fetch]
    \[--no-optional-locks] \[--no-advice] \[--bare] \[--git-dir=\<path>]
    \[--work-tree=\<path>] \[--namespace=\<name>] \[--config-env=\<name>=\<envvar>]
    \<command> \[\<args>]

## OPTIONS

-v
--version
- Prints the Git suite version that the git program came from.
	
- This option is internally converted to `git version ...` and accepts the same options as the git-version\[1] command. If `--help` is also given, it takes precedence over `--version.

-h
--help
-  Prints the synopsis and a list of the most commonly used commands. If the option `--all` or `-a` is given then all available commands are printed. If a Git command is named this option will bring up the manual page for that command.
	   
- Other options are available to control how the manual page is displayed. See git-help[1] for more information, because git --help ... is converted internally into git help ....

-C \<path>

- Run as if git was started in \<path> instead of the current working directory. When multiple -C options are given, each subsequent non-absolute -C \<path> is interpreted relative to the preceding -C \<path>. If \<path> is present but empty, e.g. -C "", then the current working directory is left unchanged.
    
- This option affects options that expect path name like --git-dir and --work-tree in that their interpretations of the path names would be made relative to the working directory caused by the -C option. For example the following invocations are equivalent:
    `git --git-dir=a.git --work-tree=b -C c status
    `git --git-dir=c/a.git --work-tree=c/b status`

-c \<name>=\<value>
- Pass a configuration parameter to the command. The value given will override values from configuration files. The \<name> is expected in the same format as listed by git config (subkeys separated by dots).
	
- Note that omitting the = in git -c foo.bar ... is allowed and sets foo.bar to the boolean true value (just like [foo]bar would in a config file). Including the equals but with an empty value (like git -c foo.bar= ...) sets foo.bar to the empty string which git config --type=bool will convert to false.
 
--config-env=\<name>=\<envvar>

- Like -c \<name>=\<value>, give configuration variable \<name> a value, where \<envvar> is the name of an environment variable from which to retrieve the value. Unlike -c there is no shortcut for directly setting the value to an empty string, instead the environment variable itself must be set to the empty string. It is an error if the <envvar> does not exist in the environment. <envvar> may not contain an equals sign to avoid ambiguity with <name> containing one.

    This is useful for cases where you want to pass transitory configuration options to git, but are doing so on operating systems where other processes might be able to read your command line (e.g. /proc/self/cmdline), but not your environment (e.g. /proc/self/environ). That behavior is the default on Linux, but may not be on your system.

    Note that this might add security for variables such as http.extraHeader where the sensitive information is part of the value, but not e.g. url.<base>.insteadOf where the sensitive information can be part of the key.
--exec-path[=<path>]

    Path to wherever your core Git programs are installed. This can also be controlled by setting the GIT_EXEC_PATH environment variable. If no path is given, git will print the current setting and then exit.
--html-path

    Print the path, without trailing slash, where Git’s HTML documentation is installed and exit.
--man-path

    Print the manpath (see man(1)) for the man pages for this version of Git and exit.
--info-path

    Print the path where the Info files documenting this version of Git are installed and exit.
-p
--paginate

    Pipe all output into less (or if set, $PAGER) if standard output is a terminal. This overrides the pager.<cmd> configuration options (see the "Configuration Mechanism" section below).
-P
--no-pager

    Do not pipe Git output into a pager.
--git-dir=<path>

    Set the path to the repository (".git" directory). This can also be controlled by setting the GIT_DIR environment variable. It can be an absolute path or relative path to current working directory.

    Specifying the location of the ".git" directory using this option (or GIT_DIR environment variable) turns off the repository discovery that tries to find a directory with ".git" subdirectory (which is how the repository and the top-level of the working tree are discovered), and tells Git that you are at the top level of the working tree. If you are not at the top-level directory of the working tree, you should tell Git where the top-level of the working tree is, with the --work-tree=<path> option (or GIT_WORK_TREE environment variable)

    If you just want to run git as if it was started in <path> then use git -C <path>.
--work-tree=<path>

    Set the path to the working tree. It can be an absolute path or a path relative to the current working directory. This can also be controlled by setting the GIT_WORK_TREE environment variable and the core.worktree configuration variable (see core.worktree in git-config[1] for a more detailed discussion).
--namespace=<path>

    Set the Git namespace. See gitnamespaces[7] for more details. Equivalent to setting the GIT_NAMESPACE environment variable.
--bare

    Treat the repository as a bare repository. If GIT_DIR environment is not set, it is set to the current working directory.
--no-replace-objects

    Do not use replacement refs to replace Git objects. This is equivalent to exporting the GIT_NO_REPLACE_OBJECTS environment variable with any value. See git-replace[1] for more information.
--no-lazy-fetch

    Do not fetch missing objects from the promisor remote on demand. Useful together with git cat-file -e <object> to see if the object is locally available. This is equivalent to setting the GIT_NO_LAZY_FETCH environment variable to 1.
--no-optional-locks

    Do not perform optional operations that require locks. This is equivalent to setting the GIT_OPTIONAL_LOCKS to 0.
--no-advice

    Disable all advice hints from being printed.
--literal-pathspecs

    Treat pathspecs literally (i.e. no globbing, no pathspec magic). This is equivalent to setting the GIT_LITERAL_PATHSPECS environment variable to 1.
--glob-pathspecs

    Add "glob" magic to all pathspec. This is equivalent to setting the GIT_GLOB_PATHSPECS environment variable to 1. Disabling globbing on individual pathspecs can be done using pathspec magic ":(literal)"
--noglob-pathspecs

    Add "literal" magic to all pathspec. This is equivalent to setting the GIT_NOGLOB_PATHSPECS environment variable to 1. Enabling globbing on individual pathspecs can be done using pathspec magic ":(glob)"
--icase-pathspecs

    Add "icase" magic to all pathspec. This is equivalent to setting the GIT_ICASE_PATHSPECS environment variable to 1.
--list-cmds=<group>[,<group>…​]

    List commands by group. This is an internal/experimental option and may change or be removed in the future. Supported groups are: builtins, parseopt (builtin commands that use parse-options), main (all commands in libexec directory), others (all other commands in $PATH that have git- prefix), list-<category> (see categories in command-list.txt), nohelpers (exclude helper commands), alias and config (retrieve command list from config variable completion.commands)
--attr-source=<tree-ish>

    Read gitattributes from <tree-ish> instead of the worktree. See gitattributes[5]. This is equivalent to setting the GIT_ATTR_SOURCE environment variable.

