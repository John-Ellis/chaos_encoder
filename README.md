## Chaos Encoder

Building on the work of [Cuomo, Oppenheim, and Strogatz who implimented a synchronized chaotic system to mask a low amplitude signal under high amplitude noise.](http://engineering.nyu.edu/mechatronics/Control_Lab/bck/VKapila/Chaotic%20Ref/Porfiri's/Biblio/cuomo93.pdf) 

Here we are implimenting a digital version of the same encoding scheme.

### Method:

Given an example directory containing an initialization file and a source signal file the main program intializes the clock to the first timestamp in the source and initializes both the decoder and encoder based on the corresponding initialization file.

For every signal clock value the clock computes a delta_T to be used by the system models. The encoding system is updated, it's one component of it's output vector is summed with the signal and passed to the decoding portion.

The decoding system similarly updates itself based on delta_t and it's previous state. Then by subtracting the corresponding output component and signal from the previous time step we can recover the signal at the current timestep.

However to achieve and maintain coupling the output component must be overwritten with the encoded stream.