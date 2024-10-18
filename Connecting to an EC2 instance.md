# Bash commands to connect to an EC2 instance 
### To connect to an EC2 instance from your local machine your commands should be the belows

## 1st check that the .pem file exist or not
```
ls -l ~/Downloads/<fileName>.pem
```
```
ls -l ~/Downloads/test_laptop.pem
```

## Give the permissions to access the file with the file location
```
chmod 777 /c/Users/shrey/Downloads/<fileName>.pem
```
```
chmod 777 /c/Users/shrey/Downloads/test_laptop.pem
```

## Then to connect to the EC2 instance reun the below
```
ssh -i ~/Downloads/<fileName>.pem <ec2-user>@<public ip>
```
```
ssh -i /c/Users/shrey/Downloads/test_laptop.pem ubuntu@51.20.18.229
```



