# WSL Development Environment

1.Install WSL (Ubuntu) and update to newest version

- ...
- Update, upgrade and install git
- Command to clone github dotfiles

  ```bash
  git clone --bare https://github.com/haininhhoang94/dotfiles $HOME/dotfiles
  /usr/bin/git --git-dir=$HOME/dotfiles --work-tree=$HOME
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

    3.Install neovim

  ```bash
  sudo apt install neovim
  $HOME/.config/nvim/utils/install.sh
  ```

  4.Install some more

  ```bash
  sudo apt-get install ranger fzf ctags
  sudo add-apt-repository ppa:lazygit-team/release
  sudo apt-get update
  sudo apt-get install lazygit
  ```

  - For FAR to work

  ```bash
  :UpdateRemotePlugins
  ```

  - TabNine to work

  ```bash
  TabNine::config
  ```

  - Install node support neovim

  ```bash
  sudo chown -R $USER /usr/local/lib
  sudo chown -R $USER /usr/local/bin
  sudo chown -R $USER /usr/lib
  npm i -g neovim
  ```

  - Install Neovim remote

  ```bash
  pip install neovim-remote
  ```

  4.Install R

  ```bash
  # install r
  sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
  sudo add-apt-repository 'deb https://cloud.r-project.org/bin/Linux/ubuntu focal-cran40/'
  sudo apt-get update
  # install r requirements package
  sudo apt install libcurl4-openssl-dev libssl-dev
  sudo apt install r
  ```

  [RStudio WSL](https://support.rstudio.com/hc/en-us/articles/360049776974-Using-RStudio-Server-in-Windows-WSL2)

  5.Install regedit neovim ?

  6.Install rsync neovim

  ```bash
  sudo apt install rsync
  ```

  7.Pycharm
  [Pycharm](https://www.jetbrains.com/help/pycharm/using-wsl-as-a-remote-interpreter.html)
