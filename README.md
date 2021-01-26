# WSL Development Environment

## Windows Subsystem for Linux

1. Install WSL (Ubuntu) and update to newest version

- Update, upgrade and install git
  ```bash
  sudo apt-get update && sudo apt-get upgrade
  ```
- Command to clone github dotfiles

  ```bash
  sudo apt-get update && sudo apt-get upgrade
  git clone --bare https://github.com/haininhhoang94/dotfiles $HOME/dotfiles
  /usr/bin/git --git-dir=$HOME/dotfiles --work-tree=$HOME config --local status.showUntrackedFiles no
  ```

  2.Install ZSH, tmux, and Anaconda with utils file

  - Install zsh

  ```bash
  sudo apt-get install zsh tmux
  ```

  - Install Oh-my-zsh

  ```bash
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  chsh -s $(which zsh)
  ```

  - Exit terminal and start again

  - Install spaceship prompt theme

    ```bash
    mkdir "$ZSH_CUSTOM/themes"
    git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"
    ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
    ```

  - Downloads and install Anaconda

  ```bash
  wget -P  $HOME/Downloads https://repo.anaconda.com/archive/Anaconda3-2020.07-Linux-x86_64.sh
  sudo chmod +x $HOME/Downloads/Anaconda3-2020.07-Linux-x86_64.sh
  $HOME/Downloads/Anaconda3-2020.07-Linux-x86_64.sh
  ```

  - Install some more

  ```bash
  sudo apt-get install ranger fzf ctags ripgrep silversearcher-ag xclip
  sudo add-apt-repository ppa:lazygit-team/release
  sudo apt-get update
  sudo apt-get install lazygit
  ```

  - Install zsh plugin (autosuggestions, syntax-highlighting, fzf-tab):

  ```bash
  git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
  git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
  git clone https://github.com/Aloxaf/fzf-tab ~ZSH_CUSTOM/plugins/fzf-tab
  ```

  - Install tpm (tmux)

  ```bash
  sudo apt-get install tmux
  git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
  ```

  - Delete .zshrc and .bashrc

  ```bash
  rm -rf .zshrc .bashrc
  ```

  - dotfiles zsh and tmux check out

  ```bash
  /usr/bin/git --git-dir=$HOME/dotfiles --work-tree=$HOME status
  /usr/bin/git --git-dir=$HOME/dotfiles --work-tree=$HOME checkout
  ```

  - Exit the terminal again

  - Source for tmux

  ```bash
  tmux source-file ~/.tmux.conf
  dotfiles checkout ~/.git-credentials
  ```

  Press prefix + I (capital i, as in Install) to fetch the plugin.

  - Install conda environment

  ```bash
  conda env create -f $HOME/.environment-pyds.yml
  ```

  - Exit the terminal

3. Install neovim and clone neovim config (by myself)

```bash
sudo add-apt-repository ppa:neovim-ppa/stable
sudo add-apt-repository ppa:neovim-ppa/unstable
sudo apt install neovim
git clone https://github.com/haininhhoang94/nvim ~/.config/nvim
sudo chmod +x  ~/.config/nvim/utils/install.sh
$HOME/.config/nvim/utils/install.sh
```

4. Install some more

- For FAR to work

```bash
:UpdateRemotePlugins
```

- TabNine to work

```bash
TabNine::config
```

- Install node 12+

  ```bash
    sudo apt update
    sudo apt -y install curl dirmngr apt-transport-https lsb-release ca-certificates
    curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
    sudo apt -y install nodejs

  ```

- Install node support neovim
  (strikethrough)
  sudo chown -R $USER /usr/local/lib
  sudo chown -R $USER /usr/local/bin
  sudo chown -R $USER /usr/lib

```bash
sudo mkdir /usr/lib/node_modules/
sudo chown -R $USER /usr/lib/node_modules
sudo npm i -g neovim
```

    (Sudo is a bad idea but no better way currently) TODO

- Install Neovim remote

```bash
pip install neovim-remote
```

5. Install R

```bash
# install r
sudo apt install apt-transport-https software-properties-common
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
sudo add-apt-repository 'deb https://cloud.r-project.org/bin/linux/ubuntu focal-cran40/'
sudo apt-get update
# install r requirements package
sudo apt install libcurl4-openssl-dev libssl-dev
sudo apt install r-base r-base-dev
```

[RStudio WSL](https://support.rstudio.com/hc/en-us/articles/360049776974-Using-RStudio-Server-in-Windows-WSL2)

9.Youtubedl
[YoutubeDL](https://ytdl-org.github.io/youtube-dl/download.html)

```bash
  sudo pip install --upgrade youtube_dl
  sudo apt-get install ffmpeg
```

# Graveyard

5.Install regedit neovim ?

6.Install rsync neovim

```bash
sudo apt install rsync
```

13.Install ssh

```bash
sudo apt-get install openssh-server
sudo ssh-keygen -A
```

[SSH](https://www.hanselman.com/blog/how-to-ssh-into-wsl2-on-windows-10-from-an-external-machine)
[Disable Policies](https://stackoverflow.com/questions/41117421/ps1-cannot-be-loaded-because-running-scripts-is-disabled-on-this-system)

14.Add keygen from Windows to Linux:
```bash
ssh-keygen
type $env:USERPROFILE\.ssh\id_rsa.pub | ssh {IP-ADDRESS-OR-FQDN} "cat >> .ssh/authorized_keys"
```
[Link](https://code.visualstudio.com/docs/remote/ssh)