## Usage
Swipe only needs to follow a simple pattern. Here is an example:

``` html
<div id='slider' class='swipe'>
  <div class='swipe-wrap'>
    <div></div>
    <div></div>
    <div></div>
  </div>
</div>
```

Above is the initial required structure– a series of elements wrapped in two containers. Place any content you want within the items. The containing div will need to be passed to the Swipe function like so:

``` js
window.mySwipe = Swipe(document.getElementById('slider'));
```

I always place this at the bottom of the page, externally, to verify the page is ready.

Also Swipe needs just a few styles added to your stylesheet:

``` css
.swipe {
  overflow: hidden;
  visibility: hidden;
  position: relative;
}
.swipe-wrap {
  overflow: hidden;
  position: relative;
}
.swipe-wrap > div {
  float:left;
  width:100%;
  position: relative;
}
```

## Swipe now supports bullets and arrow navigation

If you want to add arrows and bullets to your swipe wonder you would do something similar to this, but you can structure it as you like, this is just an example, but you can see in action if you open the index.html file:

``` html
<div id="swipe_direction_nav">
  <a id="swipe_prev" class="swipe-slider-prev">Prev</a>
  <div id="swipe_bullet_wrapper"></div>
  <a id="swipe_next" class="swipe-slider-next">Next</a>
</div>
```

Also when you click on a bullet Swipe will slide to that specific section. Neat!

Go ahead and give the demo a try and see how amazing Swipe is.

Built-in bullet support and arrow navigation contributed by [Alex Budin](https://github.com/alex-b).



## Config Options

Swipe can take an optional second parameter– an object of key/value settings:

- **startSlide** Integer *(default:0)* - index position Swipe should start at

-	**speed** Integer *(default:300)* - speed of prev and next transitions in milliseconds.

- **auto** Integer - begin with auto slideshow (time in milliseconds between slides)

- **continuous** Boolean *(default:true)* - create an infinite feel with no endpoints

- **disableScroll** Boolean *(default:false)* - stop any touches on this container from scrolling the page

- **stopPropagation** Boolean *(default:false)* - stop event propagation
 
-	**callback** Function - runs at slide change.

- **transitionEnd** Function - runs at the end slide transition.

- **btnNextId** Function - the ID of the element that you want to trigger the next slide.

- **btnPrevId** Function - the ID of the element that you want to trigger the previous slide.

- **bulletWrapperId** Function - the wrapper that will contain the bullets related to your slides (you can style it at your free will in your CSS).

- **bulletClass** Function - the CSS class that you have created for your bullet, if not specified a default 'swipe-bullet' will be used.

- **bulletActiveClass** Function - the CSS class that represents the active state of your bullet, if not specified a default 'active' class will be used.

### Example

``` js

window.mySwipe = new Swipe(document.getElementById('slider'), {
  startSlide: 2,
  speed: 400,
  auto: 3000,
  continuous: true,
  disableScroll: false,
  stopPropagation: false,
  callback: function(index, elem) {},
  transitionEnd: function(index, elem) {},
  btnNextId : 'swipe_next',
  btnPrevId : 'swipe_prev',
  bulletWrapperId : 'swipe_bullet_wrapper',
  bulletClass : 'swipe-bullet',
  bulletActiveClass : 'active',
});

```

## Swipe API

Swipe exposes a few functions that can be useful for script control of your slider.

`prev()` slide to prev

`next()` slide to next

`getPos()` returns current slide index position

`getNumSlides()` returns the total amount of slides

`slide(index, duration)` slide to set index position (duration: speed of transition in milliseconds)

## Browser Support
Swipe is now compatible with all browsers, including IE7+. Swipe works best on devices that support CSS transforms and touch, but can be used without these as well. A few helper methods determine touch and CSS transition support and choose the proper animation methods accordingly.

## Who's using Swipe
<img src='http://swipejs.com/assets/swipe-cnn.png' width='170'>
<img src='http://swipejs.com/assets/swipe-airbnb.png' width='170'>
<img src='http://swipejs.com/assets/swipe-nhl.png' width='170'>
<img src='http://swipejs.com/assets/swipe-htc.png' width='170'>
<img src='http://swipejs.com/assets/swipe-thinkgeek.png' width='170'>
<img src='http://swipejs.com/assets/swipe-snapguide.png' width='170'>

Shoot me a [note](mailto:brad@birdsall.co) if you want your logo here
