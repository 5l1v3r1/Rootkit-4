<h1> RangerDanger rootkit </h1>

<h2>Installation</h2>

<p1>
  To install the rootkit first clone into the repo and run the 'make' command to produce the RangerDanger.ko file<br />
  once you have created the kernel module file all you have to do is install it with the command: 'insmod RangerDanger.ko'<br />
  Note: this has to be done as root. LKM Rootkits expect that you already have root privileges.<br />
  we will be sending commands to the device driver so for now you need to modify the permissions for the device<br />
  This is done with a simple command: 'chmod 777 /dev/ttyCWO' after that you are good to go!<br />
</p1>

<h2>Interacting with the rootkit</h2>

<p1>
  Once installed, the LKM creates a device called /dev/ttyCWO (this can be changed to whatever you want)<br />
  to send commands to the rootkit all you have to do is echo commands to the device driver<br />
  example: 'echo "whatever command" > /dev/ttyCWO' this command will be ran by the rootkit<br />
  **** I fully intend to make the process of interacting with the rootkit smoother ***
</p1>

<h2>Features</h2>

<h4>Self Hiding Module</h4>
  <p1>
    Currently the LKM hides itself on install, to toggle if the module is visable via the 'lsmod' command<br />
    just send the rootkit the command 'hide' this will toggle it on and off
  </p1>
<h4>Privilege Escalation</h4>
  <p1>
    The only other feature as of right now is to give your current shell root privileges.<br />
    this is easily done by send the rootkit the command 'cwo' this will instantly give you root!
  </p1>
  
<h2>Uninstallation</h2>
<p1>
  Since the rootkit hides itself by default you will need to send it the commmand 'hide' to make it visible.<br />
  after the LKM is visible you can easly remove it with the command: 'rmmod RangerDanger'
</p1>
