# NOAAmp - Reliable Signal Gain for NOAA Reception

## Made by: @Scooter Y

### Day 1 - Friday June 6th - 5.5 hours

This was when it all started.... I was looking into what my next PCB that I should build, and I saw that you can receive weather photos from NOAA satellites (Lets be real for a second, that's just photos from SPACE! Even cooler!). I knew I needed to build one, but didn't know where to start, and didn't realize how complex it can be. I started off like anyone would do- research parts to use. My plan originally was to build something called an RTL-SDR, which pretty much is a small-ish dongle that can receive radio signals from antennas, and convert it to a WAV file for my PC to interpret live. After a few minutes of research I figured out that it's a LOT harder than it seems; I decided to only build an amplifier for it. Since the signal is so weak, we need to amplify it a lot to get a readable output- this is what my project does. 

I started off trying to find an IC for amplifying... Apparently, that's harder than it seems, since there aren't many available ones for the needed 137MHZ. I ended up going with the MAX2659ELT+T which at that time I though was the right IC. 

![image-20250608160424663](C:\Users\Scooter\AppData\Roaming\Typora\typora-user-images\image-20250608160424663.png)

(This is what the schematic looked at that time)



After that, I decided I wanted to add the ability to switch between freq to allow other satellite signals to reach the amplifier too, and not just my intended NOAA-19. After a few minutes of wiring it it up, I realized the super small changes in freq bands ie. 1337.1 to 137.9 were too small for me too do at my capabilities, so I had to scratch that.

![image-20250608160820727](C:\Users\Scooter\AppData\Roaming\Typora\typora-user-images\image-20250608160820727.png)

(This is what the schematic looked at that time with RF switching)



Lastly, for Friday, after wiring up the whole schematic, I sent it over to my friends to double check, and low and behold, the IC I selected was for 2.4GHZ and it would have had negative amplification for 137MHZ. Woops. I was a little annoyed that I spent a long time wiring this, but it never worked out, but that's how it works... you learn from your mistakes. I will come back to it on Sunday to fix.

### Day 1 - Friday June 6th - 6.5 hours

After de-stressing for a few days, I can back to finish it. I swapped out the bad IC for the GALI-84+ which would work perfectly fine for my needs. If only the wiring for the original IC was as easy as this one.... I spent a nice 4 hours straight trying to figure out how to wire it all up properly. The datasheet was definitely not the most useful one I've seen. For example, pin 3 wanted DC-IN and RF-OUT all on the same pin :man_facepalming:. I finally found a proper application datasheet with a proper example, and after customizing it too say the least, and adding an RF Choke to it (the ADCH-80A+), I FINALLY got the schematic done!!



![image-20250608161927714](C:\Users\Scooter\AppData\Roaming\Typora\typora-user-images\image-20250608161927714.png)

(Final schematic. Even though it looks a lot smaller, it took me a long time to find all the correct values, and where everything goes)



Thank goodness the routing was nice and easy. It took me like an hour or two to route the whole board including being careful for sensitive RF routing and properly ground stitching the board. After checking my routing 9 million times, I finally came to the conclusion that I was done ![yay](C:\Users\scooter\Downloads\yay.gif). No more double checking everything to find it wrong, it's finally done, and we all hope it works first try!!



### Some photos

![image-20250608162320137](C:\Users\Scooter\AppData\Roaming\Typora\typora-user-images\image-20250608162320137.png)

(The final PCB route with ground stitching, not including a ground pour on all 2 layers)



![image-20250608162417123](C:\Users\Scooter\Roaming\Typora\typora-user-images\image-20250608162417123.png)

(What my PCB will look like with ray-tracing enabled in KiCad)