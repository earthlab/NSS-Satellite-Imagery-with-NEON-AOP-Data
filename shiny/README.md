## Run the Shiny app in RStudio

Clone the Shiny App repository 

```
git clone https://github.com/cyverse-gis/neon-shiny-browser
```

Change your RStudio working directory to the location of the app:

```
getwd()
setwd("~/neon-shiny-browser")
```

Load Shiny and run the app (note - the app has numerous spatial dependencies which must also be installed if running on a local machine, this can take some time).

```
library(shiny)
runApp()
```

<p align="center"><img src='https://github.com/cyverse-gis/neon-science-summit-2019/blob/master/gif/RStudio_NEON_Shiny.gif?raw=true' width='750'></p>

## Run Shiny app in CyVerse

Select the NEON-Shiny-Browser App in CyVerse.

Browse and download data to the Data Store.

View downloaded data in your home folder `/analyses`

## Run Shiny app with Docker locally or on a Virtual Machine

Download from DockerHub:

```
docker pull cyversevice/shiny-geospatial:neon-shiny-browser
```

Or just run the app:

```
docker run -it --rm -p 3838:3838 -e REDIRECT_URL=http://localhost:3838 -v ~/NEON_Downloads:/NEON_Downloads cyversevice/shiny-geospatial:neon-shiny-browser
```
