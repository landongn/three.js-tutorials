##Example #1:  Frustum, eyeballs, pyramids, and the sky

One of the biggest things preventing a lot of newbies in the 3d world is understanding the difference from something like the DOM to 3d space.  A lot of web developers out there usually don't think about the connection between the viewable space and HOW they view it, it's just a static, two dimensional plane that lets you append boxes, text, and images to it, along with some nifty transitions. 

Thing is though, this can turn into a mindstate that sort of overtakes your whole perspective on 'web development'.  You start being comfortable in systems of "pages" and "viewports" and being "responsive" and all of that.  That's great, to a point-  It's great for the existing web, but not so great when you start to think about that third dimension. 


One of the big things that got me for a long time about 3d in general was "How do things show up on the screen, and if this is 3d space, what's my perspective?".  

This seems pretty basic, and you'd figure that it would be easily looked up within a book, but assume for a second that I'm a complete idiot (it's not hard) and I don't even know what the hell perspective is.  When thinking about the problem, I always assumed that I had an x, a y, and a z Vector, which allowed me to place elements within 'a thing' and then magic would happen and suddenly pixels.   But really, that was just my ignorance within the web development world coming through.  

What broke through that cobweb infested brain of mine is when I learned what the heck a View Frustum was, and why it was important in 3d rendering. 

I say "Rendering" and not "Graphics" in general because it's really all about _rendering_.  You're taking a scene, adding geometry, materials, lighting, shaders, and then finally rendering it.  But to what?  What is getting rendered, and where is it getting rendered? How do I know direction? What about particle effects! Sweet tits, think about all of the fucking matrix transformation wat is happening i am not good with compu

**ahem**

Enter: The Pyramid of Eyeballs. 

![The Pyramid of Doom](https://raw.github.com/landongn/three.js-tutorials/master/1/frustum.png)

Everything that exists within the _volume_ of the frustum is what you actually see when you see "3d" graphics.  It's the lynchpin on the whole operation.  Three Dimensional Space doesn't exist without it. 

Whenever you've played a game of quake, this frustum extended out from your character, allowing you to see the world in it's detail.  It's the entity that drives all of the mathmatical wizardry and witchcraft that no doubt spawned from some dark thoughts in the brains of John Carmark all those years ago.  

The long and short of the example here is that the most basic thing in 3d- the frustum -  tells the camera what it _can_ see, but not what it _can't_.  

The thing is here, you should think of the camera as a viewport on a mobile device, but with a lot of amazing properties.  As web developers, your page can now be navigable forwards, backwards, instead of just one page -> one view.   You could layer in hundreds of different entities within your 3d world, but it's all dark and useless without a proper frustum. 

Not to overdo it here, but the next time it's a cloudy day outside, take a look up at the sky.  You and I have about about 90 degrees of vision.  Within that 90 degrees, we can see just about as far as the nearest cloud above us, and all of the clouds within our peripheral vision.  This is essentially the view frustum in the real world.  

We have a near plane (your eyes), and a far plane (the clouds).  

The edges of your peripheral vision form your field of view from your near plane to your far plane, however far away that may be.  Keep in mind, though-  You can see more of the world farther away, and less of the world up close.

Commit this to memory. It should be second nature for you to think this way when you are working in 3d.

In the example, we cover the basics of creating a camera, and setting the properties of its frustum within the constructor.  Toy around with some of the values.  What makes the white block smaller, without changing its size?  What happens when you change the field of vision?  what about different sizes of the near and far plane? 

Think about the _rendering_ process behind the scenes.  What if you wanted to only show elements that were within the players view? (a concept called Culling) Frustums help with culling in that it sets defined parameters for the viewable space in the world, and only renders those elements. 

Fast 3d programs MUST take advantage of culling, especially visually complex and nuanced graphics. 
