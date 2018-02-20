# WebGL and JavaScript Engine

This project uses WebGL and JavaScript. There is only one library dependency, gl-matrix, which is included in the project.

Since the game runs on the browser, you need to emulate a server. I recomend NetBeans 8.2 or higher and Google Chrome.

Download NetBeans and install from here: https://netbeans.org/

Get the NetBeans plugin for google Chrome from here: https://chrome.google.com/webstore/detail/netbeans-connector/hafdlehgocfcodbgjnpecfajgkeejnaa?hl=en

To try the game, please open the project on NetBeans 8.2 or higher and click on the green play icon.

I included a nice UML diagram to show all the classes in the game engine and their respective relationships. The classes are divided into groups, color-coded for clarity.

NOTES:

- The aim of this engine was to learn more about WebGL and JavaScript. In other words, coding games for the web.
- I learned to interface WebGL and HTML5 to setup the overall canvas for drawing and specifying behavior with JavaScript.
- The best features of this engine are the extensive renderable and shader capabilities.
- You can cast shadows from objects (ShadowCaster) to surfaces or other objects (ShadowReceiver) you specify.
- You can draw efficiently several lights in the scene with minimal impact on performance.
- The light model follows the Phong Illumination Model. Renderable objects have a Material which specify properties such as ambient, specular, diffuse and emissive. When a light source shine on an object, it interacts with its properties and determines the illumination.
- Lights can be speficied based on their nature (Ambient, OmniDirectional, Spot) and customize things such as light color, intensity, direction, outer and inner cone angles, fadeout.
- Objects all inherit from Renderable and this makes it easy for all GameObjects to support shader effects.
- You can create several GameObjects and compose your scene from a XML file, without touching the rest of the codebase.
- You can render fonts from a bitmap or trueType file.
- You have a simple tile engine and the ability to create parallax effects, by specifying layers with different scrolling speeds.
- A simple physics system was implemented with circle collision, rectangle collision (AABB) and pixel perfect collision. When a GameObject is created for a scene, you just specify which one of the collision models it has.
- A Camera system was implemented. You can create several cameras by leveraging the Viewport in WebGL. Cameras are GameObjects, they can be fixed or they can follow the player or other objects (position-locking). You can also apply a shaking effect to cameras.
