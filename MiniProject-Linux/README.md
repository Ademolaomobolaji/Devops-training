# Creating of EC2 Instance and connecting with ssh client.

- Sign in to AWS account and search for Instance or Create a new Instance.

- Connect to Ubunter Server with MobaXterm

### Steps to Connect EC2 with MobaXterm
- Step 1: Launch MobaXterm

Open the MobaXterm application on your computer.

- Step 2: Start a New SSH Session

Click on the "Session" icon (top left corner).

Select "SSH" from the session types.

- Step 3: Enter EC2 Instance Details

In the "Remote host" field, enter your EC2 instance’s Public IPv4 address or Public DNS (found in your AWS Console).

Keep the default SSH port as 22.

- Step 4: Specify the Username

Under "Basic SSH settings", check the box labeled “Specify username”.

Enter your instance’s username, for example:

ec2-user (for Amazon Linux)

ubuntu (for Ubuntu)

admin (for Debian)

centos (for CentOS)

- Step 5: Load the Private Key (.pem file)

Click on the "Advanced SSH settings" tab.

Check “Use private key”.

Click the browse icon (...) and select your .pem key file.

💡 Note: Ensure the .pem file has correct permissions (readable by you only).
If you get a permission error, you may need to convert .pem to .ppk format using PuTTYgen — though MobaXterm usually supports .pem directly.

- Step 6: Save the Session (Optional)

You can click "Save session" and give it a name if you want to reconnect easily later.

- Step 7: Connect

Click “OK” to start the session.

A terminal window will open, and MobaXterm will initiate the SSH connection.

- Step 8: Accept the Key Fingerprint

The first time you connect, you’ll be asked to accept the server’s SSH key fingerprint.

Click “Yes” to continue.

- Step 9: You’re Connected! 🎉

