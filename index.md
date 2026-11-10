# DSC 180A Methodology Assignment 4

**Name:** Alisha Wang
**Email:** alw054@ucsd.edu

**Section:** D03
**Mentor:** Professor Benjamin Smarr

## Quarter 2 Project Brainstorm

**What is the most interesting topic covered in your domain this quarter?**

The most interesting topic for me was how the common assumption that female animals are "too variable" to study holds up against real data. When we replicated Smarr & Kriegsfeld (2022) on 13 male and 13 female mice, male mice were actually less consistent from day to day in body temperature, and dynamic time warping (DTW) showed this better than a simple minute-by-minute comparison because it can align daily patterns that shift slightly in timing. I also found it interesting that the DTW warping path, which most studies ignore and only report the distance, ended up carrying the clearest estrus signal in our work: temperature patterns ran later on estrus days.

**Describe a potential investigation you would like to pursue for your Quarter 2 Project.**

We are getting a new mouse dataset with richer information than the one we used this quarter, and I would like to test whether our estrus-detection approach holds up on it. The first question is whether the DTW time-shift and wavelet features we built this quarter still separate estrus days in a new set of mice, or whether they only worked on the 13 females we studied. Then I would use the extra information in the new data to check where our current features fall short and add new ones. If that works, I would like to move from labeling estrus days after the fact to predicting the next estrus day from the days before it.

**What is a potential change you'd make to the approach taken in your current Quarter 1 Project?**

Our estrus labels are assumed from a regular 4-day cycle rather than measured, so a classifier can only be as good as that assumption. I would change the approach so it doesn't depend on those labels, for example by using a method that finds the repeating cycle in each mouse's own data, and then check how well the result lines up with the assumed schedule. I would also compare our DTW time-shift feature against simpler timing measures, such as the time of the daily temperature peak or a cross-correlation lag, to show whether DTW's flexible alignment actually adds something.

**What other techniques would you be interested in using in your project?**

I'm interested in hidden Markov models, since the estrous cycle moves through phases in order and an HMM could model that sequence instead of treating each day separately. I would also like to try mixed-effects models to account for differences between individual mice, and cosinor analysis as a simpler baseline for circadian rhythms. If there's enough data, a small 1D convolutional neural network on the raw minute-level signals would be a good comparison against our hand-built DTW and wavelet features.
