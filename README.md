# xxenv-latest

This **env plugin replaces the version specified in the argument with the latest version.

## Supported **env

- [pyenv](https://github.com/pyenv/pyenv)
- [rbenv](https://github.com/rbenv/rbenv) (Required [ruby-build](https://github.com/rbenv/ruby-build) to use ```rbenv latest install``` or ```rbenv latest uninstall```)
- [nodenv](https://github.com/nodenv/nodenv) (Required [node-build](https://github.com/nodenv/node-build) to use ```nodenv latest install``` or ```nodenv latest uninstall```)
- [goenv](https://github.com/syndbg/goenv)
- [phpenv](https://github.com/phpenv/phpenv) (Required [php-build](https://github.com/php-build/php-build) to use ```phpenv latest install``` or ```phpenv latest uninstall```)
- [luaenv](https://github.com/cehoffman/luaenv) (Required [lua-build](https://github.com/cehoffman/lua-build) to use ```luaenv latest install``` or ```luaenv latest uninstall```)

## Usage

Replaces '**env' with 'pyenv', 'rbenv', etc.

    **env latest <command> [<version-prefix|command-args>]

Supported commands is:
- install
- uninstall (All except the latest version)
- global
- local
- prefix

Original subcommands is:
- update-major:    Update the major version of the currently active version
- update-minor:    Update the minor version of the currently active version
- update-revision: Update the revision of the currently active version

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
    Latest version is '2.7.15'
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

Update the major version, minor version or revision of the currently active version
to the latest.

    $ pyenv install --list
    ...
    3.6.15
    ...
    3.9.10
    ...
    3.10.2
    ...
    $ pyenv global
    3.6.0
    $ pyenv latest update-revision
    Latest version is '3.6.15'
    Downloading Python-3.6.15.tar.xz...
    -> https://www.python.org/ftp/python/3.6.15/Python-3.6.15.tar.xz
    Installing Python-3.6.15...
    ...
    Installed Python-3.6.15 to /home/username/.pyenv/versions/3.6.15
    $ pyenv global
    3.6.15
    $ pyenv local 3.9.0
    $ pyenv latest update-revision
    Latest version is '3.9.10'
    Downloading Python-3.9.10.tar.xz...
    -> https://www.python.org/ftp/python/3.9.10/Python-3.9.10.tar.xz
    Installing Python-3.9.10...
    Installed Python-3.9.10 to /home/username/.pyenv/versions/3.9.10
    $ pyenv local
    3.9.10
    $ pyenv latest update-minor
    Latest version is '3.10.2'
    Downloading Python-3.10.2.tar.xz...
    -> https://www.python.org/ftp/python/3.10.2/Python-3.10.2.tar.xz
    Installing Python-3.10.2...
    Installed Python-3.10.2 to /home/username/.pyenv/versions/3.10.2
    $ pyenv local
    3.10.2
    $ pyenv global
    3.6.15

Set the global Python latest version.

    $ pyenv latest global
    $ python --version
    Python 3.7.2

Print, but not install the latest 2.7-based version of Python

    $ pyenv latest --print 2.7
    2.7.15

## License
MIT
