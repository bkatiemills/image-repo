# image-repo

A demonstration repo for a version-controlled collection of images browsable by tag.

## Quickstart

```
git clone https://github.com/BillMills/image-repo
cd image-repo
docker container run -v $(pwd):/app/static/image-repo -e HOST_PIC_PATH=$(pwd) -p 8080:5000 -d billmills/whalepic:0.1
```

Visit `127.0.0.1:8080` in your browser (Chrome recommended), and click on some tags on the left to see a selection of corresponding figures; click on figures to see them at their full size, and their full path.

## Image repo format

 - Each image or group of related images goes in its own directory
 - Each such directory contains a file `tags`; this file lists the tags associated with this image, one per line.
 - `tags` file may also include an optional first line beginning with `!CSS!`; all text following this token will be applied as the `style` property of the image (useful for setting `background-color` for images with transparent backgrounds, for example).
