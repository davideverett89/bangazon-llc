# Installations

## Visual Studio Code Extensions

Install these extensions to get your VS Code editor set up for writing Python code.

* [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance)
* [Python Extension Pack](https://marketplace.visualstudio.com/items?itemName=donjayamanne.python-extension-pack)
* [SQLTools](https://marketplace.visualstudio.com/items?itemName=mtxr.sqltools)
* [SQLTools: SQLite Driver](https://marketplace.visualstudio.com/items?itemName=mtxr.sqltools-driver-sqlite)
* [Python Test Explorer](https://marketplace.visualstudio.com/items?itemName=LittleFoxTeam.vscode-python-test-adapter)

## Python via Pyenv

Run the commands specific to your system:

| OSX        | WSL           |
| ------------- |:-------------:|
| For `pyenv` to install correctly, you need the Xcode command line tools. Type the following command into your terminal and wait for the installation to complete: `xcode-select --install` | `sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python-openssl git` |
| | Update your PATH. Add the following line to your `.zshrc`: `export PATH="/home/linuxbrew/.linuxbrew/bin:/home/linuxbrew/.linuxbrew/sbin:$PATH"`      |

## Install Pyenv

```bash
brew install pyenv
pyenv install 3.8.1
pyenv global 3.8.1
```

Now, when you check the version of Python with the command below, it should return 3.8.1.

```
python --version
```

### Troubleshooting pyenv

If it still returns a different version, you will need to edit your `~/.zshrc` file. Add the following to the bottom of the file.

```sh
# Configure pyenv
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"

if command -v pyenv 1>/dev/null 2>&1; then
  eval "$(pyenv init -)"
fi
```

If try to run `pyenv install 3.8.1` and receive an error similar to the one below

```
BUILD FAILED (OS X 10.14.6 using python-build 20180424)

Inspect or clean up the working tree at /var/folders/r5/snljcx4x3dx8ccckm7hhdgy80000gn/T/python-build.20191008104728.34069 Results logged to /var/folders/r5/snljcx4x3dx8ccckm7hhdgy80000gn/T/python-build.20191008104728.34069.log
```

Run the following command in your terminal:

```sh
sudo installer -pkg /Library/Developer/CommandLineTools/Packages/macOS_SDK_headers_for_macOS_10.14.pkg -target /
```

After this is completed, try running `pyenv install 3.8.1` again

## Install Pipenv

This tool will manage 3rd party software that is needed for each of your projects.

```sh
brew install pipenv
```