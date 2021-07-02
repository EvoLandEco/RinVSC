# R workflow in Visual Studio Code
![image](https://user-images.githubusercontent.com/57348932/123850783-b5f45d80-d91a-11eb-8ebc-c51180af8073.png)

[Visual Studio Code](https://github.com/microsoft/vscode) is a free, open-source and multi-platform code editor. Its [marketplace](https://marketplace.visualstudio.com/vscode) offers rich extensions to enhance its functionality. `R` workflow can be easily established in `VS Code` on `Windows`, `Mac OS` and `Linux`.


# I. Preparation
To establish a smooth `R` workflow, you need to install `R Base`, `R Tools`, `VS Code` and `Python`. `Python` is needed because I will introduce an enhanced R console based on it.
- [R Base](https://cran.r-project.org/) Get the latest precompiled binary distribution. 
- [R Tools](https://cran.r-project.org/) Get the latest version.
- [VS Code](https://code.visualstudio.com/)  Get the latest version for your platform.
- [Python](https://www.python.org/)  Get the latest release.

# II. Installing extensions
You can find the Extensions Tab at the left-most panel in `VS Code`. Click on it and then search and install the following two extensions:
- [R](https://github.com/Ikuyadeu/vscode-R) It provides basic `R` support for `VS Code`.
- [R LSP Client](https://github.com/REditorSupport/languageserver) It provides powerful `R` language support including formatting and debugging.
- [R Debugger](https://github.com/ManuelHentschel/vscDebugger)  It provides `R` debugging capabilities to `VS Code`.

I strongly recommend you to also install the following extensions for the marketplace:
- [Bracket Pair Colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer) It allows matching brackets to be identified with colours. This is quite useful in coding.
- [GitHub Pull Requests and Issues](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github) It allows you to review and manage Github pull requests and issues.
- [GitLens — Git supercharged](https://github.com/eamodio/vscode-gitlens) It "helps you to visualize code authorship at a glance via Git blame annotations and code lens, seamlessly navigate and explore Git repositories, gain valuable insights via powerful comparison commands, and so much more".

Feel free to find your favourite themes and extenstions in the marketplace, `VS Code` is highly customisable. The following theme is my favourite:
- [One Dark Pro](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme) It is one of the most installed themes for `VS Code`.

# III. Installing an alternative R console
![image](https://user-images.githubusercontent.com/57348932/123850591-834a6500-d91a-11eb-8f98-7a0d027b932a.png)

If you get bored with `R` console, [radian](https://github.com/randy3k/radian) provides you with an alternative choice. It has multiline editing and rich syntax highlight, along with many other enhancements. It needs `Python` to work. 

You can easily install `radian` by `pip`
```
# install released version
pip install -U radian
# or the development version
pip install -U git+https://github.com/randy3k/radian
```
And if you use `conda`,
```
conda install -c conda-forge radian
```

For more features and options, please visit [radian](https://github.com/randy3k/radian).

# IV. Setting up VS Code and installing packages
To use `radian`, you need to set up the R extension manually. Switch to the Extensions Tab in `VS Code`, find R, and then right click to access its extension settings.

- Enter R path for your platform. Note that here we use `radian`'s path instead. If you are on `Windows`, also note that there are two text boxes for you, you must enter the path of `radian.exe` into the one accepting `radian`
- Enable R session watcher.
- Press `Ctrl + Shift + P`, enter `create R terminal`, then press `Enter`. Your `radian` enhanced `R` console will open.

The extensions relies on the following packages, you need to install them manually:
- [httpgd](https://github.com/nx10/httpgd)  It provides a better user experience when dealing with R graphic.
- [languageserver](https://github.com/REditorSupport/languageserver) `R LSP Client` relies on it.
- [vscDebugger](https://github.com/ManuelHentschel/vscDebugger) `R Debugger` relies on it, there is no release for `R` 4.1.0, so you need to compile and install using `devtools`.

```
# dependencies are also included
install.packages(c("R6", "jsonlite", "lintr", "languageserver", "httpgd", "rlang"))
devtools::install_github("ManuelHentschel/vscDebugger")
```

The last step, put the following option in `~/.Rprofile` to enable httpgd graphics device:
```
options(vsc.use_httpgd = TRUE)
```

`R` workflow in `VS Code` is now fully functional. You can try some demos. 

# V. Tricks and workarounds
The developers of the extensions are actively updating and implementing new features, and they are planning to integrate all these extensions to make installation easier for all users. Visit [vscode-r wiki](https://github.com/REditorSupport/vscode-R/wiki/) for more tricks and instructions. 


- Plot something, the `httpgd` plot viewer will appear.
- You can find workspace viewer and help pages in the R Tab. The workspace viewer is not as powerful as that in `R Studio` now, but an update is coming.
- `VS Code` UI is much more flexible that `R Studio`, right click on all the panels and tabs to see what you can do.
- Always remember to hit `Tab` when you are typing something in radian (R console) to trigger auto-completion

**Last Update: 02/07/2021**

# VI. Examples
**Theme, R extension, GitLens, radian terminal, UI layout**

![image](https://user-images.githubusercontent.com/57348932/123862034-22c22480-d928-11eb-96d4-49052e9a0579.png)

**Source control, httpgd plot viewer, R language server**

![image](https://user-images.githubusercontent.com/57348932/123862403-995f2200-d928-11eb-914c-4210b310e8f2.png)

