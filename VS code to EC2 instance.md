# VS Code to EC2 instance setup

[Reference Link](https://dev.to/cindyledev/remote-development-with-visual-studio-code-on-aws-ec2-4cla)

## Prerequisite
1. Download and install Visual Studio Code
2. Install the Remote - SSH extension
3. AWS  Account. You will need your AWS_ACCESS_KEY_ID and  AWS_SECRET_ACCESS_KEY and your SSH key (.pem file)

Note: Please refer reference link for AWS SEtup part

## VS Code to remote EC2
1. Open up Visual Studio Code
2. Click on the Open a Remote Window icon at the bottom left-hand corner of the window
3. Select Connect to Host
4. Select Configure SSH Hosts...
 This will open up a config file in Visual Studio Code. If you're using Windows, it'll be something like C:/Users/cindy/.ssh/config
5. Edit the config file with the following:
"""
Host aws-e2
    HostName <your-ec2-ip-address>
    User ec2-user
    IdentityFile ~/.ssh/labsuser.pem

"""
6.Save the file
7.When you click on the Open a Remote Window icon at the bottom left-hand corner again and choose Connect to Host, you will see aws-ec2 listed.
8.Select aws-ec2 and a new Visual Studio Code window will open
9.You will see "aws-ec2" has fingerprint "SHA256:xxx" and Are you sure you want to continue?. Click on Continue. Then You should see that you're connected!
