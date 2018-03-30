# Segmented-Gaze-Control
Segmented and Gaze Controlled Decompression for Streaming Displays such as a VR.

To formally describe the project – 
1.	Sematic Layering of video: there is a pre processing step where you will analyze the input video, break it into foreground/background layers. This is not required to work in real time, and semantic accuracy may vary.

The program demarcates foreground/background with good relative accuracy. An example of such an output shown below where the green macroblocks represent the background and the red/blue macroblocks represent the foreground elements.

<img width="538" alt="screen shot 2018-03-29 at 11 42 29 pm" src="https://user-images.githubusercontent.com/23444062/38127898-071c35c8-33ad-11e8-8e2f-3e8336a6bd0c.png">

2.	Compressing of layers: Each of the foreground/background layers will need to be stored in a compressible manner so that later access can  decide what needs to be read/streamed to the player and displayed.  This is not required  to work in real time, and file format for storing the data is up to to you to decide – though an example file format has been suggested.
3.	Displaying of video: Your player should read the compressed video file and display the video per quantization inputs to simulate bandwidth distribution among layers. Foreground layers should be ideally more clearly visible than background layers.

<img width="598" alt="screen shot 2018-03-29 at 11 57 37 pm" src="https://user-images.githubusercontent.com/23444062/38127901-0978af36-33ad-11e8-9f0c-68514cfcbce7.png">

4.	Applying gaze control: We don't have Head mounted VR displays to work with to see the value of this  effect, but we can certainly simulate gaze based control by using a mouse pointer. With your mouse location acting as "gaze direction" you want decode/display a local area around the mouse location will the best clarity (no quantization) compared to other layered areas.

