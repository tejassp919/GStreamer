# Readme

This application is designed to help us play any video available online through its URL. It implements basic funcctionalitites like pause, play and seek which can be accessed using terminal input. It also allow us to change audio streams though terminal input. 

## Input format

Initially the application will tell us the details of all available stream. We can switch between differet audio streams through commands in format of "a x", replace x with the index of the audio stream you wish to play. ex "a 0" will set audio stream to 0th index stream.

We can then pause and play the stream by giving commands "p" and "c" respectively. We can seek forward by any amount by giving the command "s f x", replace x with number of seconds by which you wish to seek the stream forward. Similarly, we can seek backward by "s b x".

## Understanding the code

We build a basic pipline using playbin. and after running it, we use various call back funtions to carryy out various tasks to ensure interactivity. We basically use 3 main functions for our process:

1. **Analyse stream**: this function is called once when the state of the pipeline changes from play for the first time. It will fetch all the information regarding the input streams and also, which stream is currently playing.

2. **Handle Keyboard**: This functions responds to any terminal input given to the application. We use g_io_signal to watch for input and call this function whenever required. This function then carries out the necessary actions depending on user input.

3. **handle message**: This function takes care of all the messages generated by the bus. It takes care of calling anaylse stream function and maintianing the buffer for smooth streaming.


   
