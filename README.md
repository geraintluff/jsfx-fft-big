# Large FFTs for JSFX

The FFT function [in REAPER](http://www.reaper.fm/sdk/js/advfunc.php#fft) only supports sizes up to 32768 (complex pairs).

For longer FFTs (such as required by [PadSynth](https://github.com/geraintluff/jsfx-pad-synth)), you can calculate the FFT as a combination of shorter FFTs (Cooley-Tukey factorisation).

## How to use:

You can either include it, or copy the functions from `fft_big.jsfx` into your code.

```
fft_big(block, N, working_space);
ifft_big(block, N, working_space);
```

The results of these functions are *in order* - that is, there is no `fft_big_permute()` function because that's already included in `fft_big()`.

The implementation (currently) requires some free memory to use for intermediate values, which is passed in as the `working_space` parameter.  This working space needs to be 256 slots long.

## License

Do whatever you want with this code, just don't blame me. :)  Bug reports appreciated.