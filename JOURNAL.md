# NOAAmp - Reliable Signal Gain for NOAA Reception

## Made by: @Scooter Y

### Day 1 - Friday June 6th - 5.5 hours

This was when it all started.... I was looking into what my next PCB that I should build, and I saw that you can receive weather photos from NOAA satellites (Lets be real for a second, that's just photos from SPACE! Even cooler!). I knew I needed to build one, but didn't know where to start, and didn't realize how complex it can be. I started off like anyone would do- research parts to use. My plan originally was to build something called an RTL-SDR, which pretty much is a small-ish dongle that can receive radio signals from antennas, and convert it to a WAV file for my PC to interpret live. After a few minutes of research I figured out that it's a LOT harder than it seems; I decided to only build an amplifier for it. Since the signal is so weak, we need to amplify it a lot to get a readable output- this is what my project does. 

I started off trying to find an IC for amplifying... Apparently, that's harder than it seems, since there aren't many available ones for the needed 137MHZ. I ended up going with the MAX2659ELT+T which at that time I though was the right IC. 

![image](https://github.com/user-attachments/assets/a0114017-0397-4400-8471-358103d41259)

(This is what the schematic looked at that time)



After that, I decided I wanted to add the ability to switch between freq to allow other satellite signals to reach the amplifier too, and not just my intended NOAA-19. After a few minutes of wiring it it up, I realized the super small changes in freq bands ie. 1337.1 to 137.9 were too small for me too do at my capabilities, so I had to scratch that.

![image](https://github.com/user-attachments/assets/ecfe8731-8dc5-49f6-a7f1-f60c92b0623c)

(This is what the schematic looked at that time with RF switching)



Lastly, for Friday, after wiring up the whole schematic, I sent it over to my friends to double check, and low and behold, the IC I selected was for 2.4GHZ and it would have had negative amplification for 137MHZ. Woops. I was a little annoyed that I spent a long time wiring this, but it never worked out, but that's how it works... you learn from your mistakes. I will come back to it on Sunday to fix.

### Day 2 - Sunday June 8th - 6.5 hours

After de-stressing for a few days, I can back to finish it. I swapped out the bad IC for the GALI-84+ which would work perfectly fine for my needs. If only the wiring for the original IC was as easy as this one.... I spent a nice 4 hours straight trying to figure out how to wire it all up properly. The datasheet was definitely not the most useful one I've seen. For example, pin 3 wanted DC-IN and RF-OUT all on the same pin :man_facepalming:. I finally found a proper application datasheet with a proper example, and after customizing it too say the least, and adding an RF Choke to it (the ADCH-80A+), I FINALLY got the schematic done!!



![image](https://github.com/user-attachments/assets/9dac4db9-cef9-4c4c-bd07-385a7fcbbb1b)

(Final schematic. Even though it looks a lot smaller, it took me a long time to find all the correct values, and where everything goes)



Thank goodness the routing was nice and easy. It took me like an hour or two to route the whole board including being careful for sensitive RF routing and properly ground stitching the board. After checking my routing 9 million times, I finally came to the conclusion that I was done! No more double checking everything to find it wrong, it's finally done, and we all hope it works first try!!



### Some photos

![image](https://github.com/user-attachments/assets/f9c37f93-744a-4c16-8816-4004f9a91592)

(The final PCB route with ground stitching, not including a ground pour on all 2 layers)



![image](https://github.com/user-attachments/assets/41b08674-415e-472c-8300-dd7b8c5aee94)

(What my PCB will look like with ray-tracing enabled in KiCad)


### Day 3 - 11 hours - Wednesday June 11th

Even before reading this, I know what your thinking, 11 hours in one day is insane- how did you do it! To be honest, I'm not fully sure, but I'm guide you through what I at least did on that day. Pretty much on this day, all I did was CAD (yes, only CAD!). I decided I wanted to use Fusion 360 to design my enclusoure, but little did I relize the pain I was going to go through to design it. I chose Fusion 360 as it was what I was most familiar with. I knew I wanted a cool case with a cool usb-c entry! Even though I felt fairly confident in my Fusion 360 skills, I never really developed my own custom enclousure before.
Once, I built my case, I knew it needed some pizazz, so I decided to use the Fillet tool. The end outcome ended up looking like the image below:

![image](https://github.com/user-attachments/assets/2241278a-f99a-42ac-b2ac-425e8c52620f)
(Pretty sick, eh?!)

After the fillet, I knew I wanted it to be water-tight since it will be held outside 24/7, so what better way then to add screws to the case! I decided on using these threaded screws as they were the right side and width for my case- https://www.mcmaster.com/91864A002/?utm_term=socket+head+screws&location=9000797&matchtype=p&placement=&gad_source=1. 

After a WHOLE LOT of different changes, and a full day of re-learning Fusion 360:

![image](https://github.com/user-attachments/assets/59c56504-b0f8-438c-964a-1752fcf7e7b6) ![image](https://github.com/user-attachments/assets/c4e7c277-89f3-4c87-b87d-15a7bf71ff8e)

I present to you..... my NOAAmp enclousure!!

![image](https://github.com/user-attachments/assets/465c002c-5043-4e34-a0df-7e49cdfd4507)
![image](https://github.com/user-attachments/assets/ecc283c7-1eb0-45be-8ef2-bd89f4903bf2)
![image](https://github.com/user-attachments/assets/3722d72e-510c-45aa-a280-47178862b755)

This whole case definitely re-taught me like half that Fusion 360 offers, and made an awesome case for it!! (Why is it square you may ask... beacuse when it was rounded, the screw holes were going through the sides, and I was too lazy to just make the walls bigger ;))
