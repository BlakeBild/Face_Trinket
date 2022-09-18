import time
import thumby
import math
import random


#just making random looking faces


# BITMAP: width: 20, height: 15
whiteOpenPea = bytearray([0,240,248,252,254,254,254,254,254,254,254,254,254,254,254,254,252,248,240,0,
           0,7,15,31,63,63,63,63,63,63,63,63,63,63,63,63,31,15,7,0])
whiteSquintyPea = bytearray([0,240,248,248,248,248,248,248,248,248,248,248,248,248,248,248,248,248,240,0,
           0,7,15,15,15,15,15,15,15,15,15,15,15,15,15,15,15,15,7,0])
#maybe make a bloodshot looking pea           
           
           
# BITMAP: width: 7, height: 7
peaDot1 = bytearray([65,0,32,32,34,24,65])           
#make some more peaDots like stars or hearts or something


# BITMAP: width: 15, height: 15
nose2 = bytearray([0,0,0,0,0,0,0,255,252,128,0,0,0,0,0,
           0,0,4,2,1,0,0,15,15,15,14,12,0,0,0])

# BITMAP: width: 40, height: 15
mouth = bytearray([0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,128,128,192,192,224,120,24,0,0,
            0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,12,12,12,12,12,12,12,12,6,6,6,6,3,3,3,1,1,0,0,0,0,0,0])
mouthSmile = bytearray([0,0,24,120,224,128,128,128,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,128,128,192,192,224,120,24,0,0,
            0,0,0,0,0,1,1,3,3,7,6,6,6,12,12,12,12,12,12,12,12,12,12,12,12,6,6,6,6,3,3,3,1,1,0,0,0,0,0,0])
mouthSmile2 = bytearray([0,0,0,0,0,0,0,0,0,0,0,224,224,0,0,0,0,0,0,0,0,0,0,0,0,0,0,224,224,0,0,0,0,0,0,0,0,0,0,0,
            0,0,0,0,0,0,0,0,0,0,0,7,15,12,12,12,12,12,12,12,12,12,12,12,12,12,12,15,7,0,0,0,0,0,0,0,0,0,0,0])
catMouth = bytearray([0,0,2,18,146,146,146,84,8,128,224,0,0,0,0,0,0,0,0,128,192,128,0,0,0,0,0,0,0,224,128,0,0,72,148,146,146,18,2,0,
            0,0,0,0,0,0,0,0,0,7,15,12,12,12,12,12,12,12,14,7,1,7,14,12,12,12,12,12,12,15,7,0,0,0,0,0,0,0,0,0])
mouthOh = bytearray([0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,240,252,60,12,12,12,12,60,252,240,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,
            0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,3,15,15,12,12,12,12,15,15,3,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0])
mouthKissy = bytearray([0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,16,16,80,80,16,12,4,68,228,228,68,12,56,224,0,0,0,0,0,0,0,0,0,
           0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,4,4,4,4,12,56,32,33,35,35,33,48,28,7,0,0,0,0,0,0,0,0,0])
mouth3 = bytearray([0,0,0,0,0,0,0,0,0,0,0,0,0,128,128,192,192,192,192,192,192,192,192,192,192,128,128,0,0,0,0,0,0,0,0,0,0,0,0,0,
            0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,1,1,1,1,1,1,1,1,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0])

# BITMAP: width: 30, height: 10 
peaBrow2 = bytearray([0,16,24,8,8,8,12,12,4,4,4,4,4,4,4,4,4,4,4,4,4,12,12,8,8,8,24,16,0,0,
           0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0])
peaBrowAngry = bytearray([0,0,0,0,0,0,0,0,0,0,0,0,2,2,2,2,6,6,6,6,6,14,14,12,28,56,248,224,128,0,
            0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,1,0])
peaBrowOther = bytearray([0,24,48,48,48,24,28,14,7,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,
            0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0])            
          
peaBrowSprite = thumby.Sprite(30, 10, peaBrow2 + peaBrowAngry + peaBrowOther, 5, 2)
peaBrowSprite2 = thumby.Sprite(30, 10, peaBrow2 + peaBrowAngry + peaBrowOther, 72-35, 2)
peaBrowSprite2.mirrorX = 1
noseSprite = thumby.Sprite(15, 15, nose2, 29, 14, 0)
mouthSprite = thumby.Sprite(40, 15, mouth + mouthSmile + mouthSmile2 + mouthOh + mouthKissy + mouth3 + catMouth, 16, 26)


peaBallSprite = thumby.Sprite(20, 15, whiteOpenPea + whiteSquintyPea, 10, 7)
peaBallSprite2 = thumby.Sprite(20, 15, whiteOpenPea + whiteSquintyPea, 72-30, 7)

peaDotSprite = thumby.Sprite(7, 7, peaDot1, 12, 11)
peaDotSprite2 = thumby.Sprite(7, 7, peaDot1, 72-28, 11)
peaDotSprite.mirrorY = 1 # I just like it better upside down than how i originally drew it
peaDotSprite2.mirrorY = 1 # I just like it better upside down than how i originally drew it

faceSprCtr = 0
browSpriteCtr = 0
mouthSpriteCtr = 0

eyeDotlist = [12,12+2,12+5,12+5+2, 12+5+4] # list for set x coords for peaDots
eyeDotlist2 = [(72-28),(72-28+2),(72-28+5),(72-28+5+2),(72-28+5+4)] # list for set x coords for peaDots
# note for later, maybe move peaDots on Y when peaBalls are full

thumby.display.setFPS(8)
random.seed(time.ticks_ms())
while(True):
    thumby.display.fill(0)
    
    peaBallSprite.setFrame(faceSprCtr)
    peaBallSprite2.setFrame(faceSprCtr)
    peaBrowSprite.setFrame(browSpriteCtr)
    peaBrowSprite2.setFrame(browSpriteCtr)
    mouthSprite.setFrame(mouthSpriteCtr)

    thumby.display.drawSprite(peaBrowSprite)
    thumby.display.drawSprite(peaBrowSprite2)
    thumby.display.drawSprite(peaBallSprite)
    thumby.display.drawSprite(peaBallSprite2)
    thumby.display.drawSprite(peaDotSprite)
    thumby.display.drawSprite(peaDotSprite2)
    thumby.display.drawSprite(mouthSprite)
    thumby.display.drawSprite(noseSprite)

    
    
    t0 = 0                      # could've just slept for 4 
    ct0 = time.ticks_ms()       # but i thought maybe I'd do some smoother animations
    while(t0 - ct0 < 4000):     # just leaving it in for now to make it easier if 
        t0 = time.ticks_ms()    # i get inspired later 
    peaPos = random.randint(0, 4)
    peaDotSprite.x = eyeDotlist[peaPos]
    peaDotSprite2.x = eyeDotlist2[peaPos]
    faceSprCtr = random.randint(0,1)
    browSpriteCtr = random.randint(0,2)
    mouthSpriteCtr = random.randint(0,7)
    time.sleep(1)
    thumby.display.update()
