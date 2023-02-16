# CS421-project1: Automated Eye Tracking Data Correction

## Abstract ##
This project is a replication of the code discussed in the “Algorithms for the automated correction of vertical drift in eye-tracking data” research paper (Carr et. al).  The ten algorithms explored in my project attempt to address and correct the common eye-tracking research problem of vertical drift: the progressive displacement of fixation registrations of the vertical axis that results from a gradual loss of eye-tracker calibration over time.  The goal of this project was to run the 10 algorithms (attach, chain, cluster, compare, merge, regress, segment, split, stretch, warp) and visualize how they perform against noise, slope, shift, within-line regression, and between-line regression error, as modulated by a parameter that determines error magnitude.

## Results ##
After adding the additional algorithms, I wrote additional functions to simulate the slope, shift, within-line regression and between-line regression errors.  I ran 100 trials of each with varying radial error.  

The researchers originally found that “a method based on dynamic time warping offers great promise, but also found that some algorithms are better suited than others to particular types of drift phenomena and reading behavior”.

As visualized in the below graphs, I found CHAIN to be most resistant to noise, with a mean accuracy of about 96%, WARP, CLUSTER, SPLIT, STRETCH, & MERGE to be most resistant to slope with a mean accuracy of about, WARP, CLUSTER, SEGMENT, SPLIT, STRETCH, & MERGE to be most resistant to shift with a mean accuracy of about %, **algs** to be most resistant to within-line regression with a mean accuracy of about %, and **algs** to be most resistant to between line regression with a mean accuracy of about %.

  <p align="center"> Both my results and the original results use this color-coded key: </p>
  <p align="center"> <img width="208" alt="key" src="https://user-images.githubusercontent.com/30237570/218871804-facadd41-e215-464a-be63-a0f7cfa08f6c.png"></p

NOISE: expected, actual, corrected, stats
<p>
  <img width="200" alt="expected_noise" src="https://user-images.githubusercontent.com/30237570/218874781-4bd4e9a1-001e-41ff-97f6-a532692decff.png">
  <img width="200" alt="actual_noise" src="https://user-images.githubusercontent.com/30237570/218871535-9227d63e-28c8-4034-b606-78d8504525cd.png">
  <img width="200" alt="corrected_noise" src="https://user-images.githubusercontent.com/30237570/218871545-2719d38c-432b-4a1b-97aa-47c906b15ec5.png">
  <img width="200" alt="noise_stats" src="https://user-images.githubusercontent.com/30237570/218918247-a177b4af-8944-46bc-823c-b0fad9ba47c0.png">
</p>

SLOPE: expected, actual, corrected, stats
<p>
  <img width="200" alt="expected_slope" src="https://user-images.githubusercontent.com/30237570/218874809-db493790-1243-486c-b140-be31024fc559.png">
  <img width="200" alt="actual_slope" src="https://user-images.githubusercontent.com/30237570/218874242-fa0d973e-92bd-46b0-859a-3ec4f4acafd2.png">
  <img width="200" alt="corrected_slope" src="https://user-images.githubusercontent.com/30237570/218874276-38c7df7c-2504-4cf7-a432-984135cc72a5.png">
  <img width="200" alt="slope_stats" src="https://user-images.githubusercontent.com/30237570/218874287-3ec2f253-6007-469d-88c9-5fbaab4d05b1.png">
</p>

SHIFT: expected, actual, corrected, stats
<p>
  <img width="200" alt="expected_shift" src="https://user-images.githubusercontent.com/30237570/218874831-5d818bf3-4cca-401b-8ac6-8ef7e45adf6c.png">
  <img width="200" alt="actual_shift" src="https://user-images.githubusercontent.com/30237570/218874350-54675674-6021-4ec4-a4ba-ef9fff9ea7df.png">
  <img width="200" alt="corrected_shift" src="https://user-images.githubusercontent.com/30237570/218874387-674a1e31-2780-45ea-abed-445f61ca5e3f.png">
  <img width="200" alt="shift_stats" src="https://user-images.githubusercontent.com/30237570/218874399-715a5408-6581-426c-ade0-68a01083df0d.png">
</p>

WITHIN-LINE REGRESSION: expected, actual, corrected, stats
<p>
  <img width="200" alt="expected_within" src="https://user-images.githubusercontent.com/30237570/218874898-bfb12c26-e838-48b9-987c-130aba0b6abc.png">
  <img width="200" alt="actual_within" src="https://user-images.githubusercontent.com/30237570/219135130-ced5bee4-de87-4a10-b574-8e54c7cb9c6a.png">
  <img width="200" alt="corrected_within" src="https://user-images.githubusercontent.com/30237570/219190620-4e619f27-08af-46de-8a31-f8da7c25d8f1.png">
<img width="200" alt="within_stats" src="https://user-images.githubusercontent.com/30237570/219226475-d8c89813-3ed0-48fc-93a5-fd99f586b21a.png">

</p>

BETWEEN-LINE REGRESSION: expected, actual, corrected, stats
<p>
    <img width="200" alt="expected_between" src="https://user-images.githubusercontent.com/30237570/218874922-b9291b1c-296a-4516-99b1-46b0c25c58c6.png">
    <img width="200" alt="actual_between" src="https://user-images.githubusercontent.com/30237570/219135168-a786ace5-077a-46a0-8565-27dc863da598.png">
    <img width="200" alt="corrected_between" src="https://user-images.githubusercontent.com/30237570/219135181-3f02cb56-6645-41ce-a699-1bd8207e30a8.png">
<img width="200" alt="between_stats" src="https://user-images.githubusercontent.com/30237570/219250971-0ece4bba-508c-4cd2-be83-81e6cd25682e.png">

</p>

## Discussion ##

Comparison of my results (left) to initial study results (right):

NOISE:
<p>
  <img width="400" alt="mynoise" src="https://user-images.githubusercontent.com/30237570/218918210-747cdcd4-10b9-44b6-87b2-a5f0c2c791fd.png">
  <img width="400" alt="noise" src="https://user-images.githubusercontent.com/30237570/218870730-c16cf190-f044-4dc1-a4e4-278a072cffcc.png">
</p>

SLOPE:
<p>
  <img width="400" alt="myslope" src="https://user-images.githubusercontent.com/30237570/218874480-636133a6-927d-4fe6-a54a-2965f200e5d6.png">
  <img width="400" alt="slope" src="https://user-images.githubusercontent.com/30237570/218870748-011c6c30-3647-4f77-97e8-6e79e6bcea72.png">
</p>
  
SHIFT:
<p>
  <img width="400" alt="myshift" src="https://user-images.githubusercontent.com/30237570/218874518-69cd30b3-fd6d-45c4-a33e-0787c52453a9.png">
  <img width="400" alt="shift" src="https://user-images.githubusercontent.com/30237570/218870763-4debf349-bc66-4f88-8a43-1f1300b93f94.png">
</p>

WITHIN-LINE REGRESSION:
<p>
 <img width="400" alt="mywithin" src="https://user-images.githubusercontent.com/30237570/219226438-e1ccd4a3-2124-41f0-98cf-aba684442f70.png">
<img width="400" alt="within" src="https://user-images.githubusercontent.com/30237570/218870782-f8dd5dea-ba52-46c6-8186-f729fdb4d88b.png">
</p>

BETWEEN-LINE REGRESSION:
<p>
  <img width="400" alt="mybetween" src="https://user-images.githubusercontent.com/30237570/219250944-491a7129-e12d-41ff-9bdc-dec6f149a349.png">
<img width="400" alt="between" src="https://user-images.githubusercontent.com/30237570/218870794-7f11d4ef-848f-4b2c-8021-fd0e6cb54d99.png">
</p>

## Extensions ##


## References/Acknowledgements ##
<p>Naser Al Madi</p>
<p>https://www.educative.io/answers/how-can-we-use-the-random-triangular-method-in-python</p>
<p> https://interactivechaos.com/en/python/function/randomtriangular </p>
