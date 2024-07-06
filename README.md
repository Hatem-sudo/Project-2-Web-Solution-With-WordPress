# Project-2-Web-Solution-With-WordPress

![Capture3](https://user-images.githubusercontent.com/74002629/226575833-7d752dee-235f-45c9-a19d-57fcdf71df2a.PNG)

### Part 1: Configure storage subsystem for Web and Database servers based on Linux OS.

#### Steps

1. Launch an EC2 instance that will serve as "Web Server".
2. Attach all three volumes one by one to Web Server instance
3. Open up the Linux terminal to begin configuration of the instance

![1](https://github.com/Hatem-sudo/Project-2-Web-Solution-With-WordPress/assets/113099054/6d6510f0-dcc7-45b3-b979-27420610cc4c)

4. create a single partition on each of the 3 disks
5. Install **lvm2** package.
6. Create physical volume to be used by lvm. 
7. Create the volume group .
8. View newly created volume group.
![2](https://github.com/Hatem-sudo/Project-2-Web-Solution-With-WordPress/assets/113099054/4536855b-1dd7-4abb-bb03-30b1bc659d53)

9. Create 2 logical volumes using lvcreate utility
10. format the logical volumes with ext4 filesystem.

![100](https://github.com/Hatem-sudo/Project-2-Web-Solution-With-WordPress/assets/113099054/a766a1d8-18d7-432f-aae7-438b7dda2b8a)

11. Create mount points for logical volumes
    
![97](https://github.com/Hatem-sudo/Project-2-Web-Solution-With-WordPress/assets/113099054/0f9c8851-357f-4fab-89e1-1abedbdea4c6)

12. Create **/home/recovery/logs** to store backup of log data.
13. backup all the files in the log directory **/var/log** into **/home/recovery/logs** (It is important to backup all data on the /var/log directory because all the data will be deleted during the mount process).
14. Mount /var/log on logs-lv logical volume.
15. Finally, restore deleted log files back into /var/log directory.
16. ‘pdate **/etc/fstab** file so that the mount configuration will persist after restart of the server.
    
![98](https://github.com/Hatem-sudo/Project-2-Web-Solution-With-WordPress/assets/113099054/98a810ec-abca-4142-b31a-8152fb435ea9)

17. Test the configuration and reload.
18. Verify your setup by running.
![98](https://github.com/Hatem-sudo/Project-2-Web-Solution-With-WordPress/assets/113099054/98a810ec-abca-4142-b31a-8152fb435ea9)

### Part 2 - Prepare the Database Server
19. Launch a second RedHat EC2 instance.
20. Repeat the same steps as for the Web Server.

### Part 3 -Install WordPress and connect it to a remote MySQL database server.
21. Update the repository.
22. Install wget, Apache and it’s dependencies.
23. Start Apache

![MYSQL](https://github.com/Hatem-sudo/Project-2-Web-Solution-With-WordPress/assets/113099054/3446639e-57a8-4fa2-ad77-902acffe7288)

24. install PHP and it’s depemdencies:
25. Restart Apache.
26. Download wordpress and copy wordpress to var/www/html.

![php](https://github.com/Hatem-sudo/Project-2-Web-Solution-With-WordPress/assets/113099054/0920e118-5bec-43eb-8445-f79e5321f3b4)

### Step 4 — Install MySQL on your DB Server instance
27. Install MySQL 
28. Verify that the service is up and running.

![000](https://github.com/Hatem-sudo/Project-2-Web-Solution-With-WordPress/assets/113099054/029864e5-562c-408f-9044-e576e0555e85)

### Step 5 — Configure DB to work with WordPress
30. Configure DB to work with Wordpress.
31. Make sure to open MySQL port 3306 on DB Server EC2.
32. Install MySQL client and test that you can connect from your Web Server to your DB server.
33. Verify if you can successfully execute SHOW DATABASES.
![0000](https://github.com/Hatem-sudo/Project-2-Web-Solution-With-WordPress/assets/113099054/90660af3-51d1-440f-8eaa-ab0b76952ff6)

29. Change permissions and configuration so Apache could use WordPress.
30. Enable TCP port 80 in Inbound Rules configuration for your Web Server EC2 .
31. Access to WordPress http://<Web-Server-Public-IP-Address>/wordpress/
![end](https://github.com/Hatem-sudo/Project-2-Web-Solution-With-WordPress/assets/113099054/aba2a462-fb46-49dd-9fb7-46a16671e8d6)
  
