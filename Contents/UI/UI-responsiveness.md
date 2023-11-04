# offscreen rendering
The process where we process/calculate the graphic/visual content before dislaying it on the screen. 
We can use View Debugger to [detect expensive offscreen passes](https://www.youtube.com/watch?t=906&v=gbAjrPqFLUY&feature=youtu.be&ab_channel=iOSConfSG)

## Examples: 
- Example1: We apply a filter to a image. The output image is computed off screen. 
- Example2: Apply a shadow to a view

## Offscreen rendering is expensive: 
Take for example the case of shadow (using layer.shadowXXX = ...). Usually the view hierarchy is drawn from back to front, however in the case of shadow, the render engine needs to know the outline of the objects being draws first, so it will need to implicitly render the objects in hidden context first -> calculate the shape of the shadow -> Draw the shadow -> re-draw the objects in the actual context again.

## Practical tips
### Avoid shadow cost:
- Use bezier path
- Use layer.shouldRasterize (not good for memory space)
- Use an ImageView as a shadow (Most performant - should be used whenever possible)

### Detecting UI runtime issues
With View **Hierarchy debugger**, we can turn on Editor -> View Layers to detect runtime issues
