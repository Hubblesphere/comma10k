# comma10k

In honor of the comma.ai hackathon, which starts today (2/28/2020), we are releasing the first 1,000 images of our internal comma10k dataset. After we clean up these labels, we'll release more.

![Alt](sample.jpg "First image from the dataset")

It's 1,000 pngs of real driving captured from the comma fleet. It's MIT license, no academic only restrictions or anything. It also includes our internal segnet's guess at category.

Run <pre>./viewer.py</pre> to see them with segnet overlay.

## Directories

<pre>
 imgs/  -- The png image files
 masks/ -- PNG segmentation masks (update these!)
 segs/  -- The outputs in probablity from our internal segnet (unreleased, too big)
</pre>

## Categories of internal segnet

<pre>
 0 - #ffffff - empty
 1 -         - sky (deprecated, now undrivable)
 2 - #402020 - road
 3 - #ff0000 - lane markings (drivable, right now includes some non lane markings, remove these!)
 4 - #808060 - undrivable
 5 - #00ff66 - movable (split into vehicles and people/animals?, actually don't)
 6 -         - signs and traffic lights (deprecated, now undrivable)
 7 - #cc00ff - my car
</pre>

## The Idea

We want to add a data labeller in this repo, such that people can fix the committed labels and submit a pull request for the new ones.

Photoshop on the mask files is also a good choice.

## How can I help?

Start labelling!
Either use the included comma pencil labeller
OR
Use an external image manipulation tool such as [GIMP](https://www.gimp.org/downloads/) (Free) or [Adobe Photoshop](https://www.adobe.com/products/photoshop.html) (Paid)

1. Fork this repository to your account using the "Fork" button in the top right
2. Clone your fork, and use your labelling tool of choice to label some images
3. Open a pull request to the official repository to submit your changes!

### Using the built-in labeller (only works with MacOS/Linux)

```
pip install Flask
./label.sh
```

Then open a browser window to http://localhost:5000/
