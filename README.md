



FFMPEG one liner to change jpg background from white to light blue. 
```
ffmpeg -i input.jpg -vf "[0:v]split[original][mask];[mask]colorkey=0xFFFFFF:0.01:0.1[keyed];[original]drawbox=0:0:iw:ih:color=lightblue:t=fill[bg];[bg][keyed]overlay" output.jpg 
```
