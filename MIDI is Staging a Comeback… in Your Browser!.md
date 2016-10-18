MIDI is Staging a Comeback… in Your Browser!

With Jean-Philippe Côté

The MIDI format has been around for over 30 years. It’s in all kinds of hardware and software. It essentially is a format for sending messages that describe a note of music. There are variations, such as Show Control, that can be used to control AV. There are currently proposals in development for MIDI HD/2.0 and MIDI over Bluetooth.

Right now however we have the Web MIDI API!

[http://midi.org/articles/about-web-midi](http://midi.org/articles/about-web-midi)

This API has been available in Chrome since version 43. Also in Opera and Chrome on Android. IE/Edge currently have no development plans, while Firefox is working on the implementation.

[http://caniuse.com/#search=midi](http://caniuse.com/#search=midi)

There are plugins available which can bring support where needed.

You can create things like MIDI controlled effects, such as a vocoder written with the Web Audio API. There are web based editors and librarians with integration into Roland hardware. People have made web based synths and drum machines. Or use a Korg Mini Key plugged into USB that controls a Web Audio synth.

There is a polyfill which will fallback to the plugins if the API isn’t available.

[http://cwilso.github.io/WebMIDIAPIShim](http://cwilso.github.io/WebMIDIAPIShim)

You can send MIDI out to other software running locally by mapping your software ports appropriately.

The stock Web MIDI interface uses a format like this:

synth.send(status, note, velocity) where the parameters are integers. This is a pain.

To counter this difficulty, Jean-Phillippe has written a high level API to make it easier for a musician to work with Web MIDI. You simply get the device by name, and then:

playNote(‘C#’);

[http://github.com/cotejp/webmidi](http://github.com/cotejp/webmidi)

Demo Time!

Jean-Philippe restored an Octapad from the 80’s - replaced all the trigger switches. Plugged it into an old Midiman MIDI to USB adapter.

Used tone.js to control the Web Audio API and snap.svg to do some SVG animation.

Then he proceeded to play Tone Loc. Nice!

Visit [http://tangiblejs.com/slides/webu2016/midi-is-staging-a-comeback-in-your-browser/](http://tangiblejs.com/slides/webu2016/midi-is-staging-a-comeback-in-your-browser/) for the slides.

