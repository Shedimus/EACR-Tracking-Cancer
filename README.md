# EACR Tracking Cancer Poster
This repository serves as a reference for the poster originally presented by myself at the EACR Tracking Cancer conference in Barcelona, 2019. 

All of the data and code required to produce a final pdf version of the poster is included here if you so wish. Please also feel free to modify or copy poster layouts for your own needs too. 

Thanks for looking! Please feel free to give me feedback or requests for changes in the [issues](https://github.com/Shedimus/EACR_posterdown/issues) page. I am collaborating on the real **posterdown** package so there is a chance this format and template may be reproducible through that in the near future.

## Instructions:

To reproduce the poster as seen you will need to make sure you have the appropriate packages and LaTeX distibutions installed. Due to some custom formatting constraints (Figure 1 mostly) I had to modify the original **posterdown** package (which I thoroughly recommend by the way). Documentation for the **posterdown** package can be found at devtools::install_github("brentthorne/posterdown") if you want to make your own poster from scratch. 

You can install and use **EACR_posterdown** from github using the `devtools` package as seen below. It is definitely recommended to use RStudio and open the .Rproj file once this repository has been cloned. This will ensure all the files are in the right place and the working directory is set.

    ```r
     devtools::install_github("Shedimus/EACR_posterdown")
    ```

### If you have never used RMarkdown

1. Install `devtools` package

    ```r
    install.packages("devtools")
    ```

2. Install `posterdown` from github repo

    ```r
   devtools::install_github("Shedimus/EACR_posterdown")
    ```

3. Install `tinytex`Latex libraries:

    ```r
    tinytex::install_tinytex()
    ```

    _**NOTE** This will take some time to load the LaTex Packages but is the best option (in my opinion) for keeping your Latex library as small as possible. After the first download of these libraries you will not need to do this again. To confirm that Tinytex is properly installed use: `tinytex:::is_tinytex()` and you should get a value of `TRUE` in the console._
    
    _**NOTE** If you have conflicting versions of Latex (i.e. tinytex and MacTex), you could have problems rendering your poster. You may need to uninstall all versions, then start over by installing posterdown and tinytex from scratch._ 
    
### Reproduce the Poster:
1. Open the project file (EACR-Tracking-Cancer.Rproj) in RStudio. 

2. Open the poster RMarkdown file and ensure you have the required packages installed:
    
    ```r
    install.packages("readr")
    install.packages("kableExtra")
    install.packages("survival")
    install.packages("survminer")
    install.packages("pROC")
    ```
 3. Knit the RMarkdown file, the initial knit will be significantly slower than subsequent ones:  
    a. The **posterdown** template requires _quite a few_ LaTeX packages that will be installed on first run.  
    b. The RMarkdown will also be a _little_ slower the first time as the bootstrap resampling is done. This is cached for later runs.  

4. Enjoy the outputted pdf poster in the correct size.

5. Play around with formatting and layout at will. 

If you want to make drastic layout changes the .tex file can be found in the **EACR_posterdown** install directory at inst/rmarkdown/templates/posterdown_pdf/resources. Editing this will change how the final document is formatted through **posterdown**.
