# KMeter-macOS
![KMeter Mac Icon](https://cloud.githubusercontent.com/assets/143885/14838710/d68dd266-0bd8-11e6-9944-1c03d2b11185.png)
A macOS version of Martin Zuther's Excellent K-Meter. Includes a standalone application and two plug-in formats: VST and AU. This version supports stereo (not 5.1) only. If you want 5.1 let me know. These versions all include the needed skin files inside the packages so you no longer need a second kmeter folder. 

If you don't know what a K-Meter is check out [Martin's site](http://www.mzuther.de/en/software/kmeter/) for all the details. For now, this repo just has the binaries of the Macintosh OSX version I created. At the time I built this the macOS version 10.11.4 (El Capitain). I have been using it without issue on High Sierra.See below if you use an older version of macOS

Download Zip the project and unzip it.  Then unzip K-Meter-Dist.zip and it will contain:
* KMeter_manual.pdf
* K-Meter (the standalone version)
* K-Meter.component (the AU version)
* K-Meter.vst (the vst version duh)


## Standalone
 ![Standalone Image](https://cloud.githubusercontent.com/assets/143885/15167394/6ac8d368-16dd-11e6-9bb8-99bfbe257053.png) Drag the file into your Applications folder. That's it.  Double-click the K-Meter application and it should launch. Use the _options_ button in the upper left corner and select _Audio Settings..._ to set your input source. Start with something simple like your microphone. Select the K-20 button, enable peaks and set your volume. 

If you want to measure the loudness output of your system audio, say from a tool like Camtasia, then you'll need a tool like Soundflower that can make your output into an input. Then instead of a microphone you just select Soundflower as the input to the meter. **Warning** after experimenting with Soundflower and Loopback, they are corrupting my system audio in some weird way. The only way I could recover was from a backup. 

## AU Plugin
AU (Audio Units) are the native format for the Mac. The AU version can be used with any hosting program that supports the AU format, e.g. a DAW like [Reaper](http://www.reaper.fm/). Take the *K-Meter.component* and  move it to any folder that your host scans for AU plugins. The default location on a Mac _(that all hosts should scan by default)_ starts at the user library (i.e. ~/Library). Open a finder window. Hold down the **Option** key and click the **Go** menu and select **Library**. _The user library on the Mac is hidden by default, that's why you hold down the **Option** key._ Once that window opens navigate to:  
**Audio->Plug-ins->Components**   
and drag the **K-Meter.component** file there.  

## VST Plug-in
The VST version can be used with any hosting program that supports the VST format, e.g. a DAW like [Reaper](http://www.reaper.fm/). Take the *K-Meter.vst* and move it to any folder that your host scans for VST plugins. The default location on a Mac _(that all hosts should scan by default)_ starts at the user library (i.e. ~/Library). Open a finder window. Hold down the **Option** key and click the **Go** menu and select **Library**. _The user library on the Mac is hidden by default, that's why you hold down the **Option** key._ Once that window opens navigate to:  
**Audio->Plug-ins->VST**   
and drag the **K-Meter.vst** file there.  

## Example Usage 
Now start your DAW or rescan the folder. Here are some details on how to use the K-Meter with Reaper:   

1. Click in the **Fx** box in the master track area of Reaper. 
2. In the resulting dialog make sure _All Plugins_ is selected at the top. 
3. In the filter area at the bottom type k-meter. 
4. You should now see **VST: K-Meter (Stereo) (Martin Zuther)** or
5. **AU: Martin Zuther: K-Meter** (or possibly both if you installed both versions)
5. Double Click that to add it to the Master Track FX panel. 
6. Double click it again in that panel to put it in a floating window. 
7. Position that floating window just to the left of your main Reaper window. 
8. Now save a new project template because you're going to want this meter to open every time you start a new project. Trust me. 

### Older versions of OSX
In the latest version I set XCode to delpoy the VST and AU versions for 10.4 (or later) and the standalone version of 10.5 (or later). The problem with this is I don't actually have SDKs for 10.4 and 10.5. If I did and I set the base SDK I assume I would get compiler or linker errors if I tried to use an API from a more recent OS release. It's not just the code in the meter that is of concern if the FFT library or the JUCE library uses anything later than the OS you are running on, the meter simply won't work. I don't believe there is anything I can do about that. If you have any luck or trouble running the standalone or plug-in versions on pre OSX10.11 let me know.

### Want to Know More?
Read the K-Meter.pdf manual. 

### Just How Geeky Are You?
There is a also a folder of sound files and documentation that allows you to validate the meter. I didn't include it because it adds 12 MB to the download. You can get all of this from Martin's site.  

### For the Terminally Curious
The standalone version doesn't look like a normal Macintosh application. The entire project (VST and Standalone) relies on the [JUCE framework](https://www.juce.com/). The program also uses the [Fastest Fourier Transform in the West (fftw)](http://www.fftw.org/) library.  

####Licensing
The software is distributed under the GNU GENERAL PUBLIC LICENSE (see the LICENSE file). The Mac icons (see the K-Meter.icns file) is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International license](https://creativecommons.org/licenses/by-sa/4.0/). 
