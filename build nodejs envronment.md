---
share: true
---

To build node js from source a good practive is to fork and then clone the project

Then you can look the build Nodejs guide https://github.com/quixote15/node/tree/main#building-nodejs

Tips:

The doc says to build node concurrently with 4 processess you should run
```
./configure
make -j4
```


However, for a faster development experience and reloading source code do this:

#### Speeding up frequent rebuilds when developing

If you plan to frequently rebuild Node.js, especially if using several branches, installing `ccache` can help to greatly reduce build times. Set up with:

On GNU/Linux:

```shell
sudo apt install ccache   # for Debian/Ubuntu, included in most Linux distros
export CC="ccache gcc"    # add to your .profile
export CXX="ccache g++"   # add to your .profile
```

On macOS:

```shell
brew install ccache      # see https://brew.sh
export CC="ccache cc"    # add to ~/.zshrc or other shell config file
export CXX="ccache c++"  # add to ~/.zshrc or other shell config file
```

This will allow for near-instantaneous rebuilds even when switching branches.

When modifying only the JS layer in `lib`, it is possible to externally load it without modifying the executable:

```shell
./configure --node-builtin-modules-path "$(pwd)"
```

The resulting binary won't include any JS files and will try to load them from the specified directory. The JS debugger of Visual Studio Code supports this configuration since the November 2020 version and allows for setting breakpoints.


Troubleshooting Gcc version
https://www.cyberithub.com/how-to-update-or-upgrade-gcc-to-latest-version-on-ubuntu-debian/