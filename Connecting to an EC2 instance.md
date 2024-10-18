# Bash commands to connect to an EC2 instance 
### To connect to an EC2 instance from your local machine your commands should be the belows

## 1st check that the .pem file exist or not
```
ls -l ~/Downloads/<fileName>.pem
```

## Give the permissions to access the file with the file location
```
chmod 777 /c/Users/shrey/Downloads/<fileName>.pem
```

## Then to connect to the EC2 instance reun the below
```
ssh -i ~/Downloads/<fileName>.pem <ec2-user>@<public ip>
```



