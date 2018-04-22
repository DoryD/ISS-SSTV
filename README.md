# ISS-SSTV
Receiving images from space - pretty cool, right? 
With a little know how and some solder anyone can do this!

#### Step 1: The Antenna.
Your antenna will be the most important part of receiving signals, so let's start there. 

Hands down the easiest antenna for this job is going to be [Adam 9A4QV's V dipole](https://www.dropbox.com/s/6fpfn2p9filc9ol/DIY%20137MHz%20WX-sat%20V-dipole%20antenna.pdf?dl=0) 

(from rtl-sdr.com) 
>"The idea is that by arranging a dipole into a horizontal ‘V’ shape, the radiation pattern will be directed skywards in a figure 0 (zero) pattern. This will be optimal for satellites travelling in front, above and behind the antenna. Since polar orbiting satellites always travel North to South or vice versa, we can take advantage of this fact simply by orienting the antenna North/South."

<img src=https://upload.wikimedia.org/wikipedia/commons/d/dd/Dipole_receiving_antenna_animation_6_800x394x150ms.gif>

There is a lot of technical information in that document, but all you really need is this image to get started <img src=https://www.rtl-sdr.com/wp-content/uploads/2017/03/adams_V-dipole-500x375.png>

Connect the centre part of the coax to one leg, and the sheilding to the other, spread apart 120° and secure it in place in the horozontal position like i've done here. 

IMAGE

#### Step 2: Receiving

Using an ISS tracking website like [N2YO](http://www.n2yo.com/?s=25544) determine when the ISS will the the absolute closest possible to your location - note that "visible passes" are only relevant for astronomy and some "invisible passes" might be much closer than the visible ones. 
<img src=https://i.imgur.com/iWO8j5U.png>

Tune GQRX to 145.8MHz and wait until you start to see a signal, set your program to WFM and narrow it down to about 16kHZ bandwidth then start piping/recording the audio with your preferred method. NFM in GQRX adds in filters designed for receiving voice which will degrade the image you are trying to receive. You may also need to widen the bandwith to 20kHZ to adjust for doppler shift if you're images are coming in really choppy, manually adjusting the frequency as the shift occurs is another option.

<img src=https://i.imgur.com/0nWsfoB.png>

#### Step 3: Decoding

The best program for the job in linux is [slowrx](https://github.com/windytan/slowrx) [(AUR)](https://aur.archlinux.org/packages/slowrx-git/) Select "PD-120" and start piping the audio into the program (I used pulseaudio for this)
<img src=https://i.imgur.com/6NncNWM.jpg> 
Wait for the image to fully decode and maybe mess with some of the filters for a few tries and congratulations! You successfully decoded an image from the ISS.

<img src= https://i.imgur.com/MG2QOA4.jpg>
