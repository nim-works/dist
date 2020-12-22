# dist

[![Test Matrix](https://github.com/disruptek/dist/workflows/CI/badge.svg?branch=1.2.9)](https://github.com/disruptek/dist/actions?query=workflow%3ACI)
![Minimum supported Nim version](https://img.shields.io/badge/nim-1.2.9%2B-informational?style=flat&logo=nim)
[![License](https://img.shields.io/github/license/disruptek/dist?style=flat)](#license)
[![buy me a coffee](https://img.shields.io/badge/donate-buy%20me%20a%20coffee-orange.svg)](https://www.buymeacoffee.com/disruptek)

a nim distribution

## What Is It?

The idea here is to curate a "batteries included" ecosystem of modules that
interoperate and form a broadly useful basis for projects. Ideally, the
distribution is so successful that we can move modules from the compiler's
standard library into the distribution.

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

### install the distribution
```
$ git clone --depth 1 https://github.com/disruptek/dist
$ cd dist
$ git submodule update --init .
```

### specify the distribution in your project configuration
```
$ cd ../project
$ echo "--path=../dist" >> nim.cfg
$ nim c project.nim
```

### update the distribution
```
$ cd ../dist
$ git pull
```

### switch distribution versions
```
$ cd ../dist
$ git checkout 1.5.1
```

### see what has changed and when
```
$ cd ../dist
$ git log
```

### tag distribution versions
```
$ cd ../dist
$ git tag -a works_with_myproject
```

### you get the idea... 😉

## License
MIT
