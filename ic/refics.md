# REFICS: Assimilating Data-Driven Paradigms Into Reverse Engineering and Hardware Assurance on Integrated Circuits

## Generally Interesting pointers:
- They highlight the objective mismatch of deep learning VS practical requirements of IC image analysis. 'In contrast, errors in a few pixels, typically, do not result in severe consequences in the image analysis domain. Similarly, there are several image segmentation evaluation metrics, such as the Intersection-over-Union (IoU) and Structural Similarity Index Measure (SSIM), that are capable of evaluating segmentation based on shapes but are inherently incapable of incorporating electrical connectivity information into account. They lead to short-circuits or modification of the intended functionality resulting in significant inflation of RE process time frame to account for manual error resolution'
- An open source synthetic SEM image dataset was proposed, called **REFICS**. Link to dataset not yet found.
- They breakdown the different sources of noise that affect imaging quality. These are split into predictable and random interactions.

## Sources of noise
### Predictable or possible-to-model interactions
- Beam interaction: SEM imaging works on the basis of detecting secondary emissions of electrons from the IC material. There can be variations in the instantaneuos electron count (not equal to the average), which causes a phenomenon commonly known as *shot noise*. This can be modelled by a Poisson process. A solution to this is to increase the dwelling time of the SEM imaging process.
- Beam drift: fluctuations in the scanning beam and mechanical creep of the staging platform can cause the beam spot to move from the intentended position on the IC material. This can cause problems when e.g. expected beam spot is on background but true beam spot drifts to the metal line. This process can usually be modelled with GAussian distribution.
- Die Warpage: incremental removal of IC material during delayering process can cause mechanical stress, as the substrate supporting the material is removed. This causes some perspective distortion in the final image.
- Feature dimension and proximity: complex geometries and also structures placed close together might not be imaged clearly due to insufficient resolution or magnification of the SEM.
- Flicker noise: a common phenomenon during semiconductor operations, caused by release of electrons from electron holes. Even though not operational during imaging, the process of electron beam causes this effect as well.

### Random interactions
- Radiation damage: 