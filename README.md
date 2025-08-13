



FFMPEG one liner to change jpg background from white to light blue. 
```
ffmpeg -i input.jpg -vf "[0:v]split[original][mask];[mask]colorkey=0xFFFFFF:0.01:0.1[keyed];[original]drawbox=0:0:iw:ih:color=lightblue:t=fill[bg];[bg][keyed]overlay" output.jpg 
```

Filter each pixel if brighter than lightblue rgb val bring it down to lightblue
```
ffmpeg -i output.png -vf "lut=r='min(val,0xAD)':g='min(val,0xD8)':b='min(val,0xE6)'" out2.png
```

or try this
```
ffmpeg -i "Copy of sc0457.jpg" -vf "geq=r='min(r(X,Y),173)':g='min(g(X,Y),216)':b='min(b(X,Y),230)'" out.jpg
```
