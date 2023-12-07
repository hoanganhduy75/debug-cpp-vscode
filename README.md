#Debugging C++ with VSCode in External Terminal on macOS#

This repository provides a solution for debugging C++ code in an external terminal on macOS using Visual Studio Code. The process involves making a simple adjustment to switch the debug console to an external terminal and performing cleanup tasks for unnecessary files, such as files with no extension and .dSYM files.

Steps:

1. Clone this repository and copy the \*.json files into the .vscode workspace folder.
2. Unzip the OpenTerVs.zip file and copy it into your applications folder. This tool enables the silent opening of the terminal and VSCode when executed.
   //The terminal will open two windows if not already running when debugging.//
3. Open the setting.json file and add the following command `&& rm ./$fileNameWithoutExt` to code-runner.executorMap. Set `"code-runner.ignoreSelection"` to true. Here's an example:
   `"code-runner.executorMap": {
    "cpp": "cd $dir && clang++ -std=c++2b -stdlib=libc++ $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt && rm ./$fileNameWithoutExt"
},
"code-runner.ignoreSelection": true`
   These adjustments streamline the debugging process and enhance the efficiency of C++ development within VSCode on macOS.
