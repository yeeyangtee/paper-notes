# Segmentation of Integrated Circuit Layouts from Scan Electron Microscopy Images

use filtering + normalisation + region growing to perform segmentation. Mainly uses classical image processing techniques.

Interesting thing here is the evaluation methodology.
Segmentation errors are defined by the open/short circuit errors, which are basically things that are electrically significant instead of typical segmentation analysis such as IOU/segmentation accuracy.

The evaluation methodology is called SCT( segmentation comparison tool):
- First compute the pixel-wise difference between predictions and the ground truth.
- Next, label (numerically) the lines and background by connected regions
- Also label or segragate each region or group of the 'difference map'
- For each region in the difference map, compare the amount of line regions it touches in the predictions vs ground truth. If there is short circuit, the difference will touch less regions in the predictions.
- To also account for open circuit, do the same thing but just look at how many background regions are touched instead.
- Essentially we are counting the difference in electrically significant components for EACH region (essentially every edge.)