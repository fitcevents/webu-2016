**Level up your design and development team SVG workflow**

With Robyn Larsen

Scalable vector graphics (SVGs) are at the intersection of the design and development phases of front-end web development. SVGs hand control over creating visual assets to the developer, allowing them to rely less on designers to create multiple PNG assets. Furthermore, with SVG filters you can create impressive filter effects and animate them using[ SMIL](https://developer.mozilla.org/en-US/docs/Web/SVG/SVG_animation_with_SMIL). Note that Chrome had removed support for SMIL in Chrome 45, but put it back because the "web platform was not ready".

Before you start working with SVGs you need to decide how you want to interact with the image in the browser and be able to communicate that with you team. Decide if you want the graphic to be static or animated, and communicate this early as it will affect how the assets will be prepared. SVGs are commonly created in tools like Illustrator and Sketch. There are large number of tutorials on exporting from Illustrator, so the Sketch pipeline is focussed on here.

First, you'll want to place your asset on its own artboard as the artboard gets translated into the viewBox. Next, select the layers you want and use the Sketch flatten command to merge the layers. Merging will remove transforms, properties Sketch otherwise applies to SVGs based on their relative position in the infinite canvas. Before merging the SVG will have a lot of nested tags, which reflect how we tend to work in Sketch as designers. You’ll want to name your layer(s) in Sketch as this will be transferred to the SVG as ID(s). Naming conventions such as  icon- or logo- prefixes for SVG icons and logo IDs, and svg- for class names can help identify SVG layers in your CSS and JS. The SVG markup initially exported from Sketch is really messy. To get a better, cleaner version of the SVG (only if you’re exporting from Sketch) you can run this command from terminal:

$ defaults write com.bohemiancoding.sketch3 exportCompactSVG -bool yes

(See[ article](https://robots.thoughtbot.com/organized-workflow-for-svg) by Steve Harley, "A more efficient and organized workflow for SVGs" for more information.)

Optimize further with the[ SVGO](https://github.com/svg/svgo) NodeJS tool:

$ npm install -g svgo

$ svgo --pretty folder/

$ svgo --pretty file.svg

$ svgo --pretty file.svg file.min.svg

There are a few other addition changes you may need to do by hand. Remove the width and height attributes from the SVG, then in the CSS apply a max-width of 100% to it since you always want the vector graphics to scale to the size of the parent. We no longer have to worry about declaring the SVG namespace with xmlns attribute anymore (since SVG 2.0 landed on Sep. 15) for inline SVGs so these can be removed as well. The most important pieces of the SVG are the paths because that’s what tells the computer what the shape looks like (you probably don’t want to touch these).

There are a couple cases when you’ll want to deviate from this basic workflow, such as social media or similar icon "spritesheets" and SVGs intended for complex animations. Every website has a list of social icons and instead of exporting them as individual SVGs we can put them on a single dartboard and export them together and then use the ‘use’ keyword later to indicate which one you want to show. For SVGs intended for animation where you intend to animate the different parts you don’t want to merge the layers or optimize the SVG with SVGO since optimization reduces the integrity of the SVG. Instead you’ll want to optimize the SVG by hand in order to control its exact shape.

You can accomplish amazing things with SVG filters and there are a lot of them. ‘filter' is also a CSS property which means we can control it in CSS, e.g. only apply them at certain breakpoints.

Blur effect: Create a SVG blur effect with the feGaussianBlur filter. The stdDeviation attribute defines how far the glow effect should extend. If you see it cut off at the sides, that’s the dimensions of the viewbox that’s cutting it off. The viewBox defines the relative space that the SVG is in. Set the animate tag inside the feGaussianBlur tag in order to animate it. Within the animate tag use the attributeName to indicate which attribute the animation should target. "from" and “to" attributes set the value range to be animated. “Values" indicate the order the values should be hit during the animation while “keyTimes” are when these values should be hit. In this example the feComposite tag tells us that the source graphic and blur effect should be merged into one. If you didn’t compose the initial and blurred image you would just have a blurry image.

Spotlight: Pretend the room is the viewBox, and there is spotlight hitting you in the face. Create the spotlight with fePointLight filter. You can control the light color, specularity, position, and width. The fePointLight x, y, and z values corresponds to the spotlight's position in the viewBox/room. To animate the light moving left and right, animate its position along the x plane.

A last note about browser compatibility... it’s not super awesome. One audience member asked, "how far back in IE?", and Robyn’s answer was, “No. If you need to support IE < 10 use PNGs."

