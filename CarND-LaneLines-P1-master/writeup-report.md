# **Finding Lane Lines on the Road** 

## Writeup Report
---

**Finding Lane Lines on the Road**


The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 7 steps:

1. I converted the images to grayscale, then 

2. I applied a gaussian blur with a kernel size of 5. 

3. After these two intial steps it was time for a Canny Transform to identify various contrasting edge points in the images. 

4. Masking and using fillPoly() to create a polygon mask to focus on a specific area within the image

5. Hough transforms and lines were added with the following settings to optimize creating ideal lines:
   * rho = 1
   * theta = np.pi/180
   * threshold = 50
   * min_line_len = 150
   * max_line_gap = 200
   * line_image = np.copy(image)*0

6a. Next, we take the "lines" from the Hough Transform and use them to draw actual lines over the image 

6b. Merge and create a composite image between color and line image 

7.  Weighting of image is processed in this step and the final image is returned  

Aside from these steps the draw_lines function was kept fairly stock. It could use adjustments to only allow lines wtih specific slope ranges and that is what I plan on trying next. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][https://i.imgur.com/wvuSdMA.png]


### 2. Identify potential shortcomings with your current pipeline

So far, the biggest shortcomings I've noticed in my pipeline involve 3 things. The first two came into clear view with the Challenge Video.

1. My pipeline needs to take into account lines which may appear in the masked area but are still clearly not the main lane lines we need to draw. These are primarily horizontal and appear when contrasting shadows appear. 

2. Along the lines of the last note, my pipeline could add a filter for lighting, as well as removing obvious elements like a light blue sky or green trees that may cause contrast lines to appear and result in creating false lines. Better masking may also eliminate railings that are giving off contrast lines that the pipeline seems to be identifying as lane lines. 

3. Speed. I believe there might be a way to do all of the above while also using some sort of deque collection or other elegent solution. I will keep researching and looking into ways to improve these results and account for all kinds of weather, lighting, and road conditions! 


### 3. Suggest possible improvements to your pipeline

It was so much fun working on this project. However seeing the initial results of my pipeline on the challenge video made me laugh. It was pretty scary to suddenly see red lines everywhere after fairly good results for all other test cases. What I plan on implementing shortly is to create a filter to ignore any lines that have zero or a very shallow slope thereby eliminating all the horizontal lines that are being drawn. Next I plan on to add a new image filter that drastically increases image contrast while lowering image brightness. It is also possibe to selectively remove all blue and green prior to the initial grayscale function. I didn't have enough time at the time of submission, but I have the following somewhat promissing results pointing in the right direction:

![The disaster challenge project image](https://i.imgur.com/P5c9S8F.jpg)


After some of the above ideas implemented on a few screenshots from the challenge source video:

![pic1](https://i.imgur.com/oYGAfTN.png)


![pic2](https://i.imgur.com/yfAi7MJ.png)

AS you can see it's not perfect, but I think if I implement the full idea above it should be a much better overall solution. Let's see!



[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"


