# Project: Poisson Matting
This is the implementation of the paper: [Poisson Matting by Jian Sun, Jiaya Jia, Chi-Keung Tang and Heung-Yeung Shum](http://www.cse.cuhk.edu.hk/~leojia/all_final_papers/matting_siggraph04.pdf) done as part of Digital image processing course at IIIT Hyderabad.

## Instructions to run the code
#### clone repository
```bash
git clone {url of the page}
```
or
Click 'Clone or Download' on the top right hand side of the repository.

### Install packages
* install requirements using package manager pip(Use the package manager [pip](https://pip.pypa.io/en/stable/)

```bash
pip3 install -r requirements.txt
```

### Usage
```bash
cd project-made-online
```
* run any jupyter-notebook using 
```bash
jupyter-notebook
```
### Repository Structure
* documents
* src
    * main.ipynb
    * examples
    * Select_roi.py
    * select_roi_curve.py
* img (contains input images)
* outs (contains output images)
* attachments (contains attachments)
* requirements.txt

### Working

The inputs of the code are 
1) An input image
2) Trimap of the input image
3) The desired background(to be changed in input image)

* Only thing to be replaced is image name in main with desired input images(in read input and roi select)
* Do kernel >run all and images would be generated in desired background along with refined mattes. 
* Generated images from global matting and alpha blending in new background are saved in "outs" folder.
* After global matting results are obtained we apply local matting which is semi-supervised to get the final matte. 
Select roi will ask to select regions in image whose matte want to improve upon. Please select regions when pop-up select regions comes.

![Test Image 1](attachments/out.gif)
* The final matte is further refined by diffusion, highpass filtering and boosting. 
* We also implemented mean background method where user can output the images with same foreground but different background to get the required matte which can be blended to any new background. Refer multi-background function for details on usage.

### Results
Inputs: input image, trimap, desired background
Output: image in new background <br>
![res1](attachments/result1.png)
An image matte is generated which from poisson matting using inputs of original image and trimap.
This matte is then alpha-blended to with desired background to give image in new background. <br>
<br>


![res2](attachments/result2.png)
The difference between Global matting and Refinement.




