# SSH into the RaspberryPi

SSHing into the RaspberryPi allows you to have access to the RaspberryPi terminal from a remote device.

SSH connection is disabled by default so here are the steps to to enable it:

* Go to the RaspPi preferences > configuration and click on enable.
* Reboot RaspPi.
* Get the IP address of the RaspPi by entering `hostname -I` in the terminal.
* On your laptop, open a terminal and run `ssh pi@<IP>`.

You should then be remotely connected to the RaspPi.

To stop the ssh connection, run `close 0`.
