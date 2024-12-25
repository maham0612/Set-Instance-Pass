# Set Instance (Ubuntu) Password

To set up a password for the `ubuntu` user on an instance and enable password authentication for SSH, follow these steps:

1. **Navigate to SSH Configuration Directory**  
   ```bash
   cd /etc/ssh/sshd_config.d
   ```

2. **Edit SSH Configuration**  
   Open the `60-cloudimg-settings.conf` file using `vim` or any text editor:  
   ```bash
   sudo vim 60-cloudimg-settings.conf
   ```  

3. **Enable Password Authentication**  
   Inside the file, ensure the following line is present or update it if needed:  
   ```plaintext
   PasswordAuthentication yes
   ```

4. **Set a Password for the `ubuntu` User**  
   Use the following command to set or update the password:  
   ```bash
   sudo passwd ubuntu
   ```

5. **Restart SSH Service**  
   Apply the changes by restarting the SSH service:  
   ```bash
   sudo systemctl restart ssh
   ```
   
6. **Test the Password Login**  
   Log out of the instance and try logging back in with the username and password:
   
   ```bash
   ssh ubuntu@your_instance_ip
   ```

   OR you can log in to the instance using the `ubuntu` user and the newly set password.


---

**Note:** Enabling password authentication can pose a security risk. It is recommended to disable password authentication and use SSH keys in production environments.
