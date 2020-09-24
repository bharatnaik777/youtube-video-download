# YouTube video download script
Main features of this Script are:
* It is easy to use
* Shows video title,length,file,size and etc
* you can select by media type(audio/video)
* For user interaction, this script contains PrettyTable module (pip install PrettyTable)
* Shows downloading speed and ETA.

## Pafy
 
**pip install pafy**

Documentation:[Pafy 0.5.5](https://pypi.org/project/pafy/)

Install pafy
Main content of the script is Pafy
Pafy gives features of downloading YouTube videos


## Pretty Table
**pip install PrettyTable**

Documentation:[PrettyTable 0.7.2](https://pypi.org/project/PrettyTable/)

Install PrettyTable
Script for creaing tables 

## Steps to creating an user-friendly YouTube Video download script
* importing modules for youtube download
```
 import pafy 
 import math
 from prettytable import PrettyTable 
```

* taking input as url
```
 url =input("enter youtube url:") 
```

* line break
```
 print('\n') 
```

* assigning pafy.new()  to yt variable
```
 yt=pafy.new(url) 
```
* Creating variables for mediatypes
```
 audio=yt.audiostreams 
 video=yt.streams 
 all=yt.allstreams 
```

* printing video information
```
 print(yt) 
```

* line break
```
 print('\n') 
```

* Taking input for selecting media type
```
 type=input('audio/video:') 
```
* line break
```
 print('\n') 
```
* creating table for audio
```
 x = PrettyTable() 
 x.field_names = ["Index","bitrate","extension","file size"] 
 for i in audio: 
   p=str(math.ceil(i.get_filesize()/1024/1024))+' mb' 
   x.add_row([audio.index(i),i.bitrate,i.extension,p]) 
  ```
* creating table for video
```
 y = PrettyTable() 
 y.field_names=["Index","resolution","extension","file size"] 
 for j in video: 
    q=str(math.ceil(j.get_filesize()/1024/1024))+' mb' 
    y.add_row([video.index(j),j.resolution,j.extension,q]) 
   ```
* creating table for all
```
 z= PrettyTable() 
 z.field_names=["Index","media type","extension","quality"] 
 for k in all: 
	 r=str(math.ceil(k.get_filesize()/1024/1024))+" mb" 
	 z.add_row([all.index(k),k.mediatype,k.extension,r]) 


 print('select a file:') 
```
* conditions for media type
```
 if type=='audio': 
  	  print(x) 
  	  a=int(input("type index no. of your file:"))  
  	  l=audio[a].get_filesize() 
  	  print("your file size is" ,math.ceil(l/1024/1024),"mb") 
  	  d=input("Do you want to download the file?(y/n)") 
  	  if d=='y': 
  	 	 print(audio[a].download()) 
  	 	 print("your audio is downloaded") 
  	  else: 
  	   	  print("select again") 
  	   	 
  	   	 
 elif type=='video': 
	    print(y) 
	    b=int(input("type index no.of your file:")) 
	    m=video[b].get_filesize() 
	    print("your file size is" ,math.ceil(m/1024/1024),"mb") 
	    e=input("Do you want to download the file?(y/n)") 
	    if e=='y': 
	   	 print(video[b].download()) 
	   	 print("your video is downloaded") 
	    else: 
	   	 print("select again") 
	   
	   
 else: 
	    print(z) 
	    c=int(input("type index no. of your file:")) 
	    n=all[c].get_filesize() 
	    print("your file size is" ,math.ceil(n/1024/1024),"mb") 
	    f=input("Do you want to download the file?(y/n)") 
	    if f=='y': 
	        print(all[c].download()) 
	        print("your video is downloaded") 
	    else: 
	   	 print("select again") 
```


Created by Bharat Naik...

© Bharat Naik

If you have any questions or issues contact me.
