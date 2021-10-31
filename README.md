# dist

[![Test Matrix](https://github.com/nim-works/dist/workflows/CI/badge.svg?branch=1.6.1)](https://github.com/nim-works/dist/actions?query=workflow%3ACI)
![Minimum supported Nim version](https://img.shields.io/badge/nim-1.6.1%2B-informational?style=flat&logo=nim)
[![License](https://img.shields.io/github/license/nim-works/dist?style=flat)](#license)

a nim distribution

## What Is It?

The idea here is to curate a "batteries included" ecosystem of modules that
interoperate and form a broadly useful basis for projects. Ideally, the
distribution is so successful that we can move modules from the compiler's
standard library into the distribution.

[There's a little more detail in this Fusion RFC comment.](https://github.com/nim-lang/RFCs/issues/310#issuecomment-754130821)

## How Does It Work?

Each branch of the distribution will correspond to a version of the Nim
compiler. Some effort will be made towards *forward* compatibility, but little
effort will be made for backward compatibility -- check out the version of the
distribution that (at least) matches your compiler!

## What's The Point Of That?

Now compatibility of your project can be tied to specific compiler versions and
a monorepo of supporting software that should work together with that version
of Nim. No combinatorial explosion of dependency interoperability calculation
is necessary, and such calculations and tests may be shared by all users.

## What Goes Into The Distribution?

We'll start with the compiler's test suite of so-called **important packages**
and consider additional packages which help to test the distribution or add
broadly useful functionality.

## Okay, I'm Sold.  How Do I Use It?

### Automatic Installation of the Distribution

The easiest way to use the distribution is via **gitnim**:

https://github.com/nim-works/gitnim or https://gitnim.com/

```bash
$ git nim
```
![git nim](https://github.com/nim-works/gitnim/raw/master/docs/gitnim.svg "git nim")

### Manual Installation of the Distribution
```
$ git clone --depth 1 https://github.com/nim-works/dist
$ cd dist
$ git submodule update --init .
```

### Using the Distribution in Your Project
```
$ cd ../project
$ echo "--path=../dist" >> nim.cfg
$ nim c project.nim
```

### Updating the Distribution
```
$ cd ../dist
$ git pull
```

### Seeing What Changed and When
```
$ cd ../dist
$ git log
```

### Switching Distribution Versions
```
$ cd ../dist
$ git checkout 1.5.1
```

### Tagging Distribution Versions
```
$ cd ../dist
$ git tag -a works_with_myproject
```

### Switching to a Specific Tag
```
$ cd ../dist
$ git checkout works_with_myproject
```

### you get the idea... 😉

## License
MIT
