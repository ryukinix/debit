# debit

Edit debian packages easilly (or more easier).

# How to install

```
curl https://raw.githubusercontent.com/ryukinix/debit/master/debit -o ~/.local/bin/debit
```

# How to use

You need to `unpack` your debian package to edit manually, for that
use:

```
debit unpack package.deb
```

That command will extract the following files:

```
├── control.tar.xz
├── data.tar.xz
├── debian-binary
├── extras-control
│   ├── conffiles
│   ├── control
│   └── md5sums
├── extras-data
│   ├── etc
│   └── usr
└── package.deb
```

You can edit the contents of extras-* directories and then after finished, in the
same directory you called `debit unpack`, create a new package with:

> :exclamation: Take care of extras-control files, specially update
> `extras-control/md5sums` file if you edit anything there (maybe
> debit should take care of that someday)

```
debit pack new_package.deb
```


# References

- https://alexandra-zaharia.github.io/posts/how-to-manually-modify-a-deb-package/
