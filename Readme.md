Hello,

Here are some download files for Whiteboard App (windows 10).
These are Appx/Appx Bundle files, not *.exe file.
I could not find download link for exe file.

To install Appx Bundle file properly,

1. Your windows 10 should be updated to the recent version.
2. Enable "SideLoading" feature in settings, if it's not turned on. It's enabled by default.
   Go to Settings > Updates & Security > For Developers. Enable *Sideload apps* there.
3. Just run *.appx file to see if it installs / launches.

=====

I tested x64 Appx file (54MB) and it worked okay.

For some useful links are here, in case it doesn't install properly.
https://www.howtogeek.com/285410/how-to-install-.appx-or-.appxbundle-software-on-windows-10/

Thank you,
Yurii.

========================================================

## 2020-12-07

### WebRTC Servers

=== 1. Janus WebRTC Server - C, C++, Javascript

 - [Github Link](https://github.com/meetecho/janus-gateway)
 - [Demo Link](https://janus.conf.meetecho.com/demos.html)
 - [Official Website & API Documentation](https://janus.conf.meetecho.com/index.html)


=== 2. MediaSoup - Node, C++, Typescript

 - [Github Link](https://github.com/versatica/mediasoup/)
 - [Demo Link](https://v3demo.mediasoup.org/?roomId=nypc9l8j)
 - [Official Website & API Documentation](https://mediasoup.org/)


=== 3. Jitsi - Java, Javascript

 - [Github Link](https://github.com/jitsi/jitsi)
 - [Demo Link](https://meet.jit.si/)
 - [Official Website & API Documentation](https://jitsi.org/)
 
 
=========================================================

## 2020-12-24

Link removed

## 2020-12-25

Same link, with updated contents.

=========================================================

## 2021-01-06

For RabbitMQ Offline Module, please check sub-folder named [2021-01-05](./2021-01-05)

=========================================================

## 2021-02-03

 - To merge the splitted files
 
 ```
 #cat facebook-split-?? > facebook.zip
 ```
 
  - To split again (if needed)
  
  ```
  #split -b 50M facebook.zip facebook-split-
  ```

=========================================================

## 2021-02-19

 - To merge the splitted files
 
 ```
 #cat RK3126-split-?? > RK3126.zip
 ```
