# How to deploy the website

## #1. Install development tools.

* Required OS: `Ubuntu 16.04` or `Bash on Ubuntu on Windows`
* Steps to do:
    * `sudo apt-get update`
    * `sudo apt-get install ruby ruby-dev make build-essential`
    * `gem -v`
    * `sudo gem install jekyll bundler`

## #2. Build dependencies

* Required Node.js v6.9.1 and NPM v3.10.8 or newer
* Steps to do:
    * `cd path/to/website/project`
    * `npm run install`
    * `bundle install --path ./gem_modules/bundle`

## #3. Build project

* Build: `npm run build`

## #4. Publish project

* Deploy: `npm run deploy`
* Publish: `git add . && git push origin gh-pages`

# gh-pages as a project submodule

```bash
> git submodule add -b gh-pages --name dist --force https://github.com/vunb/kites.git dist
> git submodule update --remote
```

# References

* [Install `jekyll` 3.7.3 on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-set-up-a-jekyll-development-site-on-ubuntu-16-04)
* `gem -v` prints `2.5.2.1` or newer.
