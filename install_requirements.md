﻿# Install requirements and visual studio project configuration.

## Install openFrameworks, Visual Studio Community 2015 and openFrameworks plugin for Visual Studio

* Download and unzip openFrameworks release, we used the [v0.9.8](http://www.openframeworks.cc/versions/v0.9.8/of_v0.9.8_vs_release.zip)
our path is C:\of_v0.9.8_vs_release and all projects need to be put at C:\of_v0.9.8_vs_release\apps\myApps to work.
More details in [of install.md](of_INSTALL.md)

* Go to [visual studio setup guide](http://openframeworks.cc/setup/vs/) and follow the instructions.
This project uses two OF addons,ofxGUI and ofxmlSettings they come with the release in the addons folder and should be enabled.

## Install FFmpeg

FFmpeg is optional, its only used for audio extraction or for the stripRotate utility.

* Follow [Install-FFmpeg-on-Windows](https://www.wikihow.com/Install-FFmpeg-on-Windows)

## Install OpenCV 3.2 and contrib modules

* Follow [this instructions](https://www.learnopencv.com/install-opencv3-on-windows/)

Will end up with this structure:

C:\opencv-3.2.0\source\opencv
C:\opencv-3.2.0\source\opencv_contrib

this ones are not important anymore can be deleted.

C:\opencv-3.2.0\build

The build folder.

C:\opencv-3.2.0\build\install\x64\vc14\lib

The compiled libraries for visual studio 2015.

Download the OF solution from github and put it in:

C:\of_v0.9.8_vs_release\apps\myApps

## Configuring video-assessment project

On the solution explorer right click on the video-assessment project and select openFrameworks addons. Check ofxGui and ofxXmlSettings and click ok.

* Project>Properties>C/C++>Additional Include Directories.
![figure 1](/images/vs1.jpg)

* Project>Properties>Linker>General>Additional Library Directories
![figure 2](/images/vs2.jpg)

* Project>Properties>Linker>Input>Additional Dependencies
![figure 3](/images/vs3.jpg)

** Release:

opencv_core320.lib
opencv_bgsegm320.lib
opencv_highgui320.lib
opencv_imgcodecs320.lib
opencv_imgproc320.lib
opencv_ml320.lib
opencv_objdetect320.lib
opencv_optflow320.lib
opencv_saliency320.lib
opencv_tracking320.lib
opencv_video320.lib
opencv_videoio320.lib
opencv_dnn320.lib
opencv_photo320.lib

** Debug:

opencv_core320d.lib
opencv_bgsegm320d.lib
opencv_highgui320d.lib
opencv_imgcodecs320d.lib
opencv_imgproc320d.lib
opencv_ml320d.lib
opencv_objdetect320d.lib
opencv_optflow320d.lib
opencv_saliency320d.lib
opencv_tracking320d.lib
opencv_video320d.lib
opencv_videoio320d.lib
opencv_dnn320d.lib
opencv_photo320d.lib

## vlc for windows

To be able to preview with an external aplication the currently selected video when cliking on the preview, both instaling vlc and setting the PATH environment variable to the location of vlc.exe(e.g:C:\Program Files (x86)\VideoLAN\VLC) are required.

https://get.videolan.org/vlc/3.0.1/win32/vlc-3.0.1-win32.exe

There is a batch file in the /bin folder: va.bat
this batch file sets up a session PATH environment variable that includes the default path to vlc.exe (e.g:C:\Program Files (x86)\VideoLAN\VLC)