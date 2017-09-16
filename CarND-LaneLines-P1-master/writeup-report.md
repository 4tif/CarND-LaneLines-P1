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

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

It was so much fun working on this project. However seeing the initial results of my pipeline on the challenge images made me laugh. It was pretty scary to suddenly see red lines everywhere after fairly good results for all other test cases. What I plan on implementing shortly is to create a filter to ignore any lines that have zero or a very shallow slope thereby eliminating all the horizontal lines that are being drawn. Next I plan on to add a new image filter that drastically increases image contrast while lowering image brightness. It is also possibe to selectively remove all blue and green prior to the initial grayscale function. I didn't have enough time at the time of submission, but I have the following somewhat promissing results pointing in the right direction:

[The disaster challenge project image](https://i.imgur.com/P5c9S8F.jpg)


After some of the above ideas implemented on a few screenshots from the challenge source video:

[pic1](https://i.imgur.com/oYGAfTN.png)


[pic2](https://i.imgur.com/yfAi7MJ.png)

AS you can see it's not perfect, but I think if I implement the full idea above it should be a much better overall solution. Let's see!



[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"


