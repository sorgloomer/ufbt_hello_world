# ufbt_hello_world

This is an example that demonstrates two specific problems when setting up a minimal development environment for Flipper Zero external FAP applications on a windows system.


## Steps to reproduce

 1. Have a Windows machine with python and vscode installed
 2. `git clone -b initial https://github.com/sorgloomer/ufbt_hello_world`
 3. `init_workspace.cmd`

    This installs venv and ufbt and runs the vscode_dist target
 4. Open the folder in vscode and install the recommended extensions
 
The setup succeeds, it can compile, but the developer experience has
two annoyances:

 1. It sets up the `zxh404.vscode-proto3` vscode extension, which is
    deprecated in favor of `drblury.protobuf-vsc`.

    `.vscode/extensions.json` needed to be updated.
 2. `clangd` does not find the standard headers.

    `.vscode/compiler_commands.json` updated to include the
    `arm-none-eabi/include` include path.
 
 I have committed the changes to the workspace into this repository to show
 how I fixed my working environment, but it would be great to have
 `vscode_dist` patched. Please see the [diff](https://github.com/sorgloomer/ufbt_hello_world/compare/original..master).
