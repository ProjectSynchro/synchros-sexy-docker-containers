# synchros-sexy-docker-containers
The title says it all baby.

This repository contains Dockerfiles for:

- naev-linux-lts (used for appimage release builds, oldest targetted glibc platform)
- naev-linux-latest (used for CI, and testing future platforms.)
- naev-steamruntime (Used to generate builds and for CI in the steamruntime (soldier) environment)
- naev-windows (Used to cross compile Windows releases, and CI)
- naev-macos (Used to cross compile MacOS releases, and CI)

Images are available from the Github Package Registry [here](https://github.com/users/ProjectSynchro/packages?repo_name=synchros-sexy-docker-containers)
They are used in https://github.com/naev/naev CI and CD workflows to provide standard build environments.
