# Build Instructions

This website uses the [Jekyll](https://jekyllrb.com/) static site generator, which is written in Ruby. To build this website, begin by performing 

1. Ensure that Ruby is installed ([Instructions](https://www.ruby-lang.org/en/documentation/installation)). 

*Note for MacOS users:* We recommend that you do not modify the system-installed Ruby version, which may break scripts required by the OS. Instead install a copy of Ruby via [Homebrew](https://brew.sh/) or [Macports](https://www.macports.org/).

2. Ensure that you have the latest bundler version installed. On MacOS/Linux this can beµ done by typing:
```
gem install bundler
```
You may need to run gem as root using `sudo` at this step, depending on your setup. 

3. Install [Jekyll](https://jekyllrb.com/) the packages needed to build this website by invoking:
```
bundler config set --local path 'vendor/bundle'
bundler install
```

4. You should now be able to view the website by executing the following command:
```
bundler exec jekyll serve
```
This will start a webserver that allows you to view the website by accessing `http://127.0.0.1:4000` in your browser.

