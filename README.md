# inkscape-standards

This repo contains some useful files like templates and color palettes to work with lasercut files. Files have to go Inkscape's user directory:

```
cd ~/.config/inkscape/
```

## Color scheme
Recommended color in case we use svg:style element together with "class" attribute to style an element

### Useful mapping
The desired usage for colors

| Color  | CSS Code | Cutting or Engraving     | What type of segments |
|--------|----------|--------------------------|-----------------------|
|black   | eri1     | vector cutting (general) | regular segments      |
|blue    | eri2     | vector cutting (inside)  | regular segments      |
|green   | eri3     | vector cutting (outside) | regular segments      |
|red     | eri4     | vector engraving         | regular segments      |
|magenta | eri5     | vector engraving         | slow segments         |
|cyan    | eri6     | vector cutting           | slow segments         |
|yellow  | eri7     | -- not yet used --       | -- reserved --        |

### The CSS for strokes
```
.eri1 {
  fill:none;
  fill-opacity:1;
  stroke:#000000; /*black*/
  stroke-opacity:1;
  stroke-width:0.26458333; /*1px*/
  stroke-linecap:round;
  stroke-linejoin:round;
}
.eri2 {
  fill:none;
  fill-opacity:1;
  stroke:#0000FF; /*blue*/
  stroke-opacity:1;
  stroke-width:0.26458333; /*1px*/
  stroke-linecap:round;
  stroke-linejoin:round;
}
.eri3 {
  fill:none;
  fill-opacity:1;
  stroke:#00FF00; /*green*/
  stroke-opacity:1;
  stroke-width:0.26458333; /*1px*/
  stroke-linecap:round;
  stroke-linejoin:round;
}
.eri4 {
  fill:none;
  fill-opacity:1;
  stroke:#FF0000; /*red*/
  stroke-opacity:1;
  stroke-width:0.26458333; /*1px*/
  stroke-linecap:round;
  stroke-linejoin:round;
}
.eri5 {
  fill:none;
  fill-opacity:1;
  stroke:#FF00FF; /*magenta*/
  stroke-opacity:1;
  stroke-width:0.26458333; /*1px*/
  stroke-linecap:round;
  stroke-linejoin:round;
}
.eri6 {
  fill:none;
  fill-opacity:1;
  stroke:#00FFFF; /*cyan*/
  stroke-opacity:1;
  stroke-width:0.26458333; /*1px*/
  stroke-linecap:round;
  stroke-linejoin:round;
}
.eri7 {
  fill:none;
  fill-opacity:1;
  stroke:#FFFF00; /*yellow*/
  stroke-opacity:1;
  stroke-width:0.26458333; /*1px*/
  stroke-linecap:round;
  stroke-linejoin:round;
}
```

# HowTo use another directory as user's font directory
Instead of installing each font we need to the default directory, we just can use a symbolic link to a shared dir, which is synced over cloud. This also omits to copy the font files to Inkscape dir. This is useful for a multi computer environment, where every computer should have the same set of recent files. We use Seafile in this example:
```
cd /usr/local/share
sudo su
rmdir fonts #must be empty
ln -sf ~/Seafile/horizon.somebody.com/fonts fonts
chown -H root:staff fonts/
```
