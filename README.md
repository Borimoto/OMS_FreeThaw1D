# OMS_FreeThaw1D

Freezing and thawing of soils affect a wide range of biogeochemical and hydrological ([Walvoord and Kurylyk, 2016](https://doi.org/10.2136/vzj2016.01.0010); [Schuur
et al., 2015](https://doi.org/10.1038/nature14338)) processes and interact with engineered structures in cold regions. This foundational importance together with the vast extent of cold regions globally makes the simulation of freezing and thawing soil an important and well-researched topic ([Streletskiy et al., 2019](https://doi.org/10.1088/1748-9326/aaf5e6); [Walvoord and Kurylyk, 2016](https://doi.org/10.2136/vzj2016.01.0010); [Harris et al., 2009](https://doi.org/10.1016/j.earscirev.2008.12.002)). The interest in understanding and anticipating the consequences of permafrost thaw driven by anthropogenic climate change has added additional urgency.

Studying frozen soil can be done at different timescales. At short timescale, the latent heat of fusion of water determines a time-lag in the cooling and warming of the soil thus affecting the surface heat fluxes. Studies have shown that proper frozen soil scheme help improve land surface and climate model simulation ([Viterbo et al., 1999](https://doi.org/10.1002/qj.49712555904); [Smirnova et al., 2000](https://doi.org/10.1029/1999JD901047)). 
On the other hand, permafrost evolution is characterized by a long timescale and its evolution is manly controlled by climate change. Permafrost degradation has significant impact on the ecosystems and on the social and economic life in cold regions ([Bao et al., 2016](https://doi.org/10.1002/2015JD024451))
Therefore, it is desirable to have a numerical model that can efficiently simulate frozen soil at both short timescale and long timescale.
At present, a common problem of physical-based frozen soil model concerns the treatment of the nonlinear behavior of the energy and enthalpy as function of temperature, water content and other governing variables. Because of this nonlinearity, the model may fail to compute the correct solution, or a short time step must be chosen leading to an increase of the computational cost.

`FreeThaw1D` model solves the so called enthalpy - or conservative - formulation. The novelty regards the use of the nested Newton-Casulli-Zanolli (NCZ) algorithm, ([Casulli and Zanolli](https://doi.org/10.1137/100786320)) to linearize the nonlinear system resulting from the approximation of the governing equation. Using the enthalpy formulation and the NCZ algorithm the convergence of the solver is guarateed for any time step size. This is a key feature since the integration time step can be choosen accordingly to the time scale of the processes to study, from seconds to days.


![Alt text](Jupyter_Notebook/image/frozensoil.jpg?raw=true "Title")

# Website
- [GEOframe](http://geoframe.blogspot.com/)
- [NSERC PermafrostNet](https://www.permafrostnet.ca/)

# OMS
`FreeThaw1D` is written in Java,  works under the [`OMS3`](https://abouthydrology.blogspot.com/2017/08/oms-3-essentials.html)(David et al., 2013) framework and is part of the `GEOframe` system ([Formetta et al., 2014](https://doi.org/10.1016/j.envsoft.2014.01.019), [Bancheri, 2017](http://eprints-phd.biblio.unitn.it/2679/)). It was produced as part of the Ph.D. work by Niccolò Tubini.
Here you can find the [source code](https://github.com/geoframecomponents/FreThaw1D)

GEOframe programs run on Java 8. The OMS project can be run either within the [OMS v3 Console](https://alm.engr.colostate.edu/cb/wiki/16961) or by using [Docker](https://hub.docker.com/r/omslab/oms/).

# OMS v3 Console
- As first step it is necessary to install the JDK 8. There are two options:
  - Download open JDK 8 LTS from https://adoptopenjdk.net/
  - Install it
  - find the JAVA_HOME
    - on Windows open a terminal and run `where javac`
    - on Mac open a terminal and run `where java`
  or
  - install Anaconda
  - create the environment geoframe_vicenza. This install a JDK 8 on your laptop. To create an enviroment open the Anaconda prompt
    - open Anaconda prompt
    - set in the folder containing the file *geoframe_vicenza.yaml*
    -  `conda env create -f geoframe_vicenza.yaml`
    -  `conda activate geoframe_vicenza`
  - find the JAVA_HOME
    - from the Anaconda prompt `echo JAVA_HOME`
    
- Download the OMS v3 Console version 3.6.28 from  https://alm.engr.colostate.edu/cb/wiki/16961
- Unzip the OMS Console and 
  - on Windows run the `console.bat` file
  - on Mac or Linux open a terminal and execute `./console.sh &`

- In the console setting, select the panel Run and set the Java path to the previously installed JDK. The Java path can be

  

# Acknowledgements

-  Niccolò Tubini, Stephan Gruber, Riccardo Rigon developed the theoretical aspects of the model (Authors). 
-  Niccolò Tubini, Riccardo Rigon designed the first version of the code (Authors)
-  Niccolò Tubini implemented and deployed it (Authors)
-  Riccardo Rigon and Stephan Gruber provided financial support
-  Niccolò Tubini and Riccardo Rigon wrote the documentation in the Notebooks
-  Niccolò Tubini was partially supported by a Ph.D. grant by [DICAM-UniTrento](https://www.unitn.it/dricam/) and by the  [NSERC PermafrostNet](https://www.permafrostnet.ca/)  project.
-  We thank Professor Vincenzo Casulli and Professor Michael Dumbser for their fruitful discussions on the numerical aspects of the work. 
