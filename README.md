# PeachPortal
A JavaScript-based HTML page file for easily accessing LLM being hosted on a local network HTML server with LM Studio.

Cowritten by me (20%) and a large cloud-based LLM (80%,) this file allows you to serve an LLM with LM Studio on a local machine and access the LLM via a web browser on a different machine. No OpenWebUI or other installs are necessary on either machine. You can even have a third machine like a file server or local web server host the file instead of the machine running LM Studio.

Install Steps:

1) Load LM Studio on the host machine, download desired models, et cetera. Note that all work is done by the host machine so load models optimized (CUDA, MLX) for that machine not the user or filehost machines.

2) In the Developer tab on LM Studio, turn on the server and note the IP address and port number. If the machine has more than one TCP/IP interface, this may be misleading. Use the IP address that corresponds to your usual numbering scheme. The default port really is 1234 but you can change it if you want.

3) Download and edit the HTML file appropriately. It's much less hassle for users to change the placeholder and the default address to the default on your network, but it will work even if you don't - the user will just have to set it in the URL box every time they load the page.

4) Put the edited HTML file in the directory your server serves web pages from. On most *nix boxes this is going to be something like /var/www/html but it varies tremendously.

5) On a JavaScript capable browser on the user machine go to http://<IP_OF_LM_STUDIO_MACHINE><PORT_#>. If you want to see the address look on the Developer tab in LM Studio but beware as in Step 2 above.

You can now use the Peach Portal to access your LM Studio install from any machine that can access your LM Studio host on your local network. Be sure the firewalls on both the HTML host machine (if different) allow connections on port 1234 or whatever you picked. No firewall adjustments are neessary on the user machine as the Peach Portal is just another web page to it.

Breakdown of parameter settings:

A) Server URL: Should default, if you edited it in, to the proper URL:Port. If so, it is not necessary to reenter it or hit Save. If not, or if the user has access to more than one, can change at will.

B) Select Chat History: Chats are stored locally so you cannot access a chat on User Machine A from User Machine B et cetera. You must either select an existing history or hit New Chat to begin a chat. Note that selecting a chat history does NOT activate the LLM used to generate the chat in that history. See Step C. Chats can be named when started and renamed at will with the Rename Chat button. "Fork Chat" creates an identical copy of the current chat to date so the user can try different inputs but always return to the forking point. You can fork forked chats. Chats are text-only and don't use much space but you can delete the current chat with the Delete Chat button.

C) Select Model: Just what it sounds like. Shows all models available to the host's LM Studio installation. The default system prompt is whatever is loaded on the LM Studio host, but it can  be rewviewed and edited with the "See System Prompt" and "Show System Prompt" buttons. If selecting an existing chat history, every message from the LLM is labeled with its name: just select that name from the dropdown to use the same model to continue the chat. Selecting a model ejects (stops) the running model and initializes the selected model, which can take a little bit.

D) Set System Prompt and See System Prompt are just what they sound like.

E) Max Tokens is just what it sounds like, as are Temperature and Top P.

E) The Regenerate Response button deletes the LLM's last response and resends the last user prompt. Note that this button is only avaiable when the last message in the main chat box is from the LLM.
