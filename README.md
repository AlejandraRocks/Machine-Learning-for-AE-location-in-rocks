
# Machine Learning for Acoustic Emission (AE) Localization in Rock

My doctoral thesis is framed within the study of Acoustic Emission waves as precursors to major earthquakes. Consequently, I have chosen to focus this practical work on exploring potential applications for my research. Acoustic Emissions (AE) are stress waves produced by the sudden redistribution of internal stress in materials caused by changes in internal structure. These changes in internal structure can include the initiation of cracks within rocks, crack opening, fracturing, etc. Most sources of AE are associated with damage; therefore, accurately locating these emissions is commonly used to predict material failure

![image](https://github.com/AlejandraRocks/-Machine-Learning-para-localizar-Emisi-n-Ac-stica-EA-en-Rocas-/assets/69768600/0dc72c51-48af-4cb4-85ee-7edcc8a97122)

To locate the sources of Acoustic Emission (AE), methods similar to those in seismology are commonly employed, with the most utilized being the wave travel time inversion methods (Geiger 1912; Aki and Lee 1976). These methods revolve around the goal of solving the nonlinear relationship between travel time and hypocenter location, requiring predefined constant velocity models of the medium (Richards et al. 2006). In the specific case I am interested in, which involves locating AE in rocks, the task becomes highly challenging when the rock exhibits anisotropy. This necessitates tomographic inversion of the sample to establish a velocity model, followed by an iterative inversion for location, which is computationally expensive.

In this practical work, I will employ Machine Learning methods to locate the x, y coordinates using only the arrival times of the P-wave, completely bypassing the complexity of establishing velocity models and the iterative inversion process

# **1. Data Adquistion**

Due to the ongoing pandemic, I have not been able to conduct experimental tests on my samples. Therefore, I decided to search for Acoustic Emission rupture test data in articles where the data was made available. This is the case with este enlace. The experimental setup consists of a loading frame, an AE recording system, and the rock sample assembly (Fig. 1a). The experimental setup utilized a granite rock sample with dimensions of 218 mm x 218 mm x 200 mm, featuring a vertical plane inclined at 45 degrees at the center (simulating a laboratory fault). Tension is then applied to the rock to induce lateral right shear failure in the laboratory fault at a normal failure stress of 10 MPa. Eleven piezoelectric sensors of Glaser type are attached to the rock sample on the north (N) and west (W) sides. These sensors are directly connected to the digitizer, which is linked to the computer recording the AE signals.

<img width="707" alt="montaje" src="https://github.com/AlejandraRocks/-Machine-Learning-para-localizar-Emisi-n-Ac-stica-EA-en-Rocas-/assets/69768600/495ff562-0cd7-4c70-991c-2deb2b49f521">

56 tests were conducted simulating an AE source by breaking a 0.7 mm diameter pencil lead at known locations on the fault surface (Hsu et al. 1978), prior to the actual fault rupture test. These events were distributed across the entire fault surface to ensure good spatial coverage. The arrival time of the P-waves was estimated using the Akaike Information Criterion (AIC) criterion. Below is an example of how the signal was received at each sensor and the picking of the P-wave.


<img width="595" alt="figurejemplo" src="https://github.com/AlejandraRocks/-Machine-Learning-para-localizar-Emisi-n-Ac-stica-EA-en-Rocas-/assets/69768600/4ee4460a-473d-495e-a22c-0510cdd3baeb">

The 56 pencil lead breakage tests were conducted on the fault surface. Since the Y-axis remains constant, a new coordinate system was established with X and Z axes.

<img width="633" alt="descargar" src="https://github.com/AlejandraRocks/-Machine-Learning-para-localizar-Emisi-n-Ac-stica-EA-en-Rocas-/assets/69768600/3cdfecb7-b22a-498c-98b7-9854ba3baa46">











