
### update the package: 

```
echo updating
sudo apt update -y
echo done!

```

###  upgrade the list of packages 

```
echo upgrade packages
sudo DEBIAN_FRONTEND=noninteractive apt upgrade -y
echo done!

```
### install nginx

``` 
echo installing nginx
sudo DEBIAN_FRONTEND=noninteractive apt install nginx -y
echo finished installing nginx
```

### restart nginx 

``` 
echo restarting nginx
sudo systemctl restart nginx
echo finished restarting nginx

```
### enabling nginx 

``` 
echo enabling nginx
sudo systemctl enable nginx
echo finished enabling nginx

```


### Installing nodejs v20

``` 
echo installing nodejs v20
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo DEBIAN_FRONTEND=noninteractive -E bash - &&\
sudo DEBIAN_FRONTEND=noninteractive apt-get install -y nodejs
echo finished installing nodejs v20

```
### Check correct node version and it has installed

``` 
echo checking node version
node -v
echo finished checking node version

```

### scp into  your EC2 instance 

copy in your local machine the correct path to the app using the format below:

`scp -i ~/.ssh/tech258.pem -r ~ app-code\tech258-sparta-test-app\app ubuntu@ec2-3-248-200-53.eu-west-1.compute.amazonaws.com:~`
<br>
Break down of the above :
- `scp` stands for "secure copy". 
- `i ~/.ssh/tech258.pem:`- `i` flag is used to specify the file for public key authentication.
`~/.ssh/tech258.pem` -  specifies the path to the private key  

`r`-  flag is used to copying entire directories and their contents recursively.

`app-code/tech258-sparta-test-app/app` - refers to the user's home directory on the local machine.

`app-code/tech258-sparta-test-app/app`  specifies the path to the source directory or file on the local machine.

`ubuntu@ec2-3-250-58-242.eu-west-1.compute.amazonaws.com:~:`  ubuntu is the username used to connect to the remote host

`:` separates the source and destination in the scp command.

`~` it refers to the user's home directory (ubuntu user's home directory).

### clone your repository 
`git clone <repository-url>`

### install npm 
 `npm install` in your home directory
   
   
### start your node.js application:
 `npm start`


### Run node app in background
Running a script in the background in linux can be done using nohup.

`$ nohup node /nodeapp/index.js &`

OR

`$ npm install forever -g`  *

OR 

`$ npm install pm2 -g`


Congratulations! now you can copy the ip address and add :3000 to access the TCP port

