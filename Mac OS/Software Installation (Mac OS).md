# Software Installation (Mac OS)

Note: This material is intended for educational purposes only. All rights reserved. Any unauthorized sharing or copying of this material, in any form, to any individual or party, for any use without prior permission, is strictly prohibited.

### Part 0: Prerequisites

### 0.1 Show Hidden Folder

- Go to your user home directory (Finder), type "Shift + command + ." to show all folders & files. You have to verify the installations by visualizing them later.
  **[Before]**
  ![](https://hackmd.io/_uploads/By1x1pytn.png)

**[After]**
able to see all hidden folders & files, which is important for installation & development later on.
![](https://hackmd.io/_uploads/BkFlJ6JK3.png)

### 0.2 Show File Extensions

- Finder -> Settings -> Advanced -> Check **"Show all filename extensions"**
  ![](https://hackmd.io/_uploads/SykXkTJYn.png)

### 0.3 Mac OS Version

- Lots of installation based on ==mac os version 10.1x +==.
  :::danger
  If your mac is under 10.1x, please raise it to Tutor/TA before starting the installation.
  :::

### Part 1: Homebrew

![](https://hackmd.io/_uploads/SyLVkTJY2.png)

- As a developer using mac, you have to try [Homebrew](https://brew.sh). It makes your life easier.
- Homebrew installs packages to their own directory and then symlinks their files into

```
/usr/local
```

(on macOS Intel).

- Homebrew won’t install files outside its prefix and you can place a Homebrew installation wherever you like.

### 1.0 Open Terminal

- **Command + space**, Type **"Terminal"** in the spotlight search bar.

#### 1.1 Install Homebrew (Follow the steps & complete the setup)

```
# via curl
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

![](https://hackmd.io/_uploads/r1o61Tktn.png)

- After installation, there will be 2 commands (refer to below screen) required you to execute.
  - Add default command to **.zprofile** (.zprofile is a "start-up" script for terminal)
    ![](https://hackmd.io/_uploads/S1PCJa1Fn.png)

**Run it one by one:**

```
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/vincentlau/.zprofile
```

```
eval "$(/opt/homebrew/bin/brew shellenv)"
```

Result:
![](https://hackmd.io/_uploads/Hy__0JAn2.png)

**Overall Result Check:**
**First**, Type "which brew", it should return the installed location & used location of brew.

```
which brew
```

The following is the result for apple chip. A path should be returned, that is correct result.
For intel chip, it should be inside /user/local/...
![](https://hackmd.io/_uploads/B1gee6yt2.png)

**Secondly**, type "echo $ PATH". This command is to print out the value stored in the variable $PATH.

```
echo $PATH
```

#### Result:

The following is the result for apple chip. A path with brew path should be returned, that is correct result.
For intel chip, it should be in /usr/local/...
![](https://hackmd.io/_uploads/B1g-gT1F2.png)

#### 1.2 Other brew commands

- Install wget

```
brew install wget
```

:::success
Result Check
:::
![](https://hackmd.io/_uploads/ryw0g61t2.jpg)

### Part 2: iTerm2

![](https://hackmd.io/_uploads/SkN-Z61Kh.png)

- macOS 10.14 or later
- Alternative for Terminal
- Brings the terminal into the modern age with new & useful features

#### 2.1 Install iTerm2 (by brew)

```
brew install --cask iterm2
```

![](https://hackmd.io/_uploads/ryuMWa1Yn.png)

- Check the app **"iTerm2"** in Finder Application, just like a normal Terminal.
- Keep "iTerm2" in the Dock as you will use it frequently in coming weeks.
  ![](https://hackmd.io/_uploads/BkLmWT1Kn.png)

#### Result:

![](https://hackmd.io/_uploads/Syh7b6yK2.png)

### Part 3: ZSH

![](https://hackmd.io/_uploads/SkoVbpyFh.png)

- [ZSH](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH), called the Z shell, is an extended version of the Bourne Shell (sh)
- It’s based on the same shell as Bash, ZSH has many of the same features, which is easy for everyone to switch over.

#### 3.1 Install ZSH by brew

- Latest mac OS version has built-in zsh already. You may have a check before installation.

```
# Check if you have zsh already:
which zsh
```

**[Result]** If you have zsh installed (expect MacOS should be with zsh bulit-in), the result should be as belows.
![](https://hackmd.io/_uploads/rk5DWTyF2.png)
:::warning
[Skip the following 2 steps, if you have zsh already as shown the above.]
:::

##### 1. Install ZSH & put it

```
brew install zsh
```

```
sudo sh -c "echo $(which zsh) >> /etc/shells"
```

Zsh installed by homebrew is in

```
/usr/local/bin/zsh
```

built-in zsh should be located in

```
/bin/zsh。
```

##### 2. Set zsh as default shell:

```
chsh -s $(which zsh)
```

:::success
[Everyone perform the following result checks before proceed.]
:::

#### [Result Check]

```
zsh --version
```

```
echo $SHELL
```

```
$SHELL --version
```

![](https://hackmd.io/_uploads/Sy5kf61t3.png)

#### 3.2 iTerm2 Preference

:::info
iTerm2 -> Settings (Left top corner) -> Profiles -> Terminal
:::
Make sure "Character encoding"/ "Report terminal type" are set correctly.
![](https://hackmd.io/_uploads/ryOWzp1Kh.png)

Font size, select your favourite font size in terminal
![](https://hackmd.io/_uploads/B1hWGTyKn.png)

### Part 4: Oh-my-zsh

[Oh-My-Zsh](https://github.com/ohmyzsh/ohmyzsh) is the most popular plugin framework for ZSH, and it comes with many built-in plugins and themes. **You can configure your own terminal with useful information, like text highlight/ font style/ system time/ icon/ git status, etc.**

### 4.1 Install oh-my-zsh

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

![](https://hackmd.io/_uploads/r1QwzpyYh.png)

After installing oh-my-zsh, you should find .zshrc in the home directory.
![](https://hackmd.io/_uploads/BJtvMTJYn.png)

:::success
Result Check
:::
After installed, you will find `.zshrc` in home directory.
![](https://hackmd.io/_uploads/H14OIb023.png)

After installed, you will find `.oh-my-zsh` in home directory.
![](https://hackmd.io/_uploads/BkdtLZR2h.png)

### 4.3 Install New Font

- Clone the cask-fonts library

```
brew tap homebrew/cask-fonts
```

![](https://hackmd.io/_uploads/SyXJsbR3h.png)

- Install Meslo-lg-nerd-font

```
brew install --cask font-meslo-lg-nerd-font
```

![](https://hackmd.io/_uploads/r1h42WAnn.png)

- Update Font setting in iTerm2, use **MesloFS Nerd Font**
  :::info
  iTerm2 -> Settings (Left top corner) -> Profiles -> Terminal
  :::
  ![](https://hackmd.io/_uploads/BJfjjZA22.png)

### 4.4 Install Powerlevel10k

Support special icon font without installing others plugins.

==Download powerlevel10k from github==

```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

![](https://hackmd.io/_uploads/rJmLmTyFh.png)

==Install zsh-autosuggestions==

```
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

![](https://hackmd.io/_uploads/rJIw76kK3.png)

==Install zsh-syntax-highlighting==

```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

![](https://hackmd.io/_uploads/Hkb_76Jt2.png)

In `.zshrc` file, you should:

- Add this line `plugins=(git zsh-syntax-highlighting zsh-autosuggestions)`
- Remove `plugins=(git)` by adding **#** at the beginning of the line.
- Save File

Sample: File `.zshrc`
![](https://hackmd.io/_uploads/ry6Y7T1Yn.png)

:::success
Result Check
:::
It should be placed into ==.oh-my-zsh/custom/themes/powerlevel10k== automatically. Please check it carefully.
![](https://hackmd.io/_uploads/ry297TkKh.png)

### 4.5 Change theme to powerlevel10k

- Add this line `ZSH_THEME="powerlevel10k/powerlevel10k"`
- Remove `ZSH_THEME="robbyrussell"` by adding **#** at the beginning of the line.
- Save File

```
# ZSH_THEME="robbyrussell"
ZSH_THEME="powerlevel10k/powerlevel10k"
```

![](https://hackmd.io/_uploads/SJQpQaJKh.png)

### 4.6 Execute .zshrc once again

- After rerun .zshrc (execute the below command in iTerm2), the configuration interface will be shown.
- OR you can restart iTerm2.

```
source ~/.zshrc
```

### 4.7 Your own theme style

Now, you can set up your own favourite style.

If you see this page, please just type "y" to install the latest version of the "Meslo Nerd Font".
![](https://hackmd.io/_uploads/r1XJ4T1Fh.png)

:::warning
It said DON'T exit by just click red circle. You can press command + Q, or iTerm2 -> Quit iTerm2.
:::
![](https://hackmd.io/_uploads/S1bsFMAnh.png)

Update Font in iTerm2 setting - **MesloLGS NF**
![](https://hackmd.io/_uploads/H1qacG0hh.png)

Type "y" if you can see the icon normally:

![](https://hackmd.io/_uploads/BkwZEaJY2.png)
![](https://hackmd.io/_uploads/B1s-VTyY2.png)
![](https://hackmd.io/_uploads/BkJz4pyY2.png)
![](https://hackmd.io/_uploads/ry4M4a1F2.png)

Your choice here: (My Choice: 2)
![](https://hackmd.io/_uploads/S19GE61th.png)

==Please choose **Unicode** to display those special icons in prompt corrently.==
![](https://hackmd.io/_uploads/ByuXE6JKh.png)

Your choice: (My Choice 4)
![](https://hackmd.io/_uploads/BJCD4aJF3.png)

My Choice 5
![](https://hackmd.io/_uploads/BySuVT1F2.png)

My choice 1
![](https://hackmd.io/_uploads/HJ5uNT1t3.png)

Show current time & time format (My choice: n)
![](https://hackmd.io/_uploads/HJJK46kKh.png)
![](https://hackmd.io/_uploads/BJQY4pyF2.png)

Prompt 內的分隔符號、末端的形狀
![](https://hackmd.io/_uploads/SkOY46kK3.png)
![](https://hackmd.io/_uploads/HJl2KNakF3.png)

Your choice here: (My choice 1)
![](https://hackmd.io/_uploads/rkz5Epkt3.png)

Your choice here : (My choice 2)
![](https://hackmd.io/_uploads/HyP9Eayth.png)

如果是分成兩行，可以幫第一行左右 Prompt 加連接線
![](https://hackmd.io/_uploads/r1A9VTJt2.png)

如果是分成兩行，可以為末端設定 Frame 風格，多一個圓弧線條
![](https://hackmd.io/_uploads/SJQiN61Fn.png)

設定兩次指令之間的 Prompt 空間 (My choice 1)
![](https://hackmd.io/_uploads/BJdjEaJFh.png)

會讓 Prompt 看起來更符合閱讀的語意，例如「on」某個 branch、「took」幾秒 (My choice 1)
![](https://hackmd.io/_uploads/SyajETyt3.png)

Select No (n)
![](https://hackmd.io/_uploads/HkIC4X02h.png)

Your own choice: (My Choice -> n)
![](https://hackmd.io/_uploads/HJGhN61Kn.png)

Choice 1
![](https://hackmd.io/_uploads/HJ_34T1tn.png)

Type "y" and enter.
![](https://hackmd.io/_uploads/Byn3VTyK3.png)

:::success
Result Check
:::
![](https://hackmd.io/_uploads/B1Q6VT1Y3.png)

The powerlevel10k configuration file (**.p10k.zsh**) is located in home directory.
Open it and edit it.
![](https://hackmd.io/_uploads/BJFpNaJt3.png)

Add additional information in iTerm, such as "ram" & "wifi".
For development, it's important to know the available memory and network environment.

- Uncomment (**delete #**) on the "ram" and "wifi" entry.
- Comment the "time" by adding "#"
- Save it.

![](https://hackmd.io/_uploads/B10pVTyF3.png)

:::success
Result Check
:::
![](https://hackmd.io/_uploads/BJ6TtUxcn.png)

OS Icon (https://www.nerdfonts.com/cheat-sheet) - You can find your favourite icon from cheat-sheet.

**Uncomment (remove the # at the beginning) on the line below ~/.p10k.zsh & update your icon.**
![](https://hackmd.io/_uploads/SyYgrp1t3.png)

:::success
Result Check
:::
![](https://hackmd.io/_uploads/ByW5wQRhh.png)

Change Background Color (if you want)
![](https://hackmd.io/_uploads/BkBZBp1Fn.png)

:::success
Result Check
:::
![](https://hackmd.io/_uploads/ByW5wQRhh.png)

**[Reference Only, you don't have to refer it, if you can setup all the above after the steps]**
Here are my config files for your reference (If you can't access, please raise it to Tutor/ TA)

- [.zshrc](https://github.com/hk-java/laptop-setup/blob/main/zsh/mac/.zshrc)
- [.zprofile](https://github.com/hk-java/laptop-setup/blob/main/zsh/mac/.zprofile)
- [.p10k.zsh](https://github.com/hk-java/laptop-setup/blob/main/zsh/mac/.p10k.zsh)

### Part 5: JDK

![](https://hackmd.io/_uploads/ByPBSpkKh.png)

![](https://hackmd.io/_uploads/ry9SHTyY2.png)

- As a Java developer, you have to download JDK (Java Development Kit) for Java Development. We will further explore JDK/ JRE/ JVM later on. Let's start the installation first.
- For Mac with apple chip M1/ M2, it is recommended to use Azul Zulu OpenJDK, which has better performance in terms of compilation time; for Intel chip, there is no big difference between various JDKs, let's use Zulu.
- Let's use JDK 17 (not 18), which is a LTS version (Long Term Support).
- **If you have installed JDK before, but not version 17, please still proceed this section.**
-

### 5.1 Install Azul Zulu JDK 17

Official - [OpenJDK Azul Zulu Download](https://www.azul.com/downloads/?version=java-17-lts&package=jdk#zulu)
Download and install it (as of 22-Jun, version up to 17.42.19). Follow the steps to complete the installation.

- **Apple chip**, go for **ARM 64-bit**
- **Intel chip**, go for **86 64-bit**
  ![](https://hackmd.io/_uploads/ByFFrakFn.png)

:::success
Result Check
:::

- Check the default java_home on Mac

```
/usr/libexec/java_home -V
```

![](https://hackmd.io/_uploads/r1Y9r6kY3.png)

- Setup environment variable for JAVA_HOME in ==.zshrc== in Home directory.
- **After update, SAVE file, restart the iTerm2**

```
export JAVA_HOME=$(/usr/libexec/java_home)
```

![](https://hackmd.io/_uploads/HJijrakKh.png)

:::success
Result Check
:::

- Check $JAVA_HOME, it should return the installed JDK

```
echo $JAVA_HOME
```

![](https://hackmd.io/_uploads/SyThBTkFn.png)

- Check Java Version

```
java --version
```

![](https://hackmd.io/_uploads/rkKTSaytn.png)

#### 5.2 ==[Reference Only, Skip it]== Switch installed JDKs

:::danger
JDK 21 LTS is coming out (Target Sep 2023)
:::

- You can check the zulu version from azul later on.
- You can install more than one JDK (Different JDK version or JDK provider)
  You can check all JDKs installed:

```
/usr/libexec/java_home -V
```

**[result check]** Shows Java 11 & Java 17 are installed in different path
![](https://hackmd.io/_uploads/Hy6xIa1Kh.png)

Switch to another JDK version by:

```
export JAVA_HOME=$(/usr/libexec/java_home -v 11) #switch to java 11
export JAVA_HOME=$(/usr/libexec/java_home -v 17) #switch to java 17
```

![](https://hackmd.io/_uploads/SJn-86kF2.png)

### Part 6: Git

![](https://hackmd.io/_uploads/BJUMLa1Fn.png)

- DevOps tool used for source code management.
- Free and open-source version control system used to handle small to very large projects efficiently.
- Tracks changes in the source code, enabling multiple developers to work together on non-linear development.
- ==There is a built-in git installed in Mac OS, apple-git. Not recommend to use it, as sometime git may have bug fix version. To upgrade the git easily, we use brew to install it.==

#### 6.1 Install Git

- Type the following command
- Restart iTerm2 to refresh the path

```
brew install git
```

:::success
Result Check
:::

- "where git" to check what git versions are installed. There are 2 git versions installed below, /usr/bin/git is the apple-git where "/opt/homebrew/..." is the one you installed by brew.
- "which git" to check which git version you are currently using.

```
git --version
```

![](https://hackmd.io/_uploads/H1Ew8aJFh.png)

If you have more than one git path, check the $PATH, ensure brew path come first.
![](https://hackmd.io/_uploads/rJKvUpyK3.png)

### 6.2 Create Github account

![](https://hackmd.io/_uploads/rkpKUTJth.png)

- As a developer, create a github account to start your journey.
- Create your own [Github Account](https://github.com) [ignore if you have created before].
- Update your github account info (https://hackmd.io/0L9QRERCSWSmeTEiIt4Q3w)
- It is a well known open source repository for sharing idea/ projects among the developers' community. You will find lots of useful projects/materials in github during your life as a developer. Over 80 million developers are using github as of 2022.
- You should store or backup your own projects/ material/ documents by github, so that you can refer to it in the future easily.

## 6.3 Setup SSH key

[Generate ssh key - from github](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

1. Open Terminal
2. Generate SSH key (by ed25519). Type this command to generate ssh key in your laptop ~/.ssh

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

3. ==**[Just Enter]**== Prompted to "Enter a file in which to save the key," **press Enter**. Accept default location.

```
> Enter a file in which to save the key
(/Users/you/.ssh/id_algorithm): [Press enter]
```

4. ==**[Just Enter]**== At the prompt, ask for a secure passphrase. Suggest to **press "enter" to skip.**

```
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```

:::success
Result Check
:::
![](https://hackmd.io/_uploads/rkheP61F3.png)

## 6.4 Insert ssh key to Github a/c

1. Login your github account
2. Click the icon at the right top corner, Go to **Settings**.
   ![](https://hackmd.io/_uploads/By0bD6yFh.png)

3. Go to **SSH and GPG keys**, and press N\*\*ew SSH key
   ![](https://hackmd.io/_uploads/rJQfPpkth.png)

4. Place the whole content of **==id_ed25519.pub==(public key)** to "Key" section shown below.
5. For title, simply put your email address.
   ![](https://hackmd.io/_uploads/SJaTvp1Yh.png)

:::success
Result Check
:::
After adding the ssh key, you can download the github repository by ==git clone== using ==SSH== (You will use it in later installation part).
![](https://hackmd.io/_uploads/SJmyu6kY2.png)

## 6.5 Git Config

- Change your name & email address. Execute the following commands in Terminal.

```
# set your name when using git
git config --global user.name "your name"
# set your email address when using git
git config --global user.email "your_email@gmail.com"
# default branch name when using git (set to main)
git config --global init.defaultBranch main
# Set pager off for git branch
git config --global pager.branch false
# set pager off for git diff
git config --global pager.diff false
```

Sample Screenshot:
![](https://hackmd.io/_uploads/HyJxaIl93.png)

Manually create the file and place to home directory.

- Add a `.gitignore_global` file in home folder
- Inside the folder, add those file names that you want Git to ignore before you "git push"

![](https://hackmd.io/_uploads/SJQ2AUec3.png)

![](https://hackmd.io/_uploads/ryhJ0Ul9n.png)

:::success
Result Check
:::
![](https://hackmd.io/_uploads/SJQ2AUec3.png)

![](https://hackmd.io/_uploads/rkf0CUl9n.png)

## Part 7: Apache Maven

![](https://hackmd.io/_uploads/rJRWupkt2.png)

- Project management and comprehension tool that provides developers a complete build lifecycle framework.
- Development teams can automate the project's "build" infrastructure in almost no time as Maven uses a standard directory layout and a default build lifecycle.
- You will learn and use it when developing a Java & Springboot application.

### 7.1 Install Maven 3

- By brew, you will get the latest stable version automatically, such as 3.8.6

```
brew install maven
```

:::success
Result Check
:::

- Check maven version
  - "Java version" should be the current java version
  - "Runtime path" should be same as java_home
  - Maven home should be in opt/homebrew/.., as you install maven by brew

```
mvn -v
```

![](https://hackmd.io/_uploads/r1J4OayK3.png)

Make sure "/opt/homebrew/..." is set in $PATH (Should be set automatically after installed homebrew, refer to Part 1).
![](https://hackmd.io/_uploads/HJ2NdpJK3.png)

## Part 8: VSCode (Visual Studio Code)

![](https://hackmd.io/_uploads/rJVS_pyt3.png)

### We will use VSCode to code your Java & Springboot programs in coming weeks!

- Visual Studio Code is a lightweight but powerful source code editor which runs on your desktop and is available for Windows, macOS and Linux.
- If you have programming background and want to use "IntelliJ IDEA" instead of VSCode, it's fine, just an IDE. But I would still recommend you to try VSCode, and feel how lightweight it is.

### 8.1 Install VSCode from Official Site

- [VScode Download](https://code.visualstudio.com/download) - **Mac OS 10.11 +**
- Be aware of "**apple**" or "**intel**" chip
  ![](https://hackmd.io/_uploads/Hy8__TJKn.png)

- After downloading and install it.
- Move to Application.
  ![](https://hackmd.io/_uploads/ryqdO6kKn.png)

### 8.2 Install 'code' shell command

- Launch VScode.app, ==**shift+command+p**==, type "install code" to execute the shell command
  ![](https://hackmd.io/_uploads/BySh_p1K2.png)

[Result check] Then, you will find "**code**" is placed in **==/usr/local/bin==**
![](https://hackmd.io/_uploads/BJU5_pJY3.png)
Next time you want launch the VSCode, just simply type "code ." in terminal (iTerm). **(i.e. There is a space between code and .)**
![](https://hackmd.io/_uploads/B1u6da1Yh.png)

### 8.3 Extensions

- Explorer / Search / Extensions are common functions in VScode. Put it in the menu bar on the left hand side of VSCode. (right click and select)
  ![](https://hackmd.io/_uploads/HJGAdpJt3.png)

- Extensions in VSCode help it become an integrated IDE with powerful functions, like color themes/ syntax management/ icon setting/ text color for different file types. All of those features enable you to code much more easily in VSCode.
  ![](https://hackmd.io/_uploads/rkPAOaJK3.png)

You can install all of the extensions below:

- ==Language Support for Java(TM) by Red Hat==
- ==Extension Pack for Java (Install this, the other 4 Java== extensions will be installed automatically)
- ==Maven for Java==
- ==Debugger for Java==
- ==Project Manager for Java==
- ==Test Runner for Java==
- ==Ayu (teabyii)==
- ==Prettier - Code formatter==
- ==One Dark Pro (binaryify)==
- ==Spring Initializr Java Support==
- ==Spring Boot Tools==
- ==Spring Boot Dashboard==
- ==Spring Boot Extension Pack==
- ==Lombok Annotations Support for VS Code==
- ==XML==
- ==YAML==
- ==SQL Beautify==
- ==Dependency Analytics==
- ==Markdown Preview Enhanced==

### 8.4 Code Formatter/ settings.json/ key shortcut

#### Step 1: VSCode general setting - settings.json

**In VSCode, press ==shift+command+p==, type "open user settings json" and select "Open User Settings(JSON)"**.

Overwrite your settings.json by [settings.json](https://github.com/hk-java/laptop-setup/blob/main/vscode/setting/mac/settings.json) in github/hk-java.
![](https://hackmd.io/_uploads/SJcXFp1Fn.png)

#### [Result]

![](https://hackmd.io/_uploads/HkZNtTyYn.png)

#### Step 2: VSCode Code Formatter - googlestyle.xml

CodeFormatter helps you auto-format your code to align maven checkstyle/pmd plugin.
From github laptop-setup, download the [googlestyle.xml](https://github.com/hk-java/laptop-setup/blob/main/vscode/code-formatter/java/googlestyle.xml) into the folder **~/.vscode**
![](https://hackmd.io/_uploads/HkWLtT1F3.png)

![](https://hackmd.io/_uploads/SJSUYTyYn.png)

- **In VSCode**, ==shift+command+p==, type "open user settings json" and select **"Open User Settings(JSON)"**.
- As you have downloaded it to ==~/.vscode/googlestyle.xml==, just update this path to java.format.settings.url
  ![](https://hackmd.io/_uploads/SJMtYakF3.png)

- Double Check **"lineSplit"** to 80 and **"comment.line_length"** to 200.
  ![](https://hackmd.io/_uploads/rJUYtTJY2.png)

#### step 3: VSCode keyboard shortcut - keybindings.json

- In **VSCode**, ==shift+command+p==, type **"keyboard shortcuts json"** & select **"Open Keyboard Shortcut(JSON)"**

- You can find the setup file for "Keyboard Shortcuts (JSON)" in github [keybindings.json](https://github.com/hk-java/laptop-setup/blob/main/vscode/keyboard-shortcut/mac/keybindings.json)
- Copy the file content to the above keybindings.json file.
  These are the shortcuts that you would frequently use:

  - ==shift+cmd+f==: Auto format the code
  - ==shift+cmd+o== : Organize java Imports, remove unused Imports
  - ==shift+cmd+k== : Restart VSCode

#### [Result]

- To let the above configurations take effect, you have to **restart the VSCode (you can just ==shift+cmd+k==)**

![](https://hackmd.io/_uploads/HJ9W00yK2.jpg)

## Part 9 Others

### 9.1 Unexpected file created - .DS_Store

![](https://hackmd.io/_uploads/rkZb0Rkth.png)
\*\*[Solution]

\*\* Disable the DS_Store file created

```
defaults write com.apple.desktopservices DSDontWriteNetworkStores true
defaults write com.apple.desktopservices DSDontWriteUSBStores true
```
