# Play .wav files on Arduino without an SD card

Usually when you're trying to play .wav files on an Arduino Uno, you'll need a SD card module because the Arduino cannot play sounds that are longer than 4s.

However, if you want to play around with shorter sounds, you can upload them onto your Arduino without having to buy an SD card shield.

If your .wav file is in iTunes, go through the following steps:

* go to Preferences > General Tab.
* click 'import settings'.
* select 'custom' from the 'setting' dropdown.
* Inside the custom settings, enter the same settings as below:

[](http://highlowtech.org/wp-content/uploads/2011/12/iTunes-mp3-settings.png)

* click ok on everything.
* Right-click on the audio you want to convert and select 'create MP3 version'.

After this, you're gonna have to convert this new 8KHz sound to numeric values so it can be interpreted by the Arduino.
To do this, you can download a software called EncodeAudio, and select your newly converted audio file. Once the program has finished encoding it, it will copy it to your clipboard automatically so you can paste it in your code.

Now, to be able to use it with your Arduino, you have to download the [PCM library for Arduino](https://github.com/damellis/PCM/zipball/master).

Once this is downloaded, rename it to just 'PCM' and add it to the libraries folder where you usually have your other Arduino libraries.
You'll probably have to restart Arduino to be able to see it in the 'include library' dropdown.

After this, re-open Arduino, go to File > Examples > PCM and click on the playback example.

Where you see the array of numeric values, delete them and replace them with the ones you just copied to your clipboard.

Once you get a speaker connected to your Arduino on PIN 11, you can upload the sketch and you should hear your sound!

Of course, using a SD card module or a sound board would be better but if you don't have one right now, it's a good way to prototype stuff!
