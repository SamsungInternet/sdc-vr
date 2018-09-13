# SDC Code Lab: Immersive Web - Virtual Reality

This is Part 1 of the Immersive Web Code Lab. [Part 2 is here](https://glitch.com/edit/#!/sdc-ar).

## Instructions

1. Remix this project by pushing the Remix button. This will copy everything into your own project.

![Screenshot](https://cdn.glitch.com/e8b5d783-bf86-4104-9d3b-92edbcf0eb86%2Fimage.png?1536758108849)

2. The code to edit is in `index.html`. It is a boilerplate HTML file with the JavaScript library for A-Frame added.

3. The first code we'll added is the main A-Frame component. This sets up all the rendering and VR capabilities.
```
<a-scene></a-scene>
```

4. The next thing we'll add is a `plane` for the floor. This is uses the `<a-entity>` tag **inside** 
the `<a-scene>` tag. The `geometry` component is used to add 3D shapes to the entity. `rotation` is used to rotate the plane to turn it from a vertical surace to one which lies along the ground.

```
<a-entity geometry="primitive:plane;width:20;height:20;" rotation="-90 0 0"></a-entity>
```

Press the 'Show Live' button. This will load your scene in another browser tab. After each step from now on, take a look at that tab to see how your scene looks in a desktop web browser. (We will try it out in Virtual Reality later!)

5. We can change how the plane looks by using the `material` attribute. `material="color:#00a5ae;roughness:1"`. The color can be any HTML color including names like 'lavenderblush' or 'skyblue' or hexcodes like '#abcedf'

Your `<a-entity>` should now look like this:

```
<a-entity geometry="primitive:plane;width:20;height:20;" rotation="-90 0 0" material="color:#00a5ae;roughness:1"></a-entity>
```

6. The intention is to use the plane to represent water and to make an island using a cube, so we're going to add an additional element for the land.

We'll also use the `position` component to move the plane down a bit. `position="0 -1 0"`

```
<a-entity geometry="primitive:box;depth:20;height:20;width:20" position="4 -10 1" material="color:#449b5b;roughness:1"></a-entity>
```

7. For the sky we can use the `<a-sky>` element. The sky element is a giant inside-out sphere. We can set the color to whatever we would like. In this case we can pick a nice sunset color (or whatever your prefer).

```
<a-sky color="#ffc368"></a-sky>
```

8. We can also import 3D models to the scene. We are using a lighthouse model. You can add it to the scene like so:

```
<a-assets>
    <!-- Model from Google Poly https://poly.google.com/view/eOEwsOqdcHl by Alex “SAFFY” Safayan -->
    <a-asset-item id="lighthouse-obj" src="https://cdn.glitch.com/e8b5d783-bf86-4104-9d3b-92edbcf0eb86%2Fmodel-triangulated.obj?1536741656667"></a-asset-item>
    <a-asset-item id="lighthouse-mtl" src="https://cdn.glitch.com/e8b5d783-bf86-4104-9d3b-92edbcf0eb86%2Fmaterials.mtl?1536741988245"></a-asset-item>
</a-assets>

<a-entity obj-model="obj:#lighthouse-obj;mtl:#lighthouse-mtl" position="10.12 7.50 -5.38" scale="10 10 10"></a-entity>
```

`<a-assets> and <a-asset-item>` are used to import and store 3D models. 

`obj-model="obj:#lighthouse-obj;mtl:#lighthouse-mtl"` is how they are added to each `<a-entity>`.

You have now completed your lighthouse island scene!

9. To try this out in the Gear VR headset, you will need one of the Samsung phones provided. You can borrow one from us if you don't have one. Open up the Samsung Internet browser (labelled "Internet").

10. Take a look at the URL for your project (the one that loaded up in the separate tab when you pressed 'Show Live'). Type in this URL in the Samsung Internet URL bar.

11. Now put the smartphone in a Gear VR headset. Once you put the headset on, you should see the same scene inside a window in Virtual Reality.

12. Tap on the trackpad on the side of the headset to 'click' on the goggles icon in the bottom-right corner. This will make the scene fill the whole 360 degree environment. Take a look around and enjoy your first WebVR experience!
