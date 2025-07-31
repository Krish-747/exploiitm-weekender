# Exploiitm Weekender CTF Challenge

## Question 1
[Q1](/Q1.png)

The original code is `lewsvppat{3a_Ab_iYbAl_w_kog_ghoppsr_23_hwasg}`. We also see that the final answer should be in the format of `exploiitm{...}`. Furthermore, the poem talks about an emperor, so we can infer that this is most likely a Ceasar Cipher. 

Now if you correspond `lewsvppat` and `exploiitm`, we can see that each letter is shifted backwards by 7 letters. We can also infer that `_` means ` `. We will ignore the numbers and assume that a capital and a small letter correspond to the same code with the same capitalisation. 

If you decode this using the above ceasar cipher, you get `exploiitm{3t_Tu_bRuTe_(some random gibberish)}`. To decode the some random gibberish let us try using another ceasar cipher. We can see the number 23 and we also know that Julius Ceasar was stabbed 23 times. With this we can try to infer that `hwasg` corresponds to `times`. By following that assumption, we can figure out the shift is 12 letters forwards and the _gibberish_ part decodes to `i_was_stabbed_23_times`

By combining both parts you get `exploiitm{3t_Tu_bRuTe_i_was_stabbed_23_times}` and the first flag is captured. 

## Question 2
[Q2](/Q2.png)

Now here, the audio sounds like absolute garbage (like nikhil's voice). However putting the audio through a spectrum analyser and voila
[Spectrum](/Q2%20Spectrum.png)

If you dont have any eyes, this is the flag `exploiitm{b0o_h@Ha_5c@r3d_Y0u_d1dnt_I}` and second flag is captured.

## Question 3
[Q3](/Q3.png)
The poem suggests us to check the source code. Upon checking the source code, you get the following code.
[Q3 Source code](/Q3%20Source%20Code.png)
You can see that the entire text block is being converted to lowercase. Only some letters are in uppercase which means that they are most likely the code. Inspecting those uppercase letters you get "ACROSTIC". According to the instructions, the third flag should be `exploiitm{acrostic}` and it is captured.

## Question 4
[Q4](/Q4.png)
The poem suggests us to twist the scale of dark and light, which means changing the contrast of the image. By changing multiple parameters you get the following image

[Picture](/Q4%20Picture.png)
The fourth flag should be `exploiitm{n3v3r_g0nn4_g1v3_u_up}` and we move onto the 5th question

## Question 5
[Q5](/Q5.png)
With the poem we can infer that they are referring to the location of the famous third elephant of the Gajendra Circle. Searching for the "third elephant" on Google Maps and right clicking the pin yields the following result 

[Maps](/Q5%20Maps.png)
Following the instructions, you get the flag as `exploiitm{12.995_80.236}` and with that over we move onto the last question.

## Question 6
[Q6](/Q6.png)
[Source](/Q6%20Source.png)

Now we first must understand what the original code does. In the **for loop** section we can see that each letter from the `flag` is converted into the unicode format (using the `ord` function). After that we take the unicode character and raise it to the power of `t` and take moduluo of it with `N`.

To solve this, we will follow a similar way. First we take an element from `l` list, and check if it is the same as `pow(character, e, N)`. We go through every single possible ASCII Character (32 - 127) and if it matches with the item from `l`, we append it to the flag variable.

Finally we combine it into a string and we can print it out. The final flag is `exploiitm{7W1N_Pr1M3_r54_15_UN53CUr3}` and it is captured.