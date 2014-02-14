from PIL import Image, ImageDraw
from images2gif import writeGif
import sys
WIDTH=10

def mask(im,f):
	draw = ImageDraw.Draw(im) 
	for lnum in xrange(w/WIDTH):
		for wnum in xrange(h/WIDTH):#(w/50-1):
			if (lnum+wnum)%2 == f :
				color = im.getpixel(((lnum+1)*WIDTH-WIDTH/2, (wnum+1)*WIDTH-WIDTH/2));
				#color=(0,0,0)
				draw.rectangle([(lnum*WIDTH, wnum*WIDTH), ((lnum+1)*WIDTH-1, (wnum+1)*WIDTH-1)], fill=color)
	return im

def jpg2gif(p1,p2):
    im = Image.open(p1)
    w,h = im.size
    im2 = im.copy()
    im = mask(im,1)
    im2 = mask(im2,0)
    #im3 = im.copy()
    #draw = ImageDraw.Draw(im3) 
    #draw.rectangle([0,0,w,h],fill=(0,0,0))
    writeGif(p2,[im,im2], duration=0.02, dither=0)
    im.save("0_0.jpg")



if __name__=='__main__':
    if len(sys.argv) >= 3:
    	jpg2gif(sys.argv[1],sys.argv[2])
    else:
        print "usage:python ",sys.argv[0],'injpgname outgifname'
	
