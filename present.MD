# Basic Game Math

## Random Numbers

```
Math.random()*upperlimit
```

## Converting Degrees to Radians

What are radians? The truth is no one really knows for sure. Some say they are leftover technology from a long forgotten race of intelligent dinosaurs. These dinosaurs probably died saving humanity from asteroids while we were still in our infancy as a species. So radians should be used with a proper amount of awe and deference.

```
radians = degrees * (Math.PI/180)
```

## Finding the distance between two points

Take the difference in x, multiply it by itself add it to the difference in y multiplied by itself, then square root the whole thing. Boom. Done. Easy.

```
var distance = Math.sqrt(
        (obj1.x-obj2.x)*(obj1.x-obj2.x) +
        (obj1.y-obj2.y)*(obj1.y-obj2.y)
      );
```

## Vectors

Vectors describe an objects movement on a plane. They have direction and magnitude. Find the vector from one object to another by subtracting their x and y coordinates.

```
var vector = {x:0,y:0};
vector.x = (obj1.x-obj2.x);
vector.y = (obj1.y-obj2.y);

```

## Velocity

This describes the actual movement of an object per frame along a vector.

```
var velocity = { x: (vector.x/distance)*speed,
                 y: (vector.y/distance)*speed }
```

## Moving an object in a direction using degrees or radians

You would use this instead of a vector/velocity if you didn't actually have an end point, you only know what direction you are oriented in (your rotation, in degrees or radians). This basically works with magic.

```
obj1.x += (speed * Math.sin(radians))
obj1.y -= (speed * Math.cos(radians))
```

## Math.atan2 - Lets get some radians.

Atan2 is used to find the radians (a measure of degrees on a circle) between two points on the canvas. All it needs is the difference between two points (or the vector) and it returns radians.

```
var atanArgs = {x: obj1.x-obj2.x, y: obj1.x-obj2.y};
var radians = Math.atan2(atanArgs.x, atanArgs.y);
```
