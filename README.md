# PROXY_SET_UP_IN_LINUX_TERMINAL
How to set up proxy in linux terminal


Helllo guys.
We have often faced that problem in our linux terminal that TLS handshake failed or connection timeout and your proxy ip and all even after setting up the proxy in the system.
Ever wondered?? why this is happening??
Let's discuss about this.
Actually in terminal there are different tools through which we connect to the internet or do some stuffs using internet like installing, updating etc.
The terminal doesn't obey the system proxy setting as tools used in terminal has it's own configuration files.
For example: ~/.bashrc file for bash and for apt package manager, /etc/apt/apt.conf, /etc/apt/apt.conf.d.(We will set proxy for this)
The configuration file is responsible for the behaviour of the apt(advanced package tool).
So to set up the proxy follow these steps.

1. COPY THE FOLLOWINGS
    -Without username and password
            Acquire::http::Proxy "http://proxy.server:port";
            Acquire::https::Proxy "http://proxy.server:port";

            Eg:
            Acquire::http::Proxy "http://127.0.0.1:3128";
            Acquire::https::Proxy "http://127.0.0.1:3128";

    -With username and password
            Acquire::http::Proxy "http://username:username@proxy.server:port";
            Acquire::https::Proxy "http://username:username@proxy.server:port";

            Eg:
            Acquire::http::Proxy "http://abcd:1234@127.0.0.1:3128";
            Acquire::https::Proxy "http://abcd:1234@127.0.0.1:3128";

2. Type the following command
   
    -sudo touch /etc/apt/apt.conf.d/proxy.conf

    -sudo vi /etc/apt/apt.conf.d/proxy.conf

3. Add the following copied lines to the file

4. Then save it by pressing Esc and wq!
