##Project Intro
==================================

SocksWebProxy is a C# project build to make http communication over the Tor network simple and easy for C# projects.


##Project Features
==================================

* C#
* Simple Interface for WebClient & WebRequest (Just assign a new SocksWebProxy to the *.Proxy attribute)
* No Need for Privoxy or similar service to translate http traffic to tor
* Easily Communicate over Tor with C#

##Extensions by Ogglas
==================================
Start Tor automatically and renew Ip-after every request. Follow the steps below to get everything to work and also being able to control Tor via Telnet.

1. Copy torrc-defaults into the directory in which tor.exe is. Default directory if you are using Tor browser is: "~\Tor Browser\Browser\TorBrowser\Data\Tor"
2. Open a cmd prompt window
3. chdir to the directory where tor.exe is. Default directory if you are using Tor browser is: "~\Tor Browser\Browser\TorBrowser\Tor\"
4. Generate a password for Tor control port access. tor.exe -–hash-password “your_password_without_hyphens” | more
5. Add your password password hash to torrc-defaults under ControlPort 9151. It should look something like this: hashedControlPassword 16:3B7DA467B1C0D550602211995AE8D9352BF942AB04110B2552324B2507. If you accept your password to be "password" you can copy the string above.
6. You can now access Tor control via Telnet once it is started. Now the code can run, just edit the path to where your Tor files are located in the program.
Test modifying Tor via Telnet:
7. Start tor with the following command: tor.exe -f .\torrc-defaults
8. Open up another cmd prompt and type: telnet localhost 9151
9. If all goes well you should see a completely black screen. Type "autenticate “your_password_with_hyphens”" If  all goes well you should see "250 OK".
10. Type "SIGNAL NEWNYM" and you will get a new route, ergo new IP. If  all goes well you should see "250 OK".
11. Type "setevents circ" (circuit events) to enable console output
12. Type "getinfo circuit-status" to see current circuits

##Tools
==================================

If you are not familiar with C# then you will want to have a look at these free development tools

#####Windows

<a href="http://www.microsoft.com/en-us/download/details.aspx?id=34673">Visual Studio 2012 Express</a>

#####Mac & Linux

<a href="http://monodevelop.com/">MonoDevelop</a>

##Before You Build
==================================

You will probably want to setup Tor on your development machine.

#####Tor

<a href="https://www.torproject.org/download/download.html.en">Download Tor</a>

##Software Licensing Policy
==================================

#####For Open Source Projects

If you are developing and distributing open source applications under the GPL License, then you are free to use this project under the GPL License.
<a href="http://www.gnu.org/licenses/gpl-faq.html">GPL FAQ</a>

#####Commercial, Enterprise and Government Projects

Contact me at Landon.Key@gmail.com for more information on Commercial, Enterprise, and Government use of the this project.
