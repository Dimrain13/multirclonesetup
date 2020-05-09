# multirclonesetup
First and foremost this based mainly on animosity22's work linked below. Im not going to cover the initial setup as its well documented below. All you need to do is add each users gdrive to the rclone config via the same setup steps.
https://github.com/animosity22/homescripts

I wanted to move from a free account that I didnt have admin control over to the paid platform for Gdrive. The current minimum for users for
unlimited storage is 5 users. So I made 5 users and through some issues came up with the workflow shown in the code.

My setup is as follows

Main media server is local
Server that this is setup on is a VPS
The reason for this is to avoid bogging down local internet when items are uploading and downloading.
You can have your drives mounted in multiple locations as needed.


I have crontab check every 2 hours to see if there is more than 700GB of files. When it sees that there is it then calls the upcall script which is setup to call upload_script based on the number that is set in the upcount file. The file is changed at the end of each script which will cycle though all of the drives. 

This multiplies the daily upload limit by how many users you have. In this case that is 3.5TB.

I am still working on getting this to work with snapraid.
