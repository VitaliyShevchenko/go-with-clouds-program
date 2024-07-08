### Build Tools References

Go through the following materials and get familiar with the build tools for a Go project.

* Tasfukes:
  * [Taskfile doc](https://taskfile.dev/)
    * Pay attention to Including other Taskfiles, dependencies, variables and [templating](https://taskfile.dev/reference/templating/)
* Devbox:
  * [Devbox quick start](https://www.jetify.com/devbox/docs/quickstart/)
  * [A nice blog on Devbox](https://alan.norbauer.com/articles/devbox-intro), it contains comparisons with analogues and explains some essential features.

### Tasks: introduce build tools to your project

- Introduce Taskfiles to your project (go, docker, generation, etc.)
  - Make sure that used filepaths are valid on a linux machine (needed later for CI), some functions for this are available [here](https://taskfile.dev/reference/templating/#task-functions).
- Introduce devbox to your project, build your project from devbox.
  - For windows users, try out devbox in [WSL](https://learn.microsoft.com/en-us/windows/wsl/).
