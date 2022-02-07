# RexxUp
The Rexx Package Manager

Nothing to see here yet - we need a package manager, it will be git based with initially mostly java and java compiled to native components

It needs to be both usable to install and build Rexx distributions as modules for those, like external function libraries or modules.

Let us know if you want to work on it.

## The plan
We have an easily (curl, wget, http(s)client) downloadable `rxup` command, which enables us to pull from a git repo that contains formulae for downloading or building rexx distro's, applications or modules. First stab at this will be Java (NetRexx) with jGit, second stage will be Graal compiled native executables. After that, we can use Rexx drivers (bREXX, cREXX, ooRexx, Regina - the trick here will be to keep the Rexx source compatible). When interested, people can contribute native versions in C, Go or Rust, using the Git API. We use Github but steer clear from things that are Github but not Git, in order to be able to host our own repository in a number of places.

Like other package managers, we can have prebuilt binaries for ISA's, OS, OS versions, or build from source. For native tools we need to lean on apt, yum and brew/port. For Windows, we need Windows people or declare dependencies that need to be manually installed.

