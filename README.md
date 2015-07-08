# MyDeepDream
Nicholas Alaniz 2015

#Sources

[tutorial](http://ryankennedy.io/running-the-deep-dream/)

[deepdream repo](https://github.com/ryankennedyio/deep-dream-generator)

[boot2docker](https://github.com/boot2docker/windows-installer/releases)
## How to
1. download and install boot2docker + virtualbox package  

2. run boot2docker.exe		

3. let it run until you see		
	`User@Computer ~`		
 	`$ _`

4. get the deepdream repo packaged by ryankennedyio		
  `docker pull ryankennedyio/deepdream`		

5. wait a while.		

6. while you wait, decide which folder to share with the virtual machine (defaults to //c/Users/)		
	use this format on windows		
	`//c/Replace/With/Path/To/Working/Directory`		

7. boot the image with this command		
	`docker run -d -p 443:8888 -e "PASSWORD=password" -v //c/Replace/With/Path/To/Working/Directory:/src/ ryankennedyio/deepdream`		

8. for me the output looked like		
  `Nick@PC ~`		
  `$ docker run -d -p 443:8888 -e "PASSWORD=password" -v //c/Users/Nick/DeepDreamImages:/src/ ryankennedyio/deepdream`		
  `985354e97173bdd7ca2753b8e40e0fe3372a21f1580a9a78fce5c2b24bc0098e`		

9. let the vm start and configure itself		

10. make sure the vm is running
	`boot2docker status`		

11. get the server ip		
  `boot2docker ip`

12. use your web browser to go to		
	`https://the.ser.ver.ip/`		

##extras		
1. boot2docker console		
	`resize the console by right clicking on its title`		
	`select properties`		
	`open the layout tab`		
	`change screen buffer size to 200 and 1000`		
2. browsing vm filesystem from boot2docker console		
	`docker ps`		
	look for NAMES, the value(s) below are names (will be something odd)		
	`docker exec -it odd_name bash`		
	you are now browsing the vm filesystem		
