# R workflow in Visual Studio Code
![image](https://user-images.githubusercontent.com/57348932/123850783-b5f45d80-d91a-11eb-8ebc-c51180af8073.png)

[Visual Studio Code](https://github.com/microsoft/vscode) is a free, open-source and multi-platform code editor. Its [marketplace](https://marketplace.visualstudio.com/vscode) offers rich extensions to enhance its functionality. `R` workflow can be easily established in `VS Code` on `Windows`, `Mac OS` and `Linux`.


# Preparation
To establish a smooth `R` workflow, you need to install `R Base`, `VS Code` and `Python`. `Python` is needed because I will introduce an enhanced R console based on it.
- [R Base](https://cran.r-project.org/) Get the latest precompiled binary distribution. 
- [VS Code](https://code.visualstudio.com/)  Get the latest version for your platform.
- [Python](https://www.python.org/)  Get the latest release.

# Installing extensions
You can find the Extensions Tab at the left-most panel in `VS Code`. Click on it and then search for the following extensions. They are fundamental for you to work with `R`:
- [R](https://github.com/Ikuyadeu/vscode-R) It provides basic R support for `VS Code`. Install R, not R Tools.
- [R LSP Client](https://github.com/REditorSupport/languageserver) It provides powerful editor support including formatting and debugging.


I strongly recommend you to also install the following extensions:
- [Bracket Pair Colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer) It allows matching brackets to be identified with colours. This is quite useful in R coding.
- [GitHub Pull Requests and Issues](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github) It allows you to review and manage GitHub pull requests and issues.
- [GitLens — Git supercharged](https://github.com/eamodio/vscode-gitlens) It "helps you to visualize code authorship at a glance via Git blame annotations and code lens, seamlessly navigate and explore Git repositories, gain valuable insights via powerful comparison commands, and so much more".
- [One Dark Pro](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme) It is one of the most installed themes for `VS Code`.

Feel free to find your own extenstions combo in the marketplace, `VS Code` is highly customisable.

# Installing an alternative R console
![image](https://user-images.githubusercontent.com/57348932/123850591-834a6500-d91a-11eb-8f98-7a0d027b932a.png)

If you get bored with `R` console, [radian](https://github.com/randy3k/radian) provides you with an alternative choice. It has multiline editing and rich syntax highlight, along with many other enhancements. Don't forget to install `Python` before `radian`.

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

For more features, options and tricks, please visit [radian](https://github.com/randy3k/radian).

# Setting up VS Code
To use `radian`, you need to set up the R extension manually. Switch to the Extensions Tab in `VS Code`, find R, and then right click to access its extension settings.

- Enter R path for your platform. Note that here we use `radian`'s path instead. If you are on `Windows`, also note that there are two text boxes for you, you must enter the path of `radian.exe` into the one accepting `radian`
- Enable R session watcher.
- Press `Ctrl + Shift + P`, enter `create R terminal`, then press `Enter`. Your `radian` enhanced `R` console will open.
- In `R` console, install the following packages:
```
# packages to integrate VS Code with R
install.packages(c("jsonlite", "lintr", "languageserver", "httpgd"))
```
- Put the following option in `~/.Rprofile`:
```
# enable httpgd graphic device
options(vsc.use_httpgd = TRUE)
```
- Restart `VS Code` and create an `R` terminal.
- Plot something, the `httpgd` plot viewer will appear. Visit [httpgd](https://github.com/nx10/httpgd) for more tricks.
- Adjust UI layout，login your GitHub, explore more settings, extensions and themes...

`R` workflow in `VS Code` is now fully functional. Currently `VS Code` is not overall better than `RStudio`, but I do see its potential. Please open an issue if you have any problem, and don't forget to visit all the GitHub project links provided above to report an issue or find a solution.

**Last Update: 06/30/2021**

# Examples
**Theme, R extension, GitLens, radian terminal, UI layout**

![image](https://user-images.githubusercontent.com/57348932/123862034-22c22480-d928-11eb-96d4-49052e9a0579.png)

**Source control, httpgd plot viewer, R language server**

![image](https://user-images.githubusercontent.com/57348932/123862403-995f2200-d928-11eb-914c-4210b310e8f2.png)

