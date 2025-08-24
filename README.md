# PeachPortal
A JavaScript-based HTML page for easily accessing LLM being hosted on a local network HTML server.
Cowritten by me (20%) and a large cloud-based LLM (80%,) this file allows you to serve an LLM with LM Studio on a local machine and access the LLM via a web browser on a different machine. No OpenWebUI or other installs are necessary on either machine. You can even have a third machine like a file server or local web server host the file instead of the machine running LLM.

Install notes:

    Load LM Studio on the host machine, download desired models, et cetera. Note that all work is done by the host machine so load models optimized (CUDA, MLX) for that machine not the user or filehost machines.

    In the Developer tab on LM Studio, turn on the server and note the IP address and port number. If the machine has more than one TCP/IP interface, this may be misleading. Use the IP address that corresponds to your usual numbering scheme. The default port really is 1234 but you can change it if you want.

    Download and edit the HTML file appropriately. It's much less hassle for users to change the placeholder and the default address to the default on your network, but it will work even if you don't - the user will just have to set it in the URL box every time they load the page.

    Put the edited HTML file in the directory your server serves web pages from. On most *nix boxes this is going to be something like /var/www/html but it varies tremendously.

    On a JavaScript capable browser on the user machine go to http://<IP_OF_LM_STUDIO_MACHINE><PORT_#>. If you want to see the address look on the Developer tab in LM Studio but beware as in Step 2 above.

    You can now use the Peach Portal to access your LM Studio install from any machine that can access your LM Studio host on your local network. Be sure the firewalls on both the HTML host machine (if different) allow connections on port 1234 or whatever you picked. No firewall adjustments are neessary on the user machine as the Peach Portal is just another web page to it.
