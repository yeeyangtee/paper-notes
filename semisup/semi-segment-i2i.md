# Towards annotation-efficient segmentation via image-to-image translation

Task: segmentation of tumour from images. motivation is to use less training data.

Main idea: 
- Formulate healthy VS unhealthy images as a image translation objective.
- i2i translation is unsupervised, they implicitly learn the removal/addition of tumors.
- This is very similar to segmentation task (removal of tumor part)
- Use this to simultaneously train a segmentation network that can be used to segment out tumour regions.

