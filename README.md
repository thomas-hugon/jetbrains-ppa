# Deprecation notice!

I will no longer maintain this project. I don't see it serving a purpose anymore since

* Jetbrains [has added all their products as snaps on snapcraft.io](https://snapcraft.io/search?q=jetbrains) now (I'm using that now)
* travis-ci.org is now in readonly mode and will be removed at some point (would need investment that I don't think is worth my time)

If anyone would like to adopt it, feel free to fork.

# Inofficial Jetbrains PPA

This is the inofficial Jetbrains PPA which you can use to get the latest and greatest products from Jetbrains.

Currently, the following packages are supported and automatically updated using [TravisCI](https://travis-ci.org/JonasGroeger/jetbrains-ppa).

* CLion `clion`
* DataGrip `datagrip`
* GoLand `goland`
* IntelliJ IDEA Community `intellij-idea-community`
* IntelliJ IDEA Ultimate `intellij-idea-ultimate`
* PhpStorm `phpstorm`
* PyCharm Community `pycharm-community`
* PyCharm Education `pycharm-education`
* PyCharm Professional `pycharm-professional`
* Rider `rider`
* RubyMine `rubymine`
* WebStorm `webstorm`

# Usage

To use it, enter the commands below, one by one. They download the correct GPG Key and add this repositories sources to your system sources.

```
curl -s https://s3.eu-central-1.amazonaws.com/jetbrains-ppa/0xA6E8698A.pub.asc | sudo apt-key add -
echo "deb http://jetbrains-ppa.s3-website.eu-central-1.amazonaws.com bionic main" | sudo tee /etc/apt/sources.list.d/jetbrains-ppa.list > /dev/null
sudo apt-get update
```

To install for example IntelliJ Idea Ultimate, you can now run

```
sudo apt-get install intellij-idea-ultimate
```

If you still have the sources from [my Launchpad PPA](https://launchpad.net/~jonas-groeger/+archive/ubuntu/jetbrains), please run:

```
sudo rm -f /etc/apt/sources.list.d/jetbrains.list{,.distUpgrade,.save}
```

If you have any issues, please [create a GitHub issue](https://github.com/JonasGroeger/jetbrains-ppa/issues/new).

## I want another package

If you want a package for another Jetbrains product please [create a GitHub issue](https://github.com/JonasGroeger/jetbrains-ppa/issues/new).

## Why not use the [official snap packages](https://snapcraft.io/search?q=jetbrains)?

Sure! If you like snap packages, go ahead. However, not all packages contained in this repository are already available as snap packages. And maybe you don't like snaps? :)

## Building the packages

To build a package, run the `build` script with a package folder:

    ./build-single-deb packages/<package>

To build intellij-idea-ultimate for example use:

    ./build-single-deb packages/intellij-idea-ultimate

## Why this was written

I hate manually downloading, extracting and moving the `*.tar.gz` from the
JetBrains website to get an IDE update. Unfortunately JetBrains does not have a
Debian repository.

There are already [existing](https://launchpad.net/~mmk2410/+archive/ubuntu/intellij-idea)
 [PPAs](https://launchpad.net/~vantuz/+archive/ubuntu/jetbrains).
However, none have continuous delivery or provide a wide range of JetBrains products.

---

Maintained by Jonas Gröger. Automatically updated by [TravisCI](https://travis-ci.org/JonasGroeger/jetbrains-ppa).
