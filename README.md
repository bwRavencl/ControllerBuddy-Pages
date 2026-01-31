# ControllerBuddy-Pages

## 📖 Description

This repository hosts the source code behind the official ControllerBuddy homepage.  
To learn more about ControllerBuddy, click [here](https://controllerbuddy.org) to visit the site.

## 🛠️ Local Testing

To test the site locally, follow these steps:
1. Install [Ruby](https://www.ruby-lang.org) and [Bundler](https://bundler.io)
2. Configure Bundler to install gems locally:
    ```sh
    bundle config set --local path 'vendor/bundle'
    ```
3. Install the required gems:
    ```sh
    bundle install
    ```
4. Serve the site locally:
    ```sh
    bundle exec jekyll serve --baseurl=""
    ```
5. Open your web browser and navigate to `http://localhost:4000` to view the site.

## ⚖️ License

[Attribution-NonCommercial-NoDerivatives 4.0 International](LICENSE)
