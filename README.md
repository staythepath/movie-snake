# Movie Snake

Watch a movie at the head of a 3D snake that grows from the film's camera movement.

Each frame of the movie is a rectangle the shape of the picture. As the movie plays, those rectangles join into a tube that copies the camera lens: pans and tilts bend it, trucks and cranes slide it, push-ins and zooms make it grow faster, and a locked-off shot grows a straight bar. The snake's skin takes its color from the four corners of each frame.

## Use it

Open `index.html` in a browser (or serve the folder with any static server). Everything runs locally; your movie never leaves your computer.

- **Open movie** plays a video file (MP4/H.264 or WebM work best). The snake grows as it plays.
- **Test rig** is a small 3D world with a virtual camera you drive yourself. Hold the buttons or use the keys:
  - Pan ← →, tilt ↑ ↓, roll Q E, dolly W S, zoom Z X, truck A D, crane R F, dolly zoom V B, cut C.
  - **Snake follows → The lens** copies your exact moves. **Tracker** uses only what the picture shows, the same as with a movie.
- **Explore snake** (automatic when a movie ends) lets you orbit, pan, zoom, and fly around the snake with W A S D and R F.
  Fly inside the snake to see the movie frame from that moment.

## How movement is read from a movie

The page estimates camera motion live from how the picture shifts between frames (block matching plus a fitted shift, scale, and rotation). It catches pans, tilts, rolls, zooms, and push-ins, and it detects cuts and letterboxing. From the picture alone it can't tell a sideways truck from a pan, so a toggle chooses whether that motion bends or slides the snake. Exact meter-for-meter lens paths would need an offline 3D camera-tracking pass.

Built with [three.js](https://threejs.org/) r128.
