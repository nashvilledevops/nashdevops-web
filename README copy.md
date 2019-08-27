# nashvilledevops.github.io
NashDevOps Web Site

This is the official project to support the NashDevOps.com Website

NashDevOps is a group for curious individuals that are interested in collaborating with other like-minded people that have passion for the DevOps Culture. This includes Technical Practitioners & IT Business Leaders involved with Digital & IT Transformation initiatives.

This project is open sourced and all are invited to contribute.

Join Us at a Meetup:
- [NashDevOps Meetup](https://www.meetup.com/NashDevOps/)

Visit Us on the Web:
- [NashDevOps Website](https://nashdevops.com)


## Getting Started

TLDR; 
NashDevOps.com is a static site build using Jekyll and hosted via GitHub Pages. This Jekyll project utilizes Docker to deliver a consistent build and server environment to support development. 

### Learn About Jekyll

See Documentation:
- [Jekyll](https://jekyllrb.com/)
- [Jekyll - How it Works](https://jekyllrb.com/docs/usage/)

### Learn About GitHub Pages

See Documentation:
- [GitHub Pages](https://pages.github.com/)
- [GitHub Pages - Custom Domain](https://help.github.com/en/articles/using-a-custom-domain-with-github-pages)
- [GitHub Pages - Configure HTTPS](https://help.github.com/en/articles/securing-your-github-pages-site-with-https)

### Install Docker

See Documentation:
- [Docker](https://www.docker.com/)
- [Docker - Install](https://docs.docker.com/install/)

### Pull the Official Jekyll Image

See Documentation:
- [DockerHub](https://hub.docker.com/)
- [Jekyll Docker Image](https://hub.docker.com/r/jekyll/jekyll)
- [Jekyll Docker Image - ReadMe](https://github.com/envygeeks/jekyll-docker/blob/master/README.md)

Example:

    # Docker Pull Command
    docker pull jekyll/jekyll

    # Verify Docker Images
    docker images

### Clone the Repository

Example:

    # Git Clone Project
    git clone git@github.com:nashvilledevops/nashvilledevops.github.io.git

### Building the Project (via Docker)

The following commands will build the Jekyll Project using the Standard Official Docker Image (jekyll/jekyll) which includes a default set of "dev" packages, along with Node.js, and other stuff that makes Jekyll easy. It also includes a bunch of default gems that the community wishes us to maintain on the image.

Note: When you run the docker command below to build the project you will need to be at the root of the project directory as the present working directory (i.e. $PWD) is mounted as a volume within the running container.

Example:

    # Set the Jekyll Version
    export JEKYLL_VERSION=3.8.6

    # Run Docker to Build our Jekyll Project
    docker run --rm --volume="$PWD:/srv/jekyll" -it jekyll/jekyll:$JEKYLL_VERSION jekyll build


### Serving the Project (via Docker)

The following commands will serve the Jekyll Project using the Standard Official Docker Image (jekyll/jekyll) at http://0.0.0.0:4000 

Note: When you run the docker command below to serve the project you will need to be at the root of the project directory as the present working directory (i.e. $PWD) is mounted as a volume within the running container.

Example: 

    # Set the Jekyll Version
    export JEKYLL_VERSION=3.8.6

    # Run Docker to Serve our Jekyll Project
    docker run --rm --volume="$PWD:/srv/jekyll" -p 4000:4000 -it jekyll/jekyll:$JEKYLL_VERSION jekyll serve


### Developing the Project (via Docker)

Once the docker container is running you can visit the site at http://0.0.0.0:4000 (see above) and can develop against the Jekyll Project locally and refresh your browser to see the changes.

### Jekyll Project Structure

Here is a quick overview of the custom Jekyll Project:

    /
        
        /_includes         # Partials such as head, header, foot, footer used in layouts
            foot.html
            footer.html
            head.html
            header.html
        
        /_layouts          # Common Layouts (e.g. page, post, slide) used throughout the site
            cover.html
            default.html
            landing.html
            page.html      # e.g. Used by Common Pages
            post.html      # e.g. Used by Blog Posts
            scroll.html 
            slide.html     # e.g. Used by Slides (reveal.js)

        /_pages            # Custom Static HTML Pages (e.g. About, Blog, Sponsors) used in the site
            /about
                index.html               # About Us Page
                brian-hooper.html        # Core Contributor Profile Page
                julian-bankston.html     # Core Contributor Profile Page
                miles-maddox.html        # Core Contributor Profile Page
                nick-wallace.html        # Core Contributor Profile Page
                steve-stewart.html       # Core Contributor Profile Page

            /blog
                index.html               # Blog Page (latest posts)
            /search
                index.html               # Search Page (uses search.json data)
            /sponsors
                index.html               # Sponsors Page
                gadgetry.html            # Sponsor Profile Page
                redhat.html              # Sponsor Profile Page
                shadowsoft.html          # Sponsor Profile Page


        /_posts            # Custom Blog Posts (e.g. Markdown / HTML)

        /_site             # Site Directory for the Build

        /_slides           # Custom HTML Slide Presentations (e.g. RevealJS)

        /assets            # Site Assets (e.g. images, js scripts, css styles, js modules)

        /templates         # Example Static HTML Page Templates for _pages Directory

        _config.yml        # Jekyll Config
        404.html           # Site 404 Error for Github Pages
        Gemfile            # Jekyll Gemfile
        index.html         # Site Entrypoint 
        LICENSE            # Mozilla Public License 2.0 
        README.md          # THE FILE YOU ARE READING NOW
        search.json        # Supports the Search Functionality at /search

