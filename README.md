<img width="1920" height="1080" alt="Screenshot (127)" src="https://github.com/user-attachments/assets/fd8360d1-2ea1-462c-b6ce-5b5d774ec6d5" />
<img width="1920" height="1080" alt="Screenshot (126)" src="https://github.com/user-attachments/assets/cb1e59d5-f0c1-4f4f-a55f-587c9ea4a33d" />
<img width="1920" height="1080" alt="Screenshot (125)" src="https://github.com/user-attachments/assets/614c02c3-f1f0-4813-999e-16510012fe04" />
<img width="1920" height="1080" alt="Screenshot (124)" src="https://github.com/user-attachments/assets/6e957775-7b7c-4e07-a654-4c933cc1b482" />
# Lecture2-Hearing-and-Seeing-Aliasing
Results table

Sampling frequency	Nyquist frequency	Observed peak	Aliasing
24 kHz	12 kHz	7 kHz	No
16 kHz	8 kHz	7 kHz	No
12 kHz	6 kHz	5 kHz	Yes
8 kHz	4 kHz	1 kHz	Yes

The aliased peak is the sampling frequency minus the signal frequency: 12 − 7 = 5 kHz, and 8 − 7 = 1 kHz.

Answers

Which sampling frequencies represented the 7 kHz signal correctly?
24 kHz and 16 kHz. Both meet the Nyquist condition fs ≥ 14 kHz, so the peak stayed at 7 kHz.
When did the 7 kHz signal appear as another frequency?
At 12 kHz it appeared as 5 kHz, and at 8 kHz it appeared as 1 kHz.
What happened when the Nyquist frequency became lower than 7 kHz?
The 7 kHz component could no longer be represented. It folded back below the Nyquist frequency and appeared at fs − 7 kHz. This false lower frequency is aliasing.
Did the aliased signal sound different?
Yes. The 12 kHz version sounded lower in pitch (5 kHz), and the 8 kHz version sounded much lower (1 kHz). Both were clearly different from the original 7 kHz tone.
Why can MATLAB not recover the original 7 kHz signal after aliasing?
After sampling, the samples of the 7 kHz tone are identical to the samples of the alias frequency (5 kHz or 1 kHz). The information that the tone was originally 7 kHz is lost, so no processing can tell the two apart. Aliasing has to be prevented before sampling, using a low-pass anti-aliasing filter or a high enough sampling rate.

Conclusion: A signal must be sampled at more than twice its highest frequency (fs ≥ 2·fmax). Otherwise high frequencies fold back and appear as false lower frequencies.
