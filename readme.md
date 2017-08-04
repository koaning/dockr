# dockr 

This repo contains a sufficient starting point to launch a shiny server in a docker container. 

# to run locally

```
docker build . -t tempname
docker run -p=3838:3838 tempname
```

# contents 

The project contains three demo folders. These are three independant shiny apps that will be served. 

The `index.html` file links to these three projects. If you want to add more feel free to add folders and ensure that the index page is changed to reflect that. 

The `shiny-server.sh` file starts the shiny server and is passed to the docker file. 

The `Dockerfile` contains all the install instructions required for the container. If you play close attention you'll notice this one line:

```
R -e "install.packages(c('shiny', 'rmarkdown'), repos='https://cran.rstudio.com/')" && \
```

If you ever want to add packages to it you can do that from here. 

# shout outs 

This work is a slight modification from [this repo](https://github.com/rocker-org/shiny) by Winston Chang. 