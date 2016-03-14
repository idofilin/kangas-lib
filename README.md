# kangas-lib
A javascript helper library for writing interactive WebGL apps.

The library is built around a single core file `kangas-core.js`
that defines wrapper objects for WebGLRenderingContext,
WebGLShader and WebGLProgram. This core can be used on its own,
and is already useful. However, for convenience the core
functionality is extended in a modular way:

- `kangas.js` -- extends the graphics context object defined in
  `kangas-core.js`, to include handling of touch/mouse events, cleanup before
  page unload, and fullscreen requests.

- `kangas-transforms.js` and `kangas-constants.js` -- some 3D math
  and constants.

- `kangas-renderer.js` -- an object that manages
  the animation loop and the vertex and index data.

- `kangas-texture.js` -- a wrapper object around WebGLTexture;
  aids in creating textures from various sources (image file,
  frambuffer attachment, raw pixel data, etc.), and managing texture
  parameters.

- `kangas-noise.js` -- generating noise textures: White noise,
  Worley (cellular) noise, and fractal noise. 

- `kangas-bumpmap.js` -- extends `kangas-texture` by providing
  functionality for generating a bumpmap texture from a given
  input texture. 

- `shader-source-load` -- A web worker script for loading shader
  files and organizing shader source code for the rest of the
  application.

- `webgl-app.css` -- an extremely basic css stylesheet for WebGL
  apps; mostly for fullscreen applications.

- The library contains a third-party minimized script for
  building Voronoi diagrams. The script is copyrighted `(C)
  2010-2013 Raymond Hill`, released under MIT license, and its
  source code is available at
  https://github.com/gorhill/Javascript-Voronoi/.

The library's functionality is accessed through a single global
object (named `Kangas` by default), which is the constructor for
the graphics context wrapper object, mentioned above.

Examples of WebGL apps using the library are available at 
http://ido.filin.fi/showcase.html and
https://github.com/idofilin/webgl-showcase.
