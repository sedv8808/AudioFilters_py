# Audio Filters for Python

Python project for sound convolutions

### Contributors

- [Marcelle Chiriboga](https://github.com/mchiriboga)
- [Paul Vial](https://github.com/Pall-v)
- [Socorro Dominguez](https://github.com/sedv8808)

### Overview

Have you ever wondered how you could edit your audio files using filters to speed them up to save some time or maybe speed them down to listen more carefully? The purpose of this project is to create a package to address this kind of need, and it's also possible to go even deeper.

This package performs audio processing on .wav files. It contains functions which apply 1D convolutions using a simple kernel array to do some interesting transformations on the original audios, such as: changing their speed, applying effects and attenuating the signal for specified frequencies.

### Usage

All three functions expect a numpy array of integers or floats as the input_signal and can be used as follows:

##### Change speed

```
from audiofilters.change_speed import change_speed

# Use a number greater than one to speed up the file
signal_faster = change_speed(input_signal, 2)

# Use a number between 0 and 1 to slow down the file
signal_slower = change_speed(input_signal_norm, 0.5)
```

##### Low Pass Filters

```
from audiofilters.low_pass_filter import low_pass_filter

# Use 1000 as the cutoff_frequency to attenuate all frequencies above that
signal_attenuated_above_1000 = low_pass_filter(input_signal, 1000)
```

##### Reverb

```
from audiofilters.reverb import add_reverb

# Use 'hall' to add a reverb effect that simulates a hall-like recording environment
hall_reverb = add_reverb(input_signal, 'hall')

# Use 'church' to add a reverb effect that simulates a church-like recording environment
church_reverb = add_reverb(input_signal, 'church')
```




### Installation Instructions

In order to install the package, run the following command from terminal:

`pip install git+https://github.com/UBC-MDS/AudioFilters_py`

Then, import the functions that you need.

The package has the following dependencies:
- librosa
- numpy

### Package Functions

###### change_speed
This function changes the audio speed, speeding up or down an audio signal.

###### add_reverb
This function applies an effect to an audio signal so that it sounds like it was recorded in a different environment.

###### low_pass_filter
This function attenuates audio frequencies above a specified cutoff level.

### Python Ecosystem

[Pyo](https://github.com/belangeo/pyo) is an existing Python module that provides a variety of audio signal processing type, including [reverb](http://ajaxsoundstudio.com/pyodoc/examples/07-effects/02-schroeder-reverb.html?highlight=reverb) although it is for a specific type of reverb which we do not plan to implement.  The functionality to be implemented by our system will also include functions for changing speed and low-pass filtering which are not found in Pyo.  We do not plan to use any digital signal processing packages.  We plan to code the convolutions mathematically within the functions so that they are easily testable and interpretable.  We will make limited use of other packages to represent waveforms, and input/output as necessary.
