# Dual-decision task

This repository contains the code for the experiments reported in the paper [_"Discrete confidence levels revealed by sequential decisions"_](https://doi.org/10.1038/s41562-020-00953-1), by Lisi, Mongillo, Milne, Dekker & Gorea.

Type `launcher` to launch the experiment. The order of the two tasks (i.e. whether orientation or motion is first) is randomized depending on the number of the participant.

Once launched, the program will prompt for some info, including whether the current session is control or dual-decision condition. In the control task the two decision are independent, whereas in the dual-decision the sign of the second stimulus will depend on the accuracy of the first response; see [the paper](https://doi.org/10.1038/s41562-020-00953-1) for mode detailed explanation of the rationale.

After having done few control session with a participant, you can move on to the dual-decision sessions. To do so we need an estimate of the internal noise of the participant. This is calculated automatically once you launch a dual-decision session, using all previous session. Note that in its current implementation all previous consecutive session number must be present; alternatively one can calculate the noise manually using the `check_noise` function. This can be used as

```{matlab}
addpath('./functions')
check_noise('01ml', [1, 2])
```
which will estimate noise for subject `01ml` using data from session 1 and 2. It will also make a plot of the psychometric functions, from which one can judge the extent of any bias. 

Note also that screen settings should be adjusted according to the display used (see `./functions/prepScreen.m`).


