# Gstreamer guide

To begin with understanding gstreamer, let's first understand the [hello world](https://gstreamer.freedesktop.org/documentation/tutorials/basic/hello-world.html?gi-language=c) code. This will show us how to use a inbuilt end-to-end pipeline - *playbin*. It will introduce the basic concept of [*bus*](https://gstreamer.freedesktop.org/documentation/application-development/basics/bus.html?gi-language=c) and [*message*](https://gstreamer.freedesktop.org/documentation/additional/design/messages.html?gi-language=c) in gstreamer. One main thing to note is that all the functions in gstreamer have different pointers as parameters, and they also return pointers on execution. So make sure to *unref* them after use.
   
