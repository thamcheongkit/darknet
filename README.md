# YOLO: People Segmentation

### Build:
```cd /path/to/darknet```

```make```

```wget https://pjreddie.com/media/files/yolo.weights ```

### Usage:
```cd /path/to/darknet```

```./darknet detect cfg/yolo.cfg yolo.weights```:

```
layer     filters    size              input                output
    0 conv     32  3 x 3 / 1   416 x 416 x   3   ->   416 x 416 x  32
    1 max          2 x 2 / 2   416 x 416 x  32   ->   208 x 208 x  32
    2 conv     64  3 x 3 / 1   208 x 208 x  32   ->   208 x 208 x  64
                                 ... 
   29 conv   1024  3 x 3 / 1    13 x  13 x1280   ->    13 x  13 x1024
   30 conv    425  1 x 1 / 1    13 x  13 x1024   ->    13 x  13 x 425
   31 detection
Loading weights from yolo.weights...Done!
Enter Image Path: <enter_your_file_path eg. images.txt>
```

```tail metacrop.txt```:

```
/photos/3bb1a3475a739ca9a6ec249225d274c672ce67fc.jpg 54 248 98 427
/photos/4db7c11f12f3b307529682c4f733f842e43e1f02.jpg 150 314 29 589
/photos/91e624c658532130f3f78cc97e956e1afc1b90d0.jpg 181 293 66 511
/photos/fa581732852d29bcb73204c0daba2931c9b7745f.jpg 91 316 9 599
/photos/4b67d657a95fddd5ad70a67e8805af684cd18d16.jpg 139 292 56 547
/photos/5a66076e99f24123d6b5c57cded20f9c98ffd82c.jpg 116 271 14 599
/photos/d43d60b4a52e2387ad0f3e4f836fb97aa4bf9f50.jpg 136 302 31 591
/photos/da202d51daad2fb46b717422026f6e4932774bae.jpg 61 164 146 454
/photos/da202d51daad2fb46b717422026f6e4932774bae.jpg 242 352 145 450
/photos/cb8928fe24b74e65743664554b7914011b27853b.jpg 121 342 116 599
```

### How to read:
```/photos/3bb1a3475a739ca9a6ec249225d274c672ce67fc.jpg 54 248 98 427```

```<image_path> <left> <right> <top> <bottom>```
