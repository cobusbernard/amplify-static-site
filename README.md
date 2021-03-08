# amplify-static-site
Demo Hugo site for demo'ing AWS Amplify. To create the skeleton app, use the following:
~~~
# Go to user's home directory
cd ~

# Create new Hugo project skeleton
hugo new site amplify-static-site

# Go to the new project folder
cd amplify-static-site

# Initialize the Hugo project directory as a GIT Repo
git init

# CD into the themes folder and clone the Hugo learn theme as a GIT sub-module
cd themes
git submodule add https://github.com/matcornic/hugo-theme-learn.git

# Return to the parent Hugo project folder
cd ..

# Rewrite the config file - this replaces the content with the following
cat <<EOT > config.toml
baseURL = "http://example.org/"
languageCode = "en-us"
title = "Unicorn Inc - Smart Factories Workshop"
theme = "hugo-theme-learn"
uglyurls = true
EOT

# Create an index page
hugo new --kind chapter _index.md

# Replace the content of the index page
cat <<EOT > content/_index.md
--- title: "Unicorn Inc - Smart Factories Workshop"
draft: false
weight: 0
pre: "<b>0. </b>"
---
### Unicorn Inc - Smart Factories Workshop
![Unicorn Inc Logo](_/images/__unicorn__-__inc__.__png__?__classes__=__border_) 

Welcome to Unicorn Inc - Smart Factories Workshop.
EOT

# Create the images directory in the static folder
mkdir -p static/images # wget the image and save to images/unicorn-inc.png (Apply as one line)
wget -O static/images/unicorn-inc.png https://d1.awsstatic.com/events/GameDay250.96690fe1668e09bf9a5012de5dd78b6e9293b25f.png

hugo
hugo server --port 8080
~~~
