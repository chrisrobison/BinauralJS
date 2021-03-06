BinauralJS
==========

<p>A Javascript/CoffeeScript library for generating binaural beats using the Web Audio API. <a target="_blank" href="http://htmlpreview.github.com/?https://github.com/ichabodcole/BinauralJS/blob/master/example/app.html" title="NoiseGenJS Demo">DEMO</a><br>
More on binaural beats <a target="_blank" href="http://en.wikipedia.org/wiki/Binaural_beats">Here</a></p>

### Basic Usage
    // Create a new AudioContext to connect to
    var context = new webkitAudioContext()

    // Create a BinauralBeat instance, options is a hash with the below defaults if nothing is provided.
    var bBeat = new BinauralBeat(context, options{frequency: 440, beatFrequency: 5, waveType: 0, compressNodes: false});
    
    // Create a new gain node to control volume
    var volume = context.createGain();

    // Connect to the BinauralBeat node to the gain node
    bBeat.connect(volume)
    
    // Connect the gain node to the context output.
    volume.connect(context.destination)

    // Control volume like this
    volume.gain.value = .8
