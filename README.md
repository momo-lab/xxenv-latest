# xxenv-latest

This **env plugin replaces the version specified in the argument with the latest version.

## Supported **env

- [pyenv](https://github.com/pyenv/pyenv)
- [rbenv](https://github.com/rbenv/rbenv) (Required [ruby-build](https://github.com/rbenv/ruby-build) to use ```rbenv latest install``` or ```rbenv latest uninstall```)
- [nodenv](https://github.com/nodenv/nodenv) (Required [node-build](https://github.com/nodenv/node-build) to use ```nodenv latest install``` or ```nodenv latest uninstall```)

## Usage

Replaces '**env' with 'pyenv', 'rbenv', etc.

    **env latest <command> [<version-prefix|command-args>]

Supported commands is:
- install
- uninstall (All except the latest version)
- global
- local
- prefix

## Installation

Replaces '**env' with 'pyenv', 'rbenv', etc.

    git clone https://github.com/momo-lab/xxenv-latest.git "$(**env root)"/plugins/xxenv-latest

## Usage example

Install latest version of Python.

    $ pyenv latest install
    Latest version is '3.7.2'
    Downloading Python-3.7.2.tar.xz...
    -> https://www.python.org/ftp/python/3.7.2/Python-3.7.2.tar.xz
    Installing Python-3.7.2...
    Installed Python-3.7.2 to /home/username/.pyenv/versions/3.7.2


Install 2.7-based version of Python.

    $ pyenv latest install 2.7
    Lateset version is '2.7.15'
    Downloading Python-2.7.15.tar.xz...
    -> https://www.python.org/ftp/python/2.7.15/Python-2.7.15.tar.xz
    Installing Python-2.7.15...
    Installed Python-2.7.15 to /home/username/.pyenv/versions/2.7.15

Uninstall all expect the latest 2.7-based version of Python.

    $ pyenv versions
      2.7.13
      2.7.14
      2.7.15
      3.7.1
    * 3.7.2 (set by /home/username/.pyenv/version)
    $ pyenv latest uninstall 2.7
    pyenv: remove /home/username/.pyenv/versions/2.7.13? y
    pyenv: remove /home/username/.pyenv/versions/2.7.14? y
    $ pyenv versions
      2.7.15
      3.7.1
    * 3.7.2 (set by /home/username/.pyenv/versions/2.7.15)

Set the global Python latest version.

    $ pyenv latest global
    $ python --version
    Python 3.7.2

Print, but not install the latest 2.7-based version of Python

    $ pyenv latest --print 2.7
    2.7.15

## License
MIT
