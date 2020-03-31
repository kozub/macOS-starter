## Convention preparation:

1. Run:
    ```
    mkdir ~/Github/
    mkdir ~/Scripts
    mkdir ~/Workspace
       
    echo 'alias python="python3"
    alias g=git
    export AWS_PROFILE=myprofile' >> ~/.env
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

### 7. SDKMAN! & Java

1. Run: 

    ```bash
    curl -s "https://get.sdkman.io" | bash
    source "~/.sdkman/bin/sdkman-init.sh"
    echo 'source "$HOME/.sdkman/bin/sdkman-init.sh"' >> ~/.zshrc
    sdk version
    sdk install java 11.0.5-amzn
    sdk install java 8.0.232-amzn
    java -version
    ```
2. Add additional aliases:
    ```
    echo '
    jdk8 ()
    {
        sdk use java  8.0.232-amzn
        java -version
    }
    jdk11 ()
    {
        sdk use java 11.0.5-amzn
        java -version
    }
    jdk11
    ' >> ~/.env
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
   
 2. Create config files: 
```bash 

echo '
[myprofile]
aws_access_key_id = XXX
aws_secret_access_key = XXX' > ~/.aws/credentials

echo '
[myprofile]
output = json
region = eu-west-1' > ~/.aws/config
```
   
### 11. Terraform Switcher

1. Run:
    ```bash
    brew install warrensbox/tap/tfswitch
    ```
2. Run `tfswitch` and choose preferred version.    

### 12. Franz - communicators aggregator.

1. Run:
    ```bash
    brew cash install franz
    ```
2. Open Franz and log in.   
   
### 13. MonoSnap
### 14. Spotify

1. Run:
    ```
    brew cask install spotify
    ```

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
    POWERLEVEL9K_DIR_HOME_BACKGROUND='deepskyblue1'
    POWERLEVEL9K_DIR_HOME_SUBFOLDER_BACKGROUND='steelblue3'
    POWERLEVEL9K_DIR_DEFAULT_BACKGROUND='gold1'
    source /usr/local/opt/powerlevel9k/powerlevel9k.zsh-theme
    ``` 

### 3. Colored files in console

    1. Run:
    ```
    echo `
    export CLICOLOR=1
    export LSCOLORS=GxFxCxDxBxegedabagaced' >> ~/.zshrc
    ```

### 4. FZF as finder in CLI

1. Run: 
    ```
    brew install fzf
    $(brew --prefix)/opt/fzf/install
   ```
   
2. Open your `.zshrc` file and add to `fzf` to plugins.
   
### 5. ZSH history

1. Add configuration to your `.zshrc` by running command

   ```
   echo '
   # History settings
   setopt inc_append_history
   setopt share_history
   HISTFILE="$HOME/.zsh_history"
   HISTSIZE=10000000
   SAVEHIST=10000000' >> ~/.zshrc 
   ```

### 6. iTerm status bar with AWS_PROFILE, JAVA version, CPU and RAM consumption

1. Open iTerm's Preferences -> Profile -> Session and enable "Status bar enabled"
2. Click on "Configure Status Bar" and add your preferred items.
3. Add new `Interpoled-String` component to the bar with value `\(user.awsProfile)`
3. Go to Appearance and set "Status bar location" to bottom.
4. Run: 
    ```
    curl -L https://iterm2.com/shell_integration/zsh \
    -o ~/.iterm2_shell_integration.zsh
    ```
5. Run: 
    ```
    echo '
    source ~/.iterm2_shell_integration.zsh
    iterm2_print_user_vars() {
      iterm2_set_user_var awsProfile $AWS_PROFILE
    }' >> ~/.zshrc 
    ```

### 7. Git with two profiles

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

### 8. Clean up local branches in GIT

```bash
echo '
# remove all local branches
alias git-cleanup="git fetch -p && git branch -vv | grep \x27origin/.*: gone]\x27 | awk \x27{print \$1}\x27 | xargs git branch -D"
' >> ~/.env
```
[source](https://medium.com/darek1024/how-to-clean-local-git-branches-that-were-removed-on-the-remote-4d76f7de93ac)

### 9. FindCharsInPass script

### 10. MKCDir

1. Run: 

```bash
echo '
# mkdir + cd
mkcdir ()
{
    mkdir -p -- "$1" &&
      cd -P -- "$1"
};' >> ~/.env
```

### 11. ZSH autosuggestions

1. Add configuration to your `.zshrc` by running command

   ```
   echo '
   # Enable autosuggestions
   CASE_SENSITIVE="false"
   setopt MENU_COMPLETE
   setopt no_list_ambiguous
   
   autoload -Uz compinit
   compinit
   zstyle ":completion:*" menu yes select'
   ```


