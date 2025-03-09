# OpAmp_optocompressor
Audio compressor with Operational Amplifier IC and photoresistor

The circuit is very simple. It uses a dual operational amplifier, which can be a TL072, NE5532, or any other op-amp with the same pinout. Power - bilopar +-15V

![image](https://github.com/user-attachments/assets/504e1d99-08ec-4e02-beb3-4a3514f0e6d9)

The first op-amp acts as a controlled amplifier. A photoresistor (VR1) is placed in its feedback loop—its resistance decreases as the light shining on it becomes brighter. In series with it is a potentiometer (R7), which will be mounted on the front panel and will determine the "compression" level: at high resistance, the op-amp's gain will be at its maximum. When R7 is set to 0 resistance, the gain will be entirely dependent on the signal amplitude.

The trimmer resistor (R5) is optional (that's why it's marked in blue), but if installed, it can be used to limit the maximum gain.

Additionally, you can see the input diodes marked in blue—they are also optional and primarily serve a protective function against excessive signal overload.

The second operational amplifier further amplifies the signal for the LED. After it, there is a buffer on a complementary transistor pair—this is necessary to allow the use of an ultra-bright LED. Following that, there is a diode bridge.

You may have noticed that the transistors are connected without biasing, meaning they operate in pure Class B. This is intentional. Unlike an amplifier output stage, where such a configuration would cause distortion at low amplitudes, here it establishes a threshold. In other words, until the signal reaches a certain amplitude (0.6V voltage drop across the transistor's PN junction + 0.6V drop across the diode bridge, totaling 1.2V), the compressor will not "intervene" in the signal.

After the diode bridge, there is a single smoothing capacitor (1µF). There is no dedicated soft release time control, but an additional 10µF capacitor can be connected if needed.
![image](https://github.com/user-attachments/assets/890d570a-bd08-4734-942d-f56192242962)
A few words about the optocoupler construction. It’s quite simple: take a piece of heat shrink tubing, insert an ultra-bright LED on one side and a photoresistor on the other. Then, fill it with glue—and that’s it!
The PCB has a designated spot for this component.
The tubing is essential; otherwise, ambient light will interfere with the operation!
![image](https://github.com/user-attachments/assets/49e0d0d8-7e94-4b83-ae53-a2331b69f551)
![image](https://github.com/user-attachments/assets/c9818300-e2a0-489b-906c-37117eebcfef)
I took several "raw" vocal recordings (without processing). I connected everything as described below: I fed the signal from the player to the compressor's input.
One channel of the audio interface was connected to the player’s output/compressor input - this gave me the "dry" signal.
The other channel of the audio interface was connected to the compressor's output - this gave me the "processed" signal.
![image](https://github.com/user-attachments/assets/77722582-5162-45a1-8890-175e4045ec32)

I normalized both channels to the maximum level so that the difference in the waveforms would be visually noticeable.
![image](https://github.com/user-attachments/assets/2b24e45e-2dd8-4f65-b0c9-8ccdd0171b2d)
![image](https://github.com/user-attachments/assets/774e0523-6557-40fa-b6d1-f7a2323053b2)
![image](https://github.com/user-attachments/assets/4ce704db-4d1e-4fcf-9ba3-2619ef12ecb4)
As you can see, the compressor works very "softly" and almost imperceptibly! It doesn't turn the wave into a typical "brick." Its intervention is also inaudible.
