Open linux VM and open the terminal
----------------------------------
### ```sudo apt update```
----------------------------------
Should download a bunch of stuff
----------------------------------
### ```sudo apt upgrade ```
----------------------------------

Notice we are not listening on http ports
### ```ss -plunt ```
----------------------------------

Automatically starts hosting a webserver because of the version of linux we are using
          - Nginx is a server hoster just like apache.
 ----------------------------------         
### ```sudo apt install nginx```

 ---------------------------------- 
 Shows all ports that we are listening on
  ---------------------------------- 
### ```ss- plunt``` 
----------------------------------

go to localhost or 127.0.0.1 in your web browser

cd var/www/html
----------------------------------
List all items in current directory
----------------------------------
### ```ls``` 
----------------------------------
Remove the stock nginx webpage
----------------------------------
### ```sudo rm index.nginx-debian.html``` 
----------------------------------


### ```sudo nano index.html ```
(Creates a new index.html and allows you to edit it: here we will make a new start page)
      - make a small webpage 
      
  ![image](https://github.com/Oppslia/Commands-notes/assets/148699849/90ffc8f3-608d-404f-8046-7f2801c1510d)
  
### contol+o, then press enter to save

### control+x exit nano editor

### ```systemctl status nginx (should say active)```


### ```systemctl stop nginx ```

### ```systemctl status nginx ```(should say dead) you essentially killed the server.


### ```ss -plunt ``` (not listening  on 80 anymore)


### ```systemctl start nginx```

### ```ss -plunt ```

### ```systemctl status nginx (should say active)```


![image](https://github.com/Oppslia/Commands-notes/assets/148699849/60b10580-3f90-4547-be96-985f9000e8b9)

# Class period over:

# Next class period:

Open the index.html and create an image tag


```<img src="images/yourimagenme.fileextension" />``` this is a relative path to the image, so you need to make sure you have the image you download in this folder





![image](https://github.com/Oppslia/Commands-notes/assets/148699849/593a64c4-434a-45e9-a341-faced847f1e7)




refresh the page and there should be a broken image link

We dont have an image directory yet. So we will make one

### ```sudo mkdir images```

### ```ls ```(check if the directory is made)

image we used in class = https://www.southhills.edu/wp-content/uploads/AdobeStock_112962202.jpg

we saved as image.jpg into our downloads folder

Assuming you are still in var/www/html we copied from downloads to the images folder with:
----------------------------------
### ```sudo cp /home/mikko/Downloads/image.jpg images```

### source-------------------------------------------------destination
----------------------------------
Refresh your page and you should have the image on the website.


Changing gears. NTP means Network time protocol its port is 123

### in a linux terminal type ```date```
----------------------------------
We want to synchronize all servers time at once.
----------------------------------
### ```sudo apt install ntpdate```
----------------------------------
We go to our date and time settings and screw them up in the gui.
----------------------------------
### run ```date``` again 
----------------------------------
### ```sudo ntpdate time.windows.com ```  (windows time server)
----------------------------------
### ```date```
----------------------------------
check the gui date, it should also be fixed
----------------------------------

### sudo apt purge ntpdate to remove it from the machine but it doesnt apparently and guido is super confused LOL
