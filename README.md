# Spextool Manager

A quality of life utility for managing Spextool installations

## Features

- A basic management tool and activation script
- _Predictable runtime environment clutter_

## Getting started

**Clone the spexmgr repository**
```
git clone https://github.com/jhunkeler/spexmgr"
```

**Add spexmgr to your path**
```
export PATH="$(pwd)/spexmgr/bin:$PATH"
```

**Install a Spextool release**

Begin by listing all available versions:

```
$ spexmgr list
===========
 Available
===========
  1.4
  1.5
  2.0
  2.1
  2.2
  2.3
  3.1
  3.2
  3.3
  3.4
  4.0
  4.0.1
  4.0.2
  4.0.3
  4.1
```

Now install Spextool and its dependencies:

```
$ spexmgr install 4.1
spexmgr install 4.1
INFO: Downloading: Spextool_v4.1.tar.gz
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  190M  100  190M    0     0  22.2M      0  0:00:08  0:00:08 --:--:-- 25.8M
INFO: Installing: v4.1
INFO: Downloading: https://github.com/wlandsman/IDLAstro/archive/refs/heads/master.tar.gz
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
  0     0    0  9.9M    0     0  8180k      0 --:--:--  0:00:01 --:--:-- 12.9M
INFO: Downloading: https://idlastro.gsfc.nasa.gov/ftp/coyote_astron.tar.gz
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  276k  100  276k    0     0   833k      0 --:--:-- --:--:-- --:--:--  834k
INFO: Downloading: https://pages.physics.wisc.edu/~craigm/idl/down/cmtotal.tar.gz
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  689k  100  689k    0     0  1489k      0 --:--:-- --:--:-- --:--:-- 1489k
INFO: Installing dependency: IDLAstro
INFO: Installing dependency: coyote
INFO: Installing dependency: cmtotal
```

In this example IDLAstro, coyote, and cmtotal are installed to `share/` and Spextool-4.1 is installed to `spex/4.1`:

**Activate Spextool**

To activate a Spextool in your current shell:

```
source spexactivate 4.1
```

The activation script prepends `share/` and `spex/4.1` to `IDL_PATH`, and any previous activations are replaced. If you activate 4.1, then 4.0 in the same shell, then 4.1 will no longer be present in `IDL_PATH`.

**Test it**

*As of v4.0:*

```
$ idl
IDL> mc_testspextoolpath
```

*or earlier:*

TODO ITEM


## Commands

### spexmgr

```
usage: spexmgr [-h] {command} [arg ...]

Arguments:
  --help    -h        this message

Commands:
  clean               Removed cached packages/archives
  list                List available spextool releases
  install {release}   Install a spextool release
```


### spexactivate

```
usage: source bash {release}
```

