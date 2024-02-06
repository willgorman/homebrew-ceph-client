# Build from source

## Remove existing ceph-client

```
brew uninstall ceph-client
```

## Manually set cython version

```
cython --version
```

If >= 3.0.0 then `brew uninstall cython` (assuming it was installed with brew and not pip)

```
pip3 install "cython<3.0.0"
```

Should install 0.29.37 as of this writing

##  Clone this repo

I'm not sure how to set this up as a tap so just install from the formula locally.

```
git clone git@github.com:willgorman/homebrew-ceph-client.git
cd homebrew-ceph-client
git checkout sonoma
```

## Install

```
brew install ceph-client.rb --build-from-source --debug --verbose
```

## Optional: manually create cython packages directory

If the install fails with a permission error creating directories then run this:

```
mkdir -p $(brew --prefix)/opt/cython/libexec/lib/python3.11/site-packages
```
