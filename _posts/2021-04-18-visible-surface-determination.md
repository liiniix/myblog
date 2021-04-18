Also called hidden surface removal.

Given a set of 3D objects and a camera. Determine edges or surfaces of the object that are visible:
- We can clip at object level(clip against object), called clipping
- We can remove at pixel level/scene level(deeper object/pixel/edge will be occluded), called occlusion

1st one can obtain object level accuracy, 2nd one obtain pixel level accuracy.

Painter's Algorithm: Object precision

Draw farthest object first, then second farthest.
Painter's algorithm will fail if the objects are overlapping.
Also called back-to-front strategy.

### Backface Culling, Polygon based accuracy

$$NOS = \text{direction from monitor/viewing surface to eye}$$
$$N_{obj} = \text{surface normal of object}$$
$$\text{if } NOS \cdot N_{obj} < 0: \text{it's a backface, thus discarded}$$

This algo assume objects are closed:
- Works only for closed and convex objects
- Objects with holes expose backface to viewer, but discarded by algo. This is an error.

### Point/pixel level accuracy

`Video Controller` fetch pizel data from `frame buffer` to monitor. CPU also write things on frame buffer indepently. So `Frame Buffer` is called dual access memory.

There's also another buffer which is called `Z-buffer/color buffer`.

`z-buffer` is initialised by far `z` value. Color buffer is initialised by background color.

When an object is rendered, z value is compared. If new z is nearer then new z is stored in `z buffer` and color buffer/framebuffer will store with new color for `z`.

Disadvanteage:
- Z-fighting: intersecting polygons