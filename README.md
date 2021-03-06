# Marian Website

The website is build with Jekyll - a static site generator.
The content is created and updated on branch `jekyll`, then the static pages
are generated with Jekyll and stored in branch `master`. Please **do not update
files directly in `master`**.


We use custom theme, which is not supported by automatic GitHub Pages
generator. The static files have to be generated locally before deploying.


## Local build

If cloning the repository for the first time, download the remote branch:

    git clone https://github.com/marian-nmt/marian-nmt.github.io
    cd marian-nmt.github.io
    git fetch origin jekyll
    git checkout jekyll

To build the website locally you need to install `ruby` with gem `bundler`.

On Ubuntu 16.04 you can run:

    [sudo] apt-get install ruby-dev
    [sudo] gem install bundler

Then, install gem dependencies:

    bundle install

Finally, build the website (it will be generated in `_site` folder) and run a
local development server:

    make run

The website should be available at `http://127.0.0.1:4000`.

### Documentation

Documentation has to be updated manually:

    make update-docs

This requires `doxygen` to be installed.

### Pages with command-line options

Pages with command-line options for Marian tools have to be updated manually:

    rm docs/cmd/marian*.md
    make -B update-cmds

This compiles Marian, so GPU is required.

### Logos

Put a logo image into `assets/logos/` and update `_data/logos.yml`.  Use a PNG
image with transparent background.


## Deployment

To update the content of website it should be enough to edit the relevant
markdown files.
When all updates have been made and the website can be still generated locally
*without errors*, you can commit and deploy your changes by running:

    bash -v ./commit-and-deploy.sh

The script commit all changes for you with default commit message, but it is
always better to commit changes on your own beforehand and set a relevant
message.


## Tag reference

| Tag | Description |
| --- | --- |
| `[Text](/permalink/)` | An active link to another subpage of the website identified by its permalink. |
| `{% github_link <repository>/<path/to/file> %}` | An active link to a file/directory `<path/to/file>` in the given repository, i.e. `http://github.com/marian-nmt/<repository>/tree/master/<path/to/file>`. |
| `{% github_link "clickable text" <repository>/<path/to/file> %}` | An active link to a file/directory `<path/to/file>` in the given repository with `clickable text`. |
| `[Text](/link){:target="_blank"}` | Opens the linked document in a new window or tab. |
| `$$ x_{i}^{j} $$` | A LaTeX mathematical formula. |
| `[Text](/path/to/an/image){:.no-lightbox}` | Disable the automatic image box. |
