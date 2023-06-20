# brew install

```bash
./brew_install.sh
```

# iTerm2

官方链接：https://www.iterm2.com/

# 安装Oh my zsh

安装方法有两种，可以使用curl或wget，看自己环境或喜好：

## curl 安装方式

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

## wget 安装方式

```bash
sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```

# zsh-syntax-highlighting

```bash
cd ~/.oh-my-zsh/custom/plugins/
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
vi ~/.zshrc
```

这时我们再次打开zshrc文件进行编辑。找到plugins，此时plugins中应该已经有了git，我们需要把高亮插件也加上：
`plugins=(git)`修改为`plugins=(git zsh-syntax-highlighting)`


# jenv install

官方链接：https://www.jenv.be/

```bash
brew install jenv
```

## Bash

```bash
$ echo 'export PATH="$HOME/.jenv/bin:$PATH"' >> ~/.bash_profile
$ echo 'eval "$(jenv init -)"' >> ~/.bash_profile
```

## Zsh

```bash
$ echo 'export PATH="$HOME/.jenv/bin:$PATH"' >> ~/.zshrc
$ echo 'eval "$(jenv init -)"' >> ~/.zshrc
```

## nvm

官方地址：https://github.com/nvm-sh/nvm

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

```bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

## zshrc

```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```

# conda

https://github.com/conda-forge/miniforge

```bash
brew install miniforge
```

```bash
conda init zsh
```

## install X86 python

```bash
# 新建名为rosetta的虚拟环境，该环境中的Python架构为x86，经过转译运行
CONDA_SUBDIR=osx-64 conda create -n python.osx-64 python
conda activate python.osx-64
python -c "import platform;print(platform.machine())"  # 应输出“x86_64”

# make sure that conda commands in this environment use intel packages
conda env config vars set CONDA_SUBDIR=osx-64

conda deactivate      # 需要reactivate该虚拟环境，以使设置生效
conda activate python.osx-64
echo "CONDA_SUBDIR: $CONDA_SUBDIR"       # 应输出“CONDA_SUBDIR: osx-64”
```

```bash
ln -s /opt/homebrew/Caskroom/miniforge/base/envs/python.osx-64/bin/2to3 /usr/local/bin/2to3
ln -s /opt/homebrew/Caskroom/miniforge/base/envs/python.osx-64/bin/2to3-3.10 -> /usr/local/bin/2to3-3.10
ln -s /opt/homebrew/Caskroom/miniforge/base/envs/python.osx-64/bin/idle3 -> /usr/local/bin/idle3
ln -s /opt/homebrew/Caskroom/miniforge/base/envs/python.osx-64/bin/idle3.10 -> /usr/local/bin/idle3.10
ln -s /opt/homebrew/Caskroom/miniforge/base/envs/python.osx-64/bin/pip3 -> /usr/local/bin/pip3
ln -s /opt/homebrew/Caskroom/miniforge/base/envs/python.osx-64/bin/pip3.10 -> /usr/local/bin/pip3.10
ln -s /opt/homebrew/Caskroom/miniforge/base/envs/python.osx-64/bin/pydoc3 -> /usr/local/bin/pydoc3
ln -s /opt/homebrew/Caskroom/miniforge/base/envs/python.osx-64/bin/pydoc3.10 -> /usr/local/bin/pydoc3.10
ln -s /opt/homebrew/Caskroom/miniforge/base/envs/python.osx-64/bin/python3 -> /usr/local/bin/python3
ln -s /opt/homebrew/Caskroom/miniforge/base/envs/python.osx-64/bin/python3-config -> /usr/local/bin/python3-config
ln -s /opt/homebrew/Caskroom/miniforge/base/envs/python.osx-64/bin/python3.10 -> /usr/local/bin/python3.10
ln -s /opt/homebrew/Caskroom/miniforge/base/envs/python.osx-64/bin/python3.10-config -> /usr/local/bin/python3.10-config
```
