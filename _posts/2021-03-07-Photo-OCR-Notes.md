Sliding Windoe
<hr>
First component of Photo OCR phipeline is text detection. But text has different spect ratio in different photos.

> Spect Ratio: Height Width ratio

What Sliding Window algorithm says:
Take a predetermined size of rectangular patch, slide it over by a little bit throughout the image. Shift parameter size is called `step size` or `stride`. Then the image patch will go to the classifier.

In our Photo OCR case, we do the same as sliding window algorithm, make a heatmap like representaion to exploid the region with texts.

Second component of Photo OCR pipeline is character segmentation. We can use supervised classifier to detect whether there is a split between two characters.

Artificial Data Systhesis
<hr>

* Take characters from different fonts and attach these in any random background, maybe with affine, rotate, shear.

* Systhesize data with distortion

Ceiling Analysis: What part to emphasize
<hr>
Photo OCR pipeline
`Image-->Text detection-->Character Segmentation-->Character recognition`

Which component worth most time?
In isolation, which part of the pipeline is most responsible for the overall accuracy of the pipeline?