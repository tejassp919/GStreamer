# Gstreamer guide

To begin with understanding gstreamer, let's first understand the [hello world](https://gstreamer.freedesktop.org/documentation/tutorials/basic/hello-world.html?gi-language=c) code. This will show us how to use a inbuilt end-to-end pipeline - *playbin*. It will introduce the basic concept of [*bus*](https://gstreamer.freedesktop.org/documentation/application-development/basics/bus.html?gi-language=c) and [*message*](https://gstreamer.freedesktop.org/documentation/additional/design/messages.html?gi-language=c) in gstreamer. Messages are refcounted lightweight objects to signal the application of pipeline events (ex. state change message, end of stream reached message). A bus is a simple system that takes care of forwarding messages from the streaming threads to an application in its own thread context. Every pipeline contains a bus by default, so applications do not need to create a bus or anything. The only thing applications should do is set a message handler on a bus, which is similar to a signal handler to an object. When the mainloop is running, the bus will periodically be checked for new messages, and the callback will be called when any message is available.

   The [basic tutorial 2](https://gstreamer.freedesktop.org/documentation/tutorials/basic/concepts.html?gi-language=c) will help us understand how a custom pipleine is made and how error handling is done. Understand [different states in gstremer](https://gstreamer.freedesktop.org/documentation/plugin-development/basics/states.html?gi-language=c) and how they differ in terms of data flow.
   
   The [basic tutorial 3](https://gstreamer.freedesktop.org/documentation/tutorials/basic/dynamic-pipelines.html?gi-language=c) will have us to understand the concept of pads. Basically, all the elements have pads which facilitate the data flow from one element to another. There are 2 types of pads- source and sink. A pad can have 3 types of availibility- always, sometimes and on request.  In these tutorial we learn how to handle sometimes type of pad. We can learn about them in more detail over [here](https://gstreamer.freedesktop.org/documentation/application-development/basics/pads.html?gi-language=c). Major takeaway from this tutorial is to understand how various streams contained in same file can be handled using dynamic linking of pads.
   
   Now we can proceed to [basic tutorial 4](https://gstreamer.freedesktop.org/documentation/tutorials/basic/time-management.html?gi-language=c). Main takeaway of this code will be to understand how to perfrom seek to anytime using the function [gst_element_seek_simple](https://gstreamer.freedesktop.org/documentation/gstreamer/gstelement.html?gi-language=c#gst_element_seek_simple). It also introduces us to concept of [GstQuery](https://gstreamer.freedesktop.org/documentation/gstreamer/gstquery.html?gi-language=c), which has a more wider use to query different information about an element or a pad. 
   
   As of now the main thing to notice is that, any gstreamer application uses lots of callback functions for various puposes (bus watching, pad linking etc). These callback function are timely called using the concept of [signals](https://gstreamer.freedesktop.org/documentation/plugin-development/basics/signals.html?gi-language=c). Also we need to understand the purpose and use of [gmain loop](https://www.freedesktop.org/software/gstreamer-sdk/data/docs/latest/glib/glib-The-Main-Event-Loop.html).
   
   Then we can proceed to [basic tutorial 6](https://gstreamer.freedesktop.org/documentation/tutorials/basic/media-formats-and-pad-capabilities.html?gi-language=c) to understand the concept of pads in more detail.
   
   [Basic tutorial 7](https://gstreamer.freedesktop.org/documentation/tutorials/basic/multithreading-and-pad-availability.html?gi-language=c) introduces us to tee element. The purpose of this element is that it helps us to copy a stream in multiples. It help us to do multiple processess on same stream. It also explains us about *request pads*, which can create anytime as per our need.
  
   [Basic tutorial 8](https://gstreamer.freedesktop.org/documentation/tutorials/basic/short-cutting-the-pipeline.html?gi-language=c) will then explain us how we can import and eport data out of the gstreamer to any other file or application. It introuduces us with *appsrc* and *appsink* elements. *Appsrc* is usefull to inject data in middle of a gstreamer pipleine (say NLP program generated captions) which we probably didnt had in start of pipeline due to any reasons. *Appsink* will help us to export data (say audio to an NLP programme) out of the gstreamer to any other application of file.
   
   [Basic tutorial 9](https://gstreamer.freedesktop.org/documentation/tutorials/basic/media-information-gathering.html?gi-language=c) is optional. It teaches us how to fetch information regarding a given URI before hand for making certian appropriate decisions if we wish to.
    
   [Basic tutorial 10](https://gstreamer.freedesktop.org/documentation/tutorials/basic/gstreamer-tools.html?gi-language=c) teaches us how to make a very basic pipeline through command line itself. Though not usefull in actual developement, might be usefull for testing.
    
   [Basic tutorial 12](https://gstreamer.freedesktop.org/documentation/tutorials/basic/streaming.html?gi-language=c) help us to know how to we can manage buffering in gstreamer. Buffering expained in more detail over [here](https://gstreamer.freedesktop.org/documentation/application-development/advanced/buffering.html?gi-language=cgstreamer%20buufering)
   
