# RexxUp
The Rexx Package Manager

Nothing to see here yet - we need a package manager, it will be git based with initially mostly java and java compiled to native components

It needs to be both usable to install and build Rexx distributions as modules for those, like external function libraries or modules.

Let us know if you want to work on it.

## The plan
We have an easily (curl, wget) downloadable `rxup` command, which enables us to pull from a git repo that contains formulae for building rexx distro's, applications or modules. First stab at this will be Java (NetRexx) with jGit, second stage will be Graal compiled native executables. When interested, people can contribute native versions in C, Go or Rust, using the Git API. We use Github but steer clear from things that are Github but not Git.

Like other package managers, we can have prebuilt binaries for ISA's, OS, OS versions, or build from source. For native tools we need to lean on apt, yum and brew/port. For Windows, we need Windows people or declare dependencies that need to be manually installed.

## Design principles

1) There are tasks/package specifications for every package for ISA, OS and version. These are executable (with Rexx, of course). We can call the specs and the packages ‘packages’. 
2) These packages have releases and they are all in a git repo. 
3) There are specifications of dependencies, which are also versioned. 
4) The package manager can install Rexx implementations (brexx, crexx, Regina, ooRexx, bsf4ooRexx) as well as application packages, with or without source. 
5) The default and minimal operation is to download a zip, decompress it and suggest path settings corresponding to the platform. 
6) It should tell the user what it is doing and ask for permission (of the user) on every step; the permissions can be waived with a switch like -y (like the others do it). An action should be atomic and have rollback, so it works in a temp directory and do an atomic rename/rollback. 
7) It must always be possible to remove the package manager and start again.
8) It must always be possible to remove a package and try again, for example if the atomicity failed due to network or other trouble/
9) We try to be thrifty with other people’s bandwith.
10) Most of the infra (git, zip) needs to be built into the tools, to squish OS dependencies
11) There needs to be some rate limiting built in because of lunatics.
