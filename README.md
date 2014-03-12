# Winner Winner Chicken Dinner!
ChickenDinner is a stupid little Jquery plugin that will randomly load images from a client-side array. See it in action at: [chickendinner.sosweetcreative.com](http://chickendinner.sosweetcreative.com)


## That Sounds Dumb
No, you're dumb. I mean, it makes sense if you are looking to present visitors with a unique experience each time they hit you up. Think banners and heroes. Basically, I wanted to do this on a recent project  [TheMaisonMix.com](http://themaisonmix.com/), and figured someone somewhere might like to do something similar, so here we are.


## How's it Work Then?
Easy peasy. You can either apply it directly to a img tag, or as a css background-image (don't forget to include Jquery champ).


### On an img tag
First, add your image tag with a unique class. Pereferably, you'd leave the src blank (href="#") or add a fallback for the no js, "but that won't validate" punks - a sexy ass fadeIn animation prevents the image from popping through before the script fires (usually). Either way, to always maintain the parent div's height, might wanna rock an intrinsic ratio move.


```html
 /*Blank src*/
 <img class="js-chickendinner" src="#" alt="">
 
 /*With fallback for no-js losers*/
 <img class="js-chickendinner" src="images/banner1.png" alt="">
 
```

Now just initialize the badboy with your class, include the path to your images (defualt path is 'images/'), give 'er a common alt name, and list the images to swap, like so:

```javascript
 $('.js-chickendinner').chickenDinner({
      path: 'http://your-boss-site.com/images/',
      altTag: 'Banner Image',
      fadeInTime:2000,
      TheImages: ['ban1.png', 'ban2.png', 'ban3.png', 'ban4.png']
  });
  
```

### As a CSS background-image
To rock out with random background-images, first add a div with a unique class that you wanna target. Since this will work via inline css, you can also include the inline styles to serve as fallback. 

```html
/* Blank src */
  <div class="js-chickendinner-bg"> <!--Joey Content was here--> </div>
  
  /* With a fallback */
  <div class="js-chickendinner-bg" style="background-image: url("../images/banner1.png"> <!--Joey Content was here--> </div>
 
```

Initialize it, but this time add the option cssBG with the value of 'True'. ChickenDinner will then inject the background-image attribute via an inline style, so make sure to style up your div as you normally would for background images.

```javascript
   $('.js-chickendinner-bg').chickenDinner({
        path: 'images/',
        fadeInTime:2000,
        cssBg:true,
        TheImages: ['banner2.png', 'banner3.png', 'banner4.png', 'banner5.png']
    });

```

## fadeInTime?
An option with a numeric value (milliseconds) that Fades your images in all sexy like. Again, if you include a fallback image this prevents it from blipping through before the script fires.


##Defaults / Options

| Option        |      Description                  |   Value 
| :-------------| :-------------------------------:  | :------------:
| path          |  path to images                   | 'images/' 
| TheImages     | Images to be randomly selected    | ['banner2.png', 'banner3.png'] 
| cssBG         |   To employ css background-image  | True  
| altTag        |  Global img alt                   | 'Banner Image'
| fadeInTime    | Milliseconds fade in time         | 2000


## Check it 
Peep ChickenDinner in action [Here→](http://chickendinner.sosweetcreative.com/), 
