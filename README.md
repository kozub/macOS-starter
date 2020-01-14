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

### 8. JetBrain ToolBox

### 9. Intellij 

### 10. MonoSnap

### 11. Franz

### 12. Slack

### 13. AWS CLI

### 14. Gradle & Maven

### 15. Terraform Switch

### 16. Spotify


## Additional configurations:

### 1. ZSH as default shell

### 2. Fancy prompt

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
    echo "[core]
       autocrlf = input
    
    [user]
       email = official-mail@gmail.com
       name = Grzegorz Kozub
    
    [includeIf "gitdir:~/Github/"]
       path = ~/Github/.gitconfig" >> ~/.gitconfig
    ```

### 6. Clean up local branches in GIT

### 7. FindCharsInPass script

### 8. MKCDir

    




