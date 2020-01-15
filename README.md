## Convention preparation:

1. Run:
    ```bash
    mkdir ~/Github/
    mkdir ~/Scripts
    mkdir ~/Workspace
    ```

## Install applications:

### 1. Brew

1. Run:
    ```bash
    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
    ```

### 2. iTerm 2

1. Run:
    ```bash
    brew cask install iterm2
    ```

### 3. Visual Studio Code

1. Run:
    ```bash
    brew cask install visual-studio-code 
    ```

### 4. ShiftIt

1. Run:
    ```bash
    brew cask install shiftit
    ```
2. Open ShiftIt and follow its instruction. 

### 5. Clipy

Having in mind that official [project](https://github.com/Clipy/Clipy) has been abandoned, please consider using its fork:

1. Download last release from [ian4hu-clipy-fork](https://github.com/ian4hu/Clipy/releases)
2. Unzip and install.
3. Add to snippets (`⌘ + ⇧ + V` and `Edit preferences`):
    ```
    ¯\_(ツ)_/¯
    (ʘ‿ʘ)
    ```

### 6. KeePassXC

1. Run:

    ```bash
    brew cask install keepassxc
    ```
2. Open KeePassXC and load your database.

### 7. SDKMAN!x1 & Java

1. Run: 

    ```bash
    curl -s "https://get.sdkman.io" | bash
    source "~/.sdkman/bin/sdkman-init.sh"
    sdk version
    sdk install java 11.0.5-amzn
    java -version
    ```

### 8. JetBrain ToolBox & Intellij

1. Run: 

    ```bash
    brew cask install jetbrains-toolbox
    ```
2. Open `JetBrains ToolBox` and install `Intellij`.

### 9. Gradle & Maven

1. Run:
    ```bash
    sdk install gradle 6.0
    sdk install maven 3.6.3
    
    gradle help
    maven -version
    ```
   
### 10. AWS CLI

1. Run:
    ```bash
    curl "https://s3.amazonaws.com/aws-cli/awscli-bundle.zip" -o "awscli-bundle.zip"
    unzip awscli-bundle.zip
    sudo ./awscli-bundle/install -i /usr/local/aws -b /usr/local/bin/aws
    ```
   
### 11. Terraform Switcher

1. Run:
    ```bash
    brew install warrensbox/tap/tfswitch
    ```
2. Run `tfswitch` and choose preferred version.    

### 12. MonoSnap
### 13. Franz
### 15. Spotify


## Additional configurations:

### 1. ZSH as default shell

1. Run `chsh -s $(which zsh)`.
2. Restart terminal.

### 2. Fancy prompt in ZSH

1. Install `oh-my-zsh` by running: 
    ```bash
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```
2. Install `powerlevel 9k` by running:
    ```bash
   brew tap sambadevi/powerlevel9k
   brew install powerlevel9k
   ```
   
3. Enable glyphs in iTerm: Preferences -> search for `Use build-in Powerlink glyphs` -> enable it.
4. Add to `~/.zshrc`:
    ```
    # Path to your oh-my-zsh installation.
    export ZSH="~/.oh-my-zsh"
    
    #Theme configuration
    ZSH_THEME="powerlevel9k/powerlevel9k"
    POWERLEVEL9K_PROMPT_ADD_NEWLINE=true
    POWERLEVEL9K_DISABLE_RPROMPT=true
    POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(time dir vcs)
    source /usr/local/opt/powerlevel9k/powerlevel9k.zsh-theme
    ``` 

### 3. FZF as finder in CLI

### 4. iTerm status bar with AWS_PROFILE, JAVA version, CPU and RAM consumption

### 5. Git with two profiles

1. Create an additional profile configuration:

    ```bash
    echo "[user]
        email = private-mail@gmail.com
        name = Grzegorz Kozub" > ~/Github/.gitconfig
    ```
    
2. Create main profile configuration:

    ```bash
    echo '[core]
       autocrlf = input
    
    [user]
       email = official-mail@gmail.com
       name = Grzegorz Kozub
    
    [includeIf "gitdir:~/Github/"]
       path = ~/Github/.gitconfig' >> ~/.gitconfig
    ```

### 6. Clean up local branches in GIT

### 7. FindCharsInPass script

### 8. MKCDir

    




