# SDSS_CMD

Welcome to my SDSS galaxy color-magntiude diagram (CMD) viewer!! This tool can be used to read a table of galaxies with known magnitudes to create an interactive CMD where users can click on each bin of the CMD to display galaxies that are representative of that color and magnitude range.

**Requirements:**
- python (I use python3)
- jupyter notebooks
- Common packages: numpy, pandas, PIL, requests
- plotly, an interactive data visualization library
    - Either pip install plotly==4.14.3 or conda install -c plotly plotly=4.14.3
    - Visit https://plotly.com/python/getting-started/ for more information about plotly
- A csv file that has objid,u,g,r,i,z,ra,dec columns for SDSS galaxies
    - I am using a csv of the top 1000 Galaxy Zoo galaxies with more than 10 votes
- An image of just a black white background to serve as a placeholder for bins with no galaxies in your working directory
    - I use a file I found on google called "white.jpg"
    
This code has a cell that will create a folder in your working directory called gal_images1 and populate it with cutout images of all the galaxies in your csv file. The images are only ~ 1 kb in size, so they shouldn't take up too much space, but make sure you have room on your computer. This will take a few minutes, because there are 1000 images to get! Good news is that you only have to run this cell once, after that all the galaxies should just be stored on your computer and you can modify your plot/code to your heart's content.

Once you've run all the cells, you should see a color-magnitude diagram pop up of all the galaxies in your input csv file. Click on any of the bins of the CMD histogram to see a selection of galaxies representative of that color and magnitude bin. The magnitude and color bin you are clicking on is displayed in a box around your mouse cursor when you hover over any bin as the x and y values, respectively. The z value will show you the number of galaxies in that bin. If a bin has more than 3 images, I simply take the first 3 images that plotly tells me are in that bin. If you click and no images appear, that means there are no galaxies in your dataset that correspond to that color and magnitude range.

There are also two customization options above the plot. With the colormap buttons, you can chose from four different colormaps to display the CMD in based on your visual preferences. You can also reverse the colormap (i.e. if the original colormap is a gradient going from red to blue, reversing would make it go from blue to red) using the "reverse colormap" true/false buttons. This does not change anything about the data, only how it is visually displayed to you.


There are also some plot options that are built-in with plotly that are displayed as little grey buttons above and to the right of the CMD (to the left of the first galaxy image that appears). You can hover over them to see what they do. You can zoom in or out, autoscale, pan, toggle spikelines, and more.

If you'd like to run this code, I have provided my csv file called results.csv and placeholder image white.jpg in the folder with the notebook, so you should be able to run this without any modification to the code.

Please note that this notebook is a very rough and unpolished, first version of this program. I made this as a proof-of-concept to see if I could make a tool like this that is akin to the Voyages old activity about galaxy CMDs that no longer works. I have some to-dos/questions that I thought about when making this in the very last cell of this notebook. For example, one of my biggest worries right now is needing to download all the images on a computer locally. This could probably be changed if this was a web activity vs. a notebook a user would run. In addition, I would love for a user to be able to import a dataset through a button/GUI menu instead of changing code, but this only seems to be an option if using plotly dash, a tool that lets you make interactive dashboards/web apps. 

Disclaimer: I am new to plotly (this is my first time using it!) or making interactive visualizations in general, so apologizes for any confusing or badly-written code. I relied heavily on plotly tutorials and examples to create this, which can be found at https://plotly.com/python/. 

Hope you enjoy this visualization!!
