# LeNet5_C
Codebase for working with [LeNet5 in C](https://github.com/fan-wenjie/LeNet-5) by [fan-wenjie](https://github.com/fan-wenjie).

## Getting Started with This Repo (this section toc still under construction)
- [x] [Install VS Code](#install-vs-code)
- [x] [Install useful VS Code Extensions](#install-useful-vscode-extensions)

### Install [Visual Studio Code](https://code.visualstudio.com/download)

### Install useful VS Code Extensions
- You'll want...
- [C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools)
- [C/C++ Extension Pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools-extension-pack)
- You can install these extensions within VS Code by searching for 'C++' in the Extensions view (Ctrl+Shift+X).

### Open this repo as a workspace in VS Code
- This repo should land in a folder called `LeNet5_C`
- Open VS Code then click File -> Open workspace from file...
- Select the workspace file `LeNet5_C.code-workspace`
- You may have to add folder to workspace which should be the parent directory of the code-workspace file, the workspace structure should look like this:

LeNet5/ <- this directory you create on your PC and add to workspace if VSCode didn't do that automatically \
├── .vscode  \
├── Library \
├── Output \
├── Source \
├── LeNet5_C.code-workspace <- this file you open in VSCode> \
├── README.md


### Install [MSYS2](https://www.msys2.org/)
- Installation directory should be as close as possible to `C:\`
- During installation it may take a while updating keys, at 50% progress, just let it finish it wil eventually finish
- Version: `msys2-x86_64-20250221`

### Install GCC compiler via MSYS2
- Open a MSYS2 terminal
- Run the command `pacman -Syu`
- input `y` if prompted
- the terminal may close, open another terminal if that happens
- Run the command `pacman -S mingw-w64-ucrt-x86_64-gcc`
- input `y` if prompted
- Run the command `pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain`
- press `enter` to accept default config if prompted
- input `y` if prompted
- GCC is now installed

### Add GCC compiler to your windows path
- In windows, open the system properties by click the start icon and typing `edit the system environment variables`
- system properties window will open, click the button `Environment Variables...` in the bottom right of the Advanced tab
- In the section `USer variables for <user>` locate the variable `Path` and select it
- Press the `Edit` button
- Press the button `New`
- Add the following `C:\msys64\ucrt64\bin`
- Click the `OK` button until all the windows have closed

### Check your GCC compiler version
- in a terminal input `gcc --version`

### Check your GDB version
- in a terminal input `gdb --version`

### Check your G++ version
- in a terminal input `g++ --version`

### Select your compiler in VS Code
- CAUTION in the following steps, if you see "cl.exe" this is the incorrect compiler, you may have to close VS Code and reopen the project for the compiler list to update...
- Press the play button in the top-right cornern of the file you want to run and select the `Run C/C++ File` button
- When you run a c/c++ file it will ask you to select the compiler, it should be the one located in the same place that you specified in your Path `C:\msys64\ucrt64\bin`
- Note: Pick the compiler that corresponds to the language you're using: c -> gcc, c++ -> g++
- In our case we're using gcc

### Import the LeNet5 source code into the VS Code project
- The [LeNet5 in C](https://github.com/fan-wenjie/LeNet-5) by [fan-wenjie](https://github.com/fan-wenjie) is already present in this repo, we copied the codebase to this repo to freeze the LeNet5 version. It was imported with the following steps.

- Copy the entire LeNet5 repo directory to LeNet5_C/Library folder, create the folder if it doesn't exist.

### Update the LeNet5 source code
- Download the new source code normally
- Repeat the steps above
- dont forget to push the new source with any new code

### Setup VS Code so it can compile LeNet5 source code
- You'll need a tasks.json file located in .vscode folder, this should already exist in the repo but if you try to compile and it can't find the SDK, it means there is no tasks.json
- Your tasks.json should have arguments pointing to the header and library files of the SDK
- Your tasks.json should also have arguments pointing to your source code
- more details about using VS Code this way can be found [here](https://code.visualstudio.com/docs/languages/cpp)

### Run the code
Hit play and it'll run, in VS Code, sometimes it switches to the Debug Console, to see actual output (such as training percentage) switch back to the terminal tab.

Don't forget to update your paths such as the location of the dataset, etc. etc.

### Easily Formatting this Readme file (when viewing in VS Code)

You can see a preview of how this readme will look when pushed to GitHub by opening the Readme.md file in VS Code then pressing the shortcut `ctrl + shift + v`.

For a markdown formatting cheatsheet visit this page for [standard syntax](https://github.com/adam-p/markdown-here/wiki/markdown-cheatsheet "Markdown Cheat-Sheet") and [extended syntax](https://www.markdownguide.org/extended-syntax/#definition-lists).

### Tool Versions

| Tool | Version| Date |
|:-------------:|:-------------:|:-------------:|
| MSYS2 | msys2-x86_64-20250221 |
| gcc | 14.2.0 | |
| gdb | 16.2 | |
| g++ | 14.2.0 | |