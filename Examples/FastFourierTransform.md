[back to Index](Index.md)

# Fast Fourier Transform

One of math use cases in advanced Electronic Engineering is the *Fast Fourier Transformation*.  
The basic idea behind is, that we have an math algorithm, with translates a signal from time domain into an equivalent in frequency domain.

Actually, we are not working on the signal itself, but rather on a number of samples of the original signal in equidistant points in time and convert it to a series of frequency samples. Or, vice versa, convert frequency samples into time domain. 

**Fast Fourier Transform** is an algorithm, which implements a *Discrete Fourier Transform* (DFT), and the inverse is called *Inverse Discrete Fourier Transform* (IDFT). So don't be confused by the different terms.

You may have seen this in practice on a *vector network analyzer*, which is able to do present signals also in time domain, or a on a *spectrum analyzer*. May be your *oscilloscope* provides this function as an software add-on to present the spectra of an periodic signal.

Naturally, all of this works on *complex numbers*. If you're not yet familar with *complex numbers*, you should start by reading on those first and come back later.

# A first example




[back to Index](Index.md)
