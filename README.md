# Development Environment Lab

### This is a brief step-by-step guide to using Vagrant and editing the Vagrantfile to allow for the creation and usage of a virtual machine

1. Ensure you have Oracle VirtualBox and Vagrant installed on your machine.

2. Run the command ```vagrant init ubuntu/xenial164``` in your terminal and enter it using the 'cd' command.

3. Run the command ```vagrant up``` then ```vagrant ssh``` to go into the console of ubuntu.

4. Run ```sudo apt-get update && sudo apt-get upgrade -y``` to update and use the most up-to-date files available.

5. Run ```sudo apt-get install nginx -y``` to install nginx which will allow you to run it in a browser.

6. You can see if this is working by running the command ```curl http://localhost``` which will display the nginx page as code in your terminal. Additionally, you can view it in your browser by typing 'http://localhost' in your browser url.

7. You can get further information, including the ip address, by running ```ifconfig```.

8. Exit the ubuntu console with ```exit``` and open up the folder in a text editor and in the Vagrantfile, add the line ```config.vm.network "private network", ip: "192.168.10.100"``` (the ip can be any ip you choose, it does not have to be this specific example).

9. Save this and, back in your terminal, run ```vagrant reload``` followed by ```vagrant ssh``` to go back into ubuntu. Thereafter, if you run ```ifconfig``` you can see the ip address you added to the Vagrantfile. You can now search this ip address in your browser.

10. Additionally, outside of vagrant, you can also run ```vagrant plugin install vagrant-hostsupdater``` and add to the Vagrantfile the line ```config.hostsupdater.aliases = ["development.local"]``` (development.local can be anything depending on the work being carried out). Now, having gone back into ubuntu, you can search in your browser 'http://development.local' and you should see the nginx page appear as before.