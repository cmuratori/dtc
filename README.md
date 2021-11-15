# Dangerous Threads Crew

This is a very simple example program to illustrate how you move CreateWindow/DestroyWindow onto a separate thread if you need your API architecture to allow the main thread to create and destroy windows in an arbitrary way.

It may seem like a strange thing to do, but unfortunately Win32 internals have some really bad behavior during sizing and dragging windows that make it difficult for real-time rendering applications to properly continue what they're doing during those events without interruption.  Moving CreteWindow/DestroyWindow onto a separate thread moves the message processing for all windows onto that separate thread, thereby preventing Windows' message processing from interrupting your main threads.

\- Casey
