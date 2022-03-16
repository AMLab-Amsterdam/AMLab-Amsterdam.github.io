# Build Instructions

This website uses the [Jekyll](https://jekyllrb.com/) static site generator, which is written in Ruby. To build this website, perform the following steps

1. Ensure that Ruby is installed ([Instructions](https://www.ruby-lang.org/en/documentation/installation)). 

    *Note for MacOS users:* We recommend that you do not modify the system-installed Ruby version, which may break scripts required by the OS. Instead install a copy of Ruby via [Homebrew](https://brew.sh/) or [Macports](https://www.macports.org/).

2. Ensure that you have the latest bundler version installed. On MacOS/Linux this can be done by typing:
```
gem install bundler
```
You may need to run as root using `sudo` at this step, depending on your setup. 

3. Install [Jekyll](https://jekyllrb.com/) and other packages needed to build this website by invoking:
```
bundler config set --local path 'vendor/bundle'
cd /path/to/../AMLab-Amsterdam.github.io
bundler install
```
This will install all required packages into the subdirectory `vendor/bundle` of your working directory.

4. You should now be able to view the website by executing the following command:
```
bundler exec jekyll serve
```
This will start a webserver that allows you to view the website by accessing `http://127.0.0.1:4000` in your browser.

# Adding Your Personal Information 

1. Clone the repository and checkout a new branch.
```
git clone git@github.com:AMLab-Amsterdam/AMLab-Amsterdam.github.io.git
```
2. Add the following files (for details see below):
- A description file ```./_people/FirstnameLastname.md```
- A profile picture ```./assets/img/FirstnameLastname.[jpg/png]```
- Optimally, a bibliography file ```./_bibliography/FirstnameLastname.bib```

3. Commit and push your changes to your newly created branch.

4. Open a pull-request on Github.


## Description file

The description file ```FirstnameLastname.md``` takes the following format:

```
---
layout: person-page
name: John Doe
role: PhD candidate
supervisors: [first supervisor, second supervisor, ... ]
one_liner: Geometric deep learning and graph neural networks
bib_file: JohnDoe
lab: AMLab
redirect: 
description: |
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

img: assets/img/JohnDoe.jpg
img_promo: 
personal_page: https://johnswebsite.doe
scholar_userid: XXXXXXXXXXXX
github_username: johns_github
twitter_username: johns_twitter
category: phd 
---

{% include person_page.html person=page %}
```

** ------- Add description of possible roles and categories -------**

# Image
Add a profile picture ```./assets/img/FirstnameLastname.[jpg/png]``` (please keep the file size reasonably small). Make sure the file name follows the naming conventions and matches the image file name in your description file.

# Bibliography file

```
@InProceedings{bibif, 
  title =    { ... },
  author =       { ... },
  booktitle =    { ... },
  ...
  abstract =     { ... },
  pdf =      { <Link to PDF> },
  code = { <Link to github/code> },
  abbr={ <Abbreviation of conference/journal, e.g. ICML> }
}
```
Make sure the file name follows the naming conventions and matches the bibliography file name in your description file.

# Theme 

The website uses [al-folio](https://github.com/AMLab-Amsterdam/AMLab-Amsterdam.github.io), a simple, clean, and responsive Jekyll theme for academics. The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
