#nddconfig#

A Solaris network device configuration script.

##Some history##

The original nddconfig script was written as an implementation of the recommendations found in the Sun Blueprints article "[Solaris Operating Environment Network Settings for Security](http://www.filibeto.org/sun/lib/blueprints/2002-vol4-cd/1299/network.pdf)" written by [myself](http://ikawnoclast.com/) and Alex Noordergraaf in December 1999. I wrote it to implement all of our recommendations in the article.

In 2000, we updated the article and nddconfig for Solaris 8. That [article](http://www.filibeto.org/sun/lib/blueprints/2002-vol4-cd/1200/network-updt1.pdf) had some additional information about new settings in Solaris 8. The nddconfig script also added a comparison and status mode. The status mode prints your current settings for various ndd modes. That comparison mode displayed the current settings and compares it to our recommended settings.

nddconfig was rolled into the Titan security tool as well as Sun's Jumpstart Architecture and Security Scripts (JASS), a tool from my co-author Alex Noordergraaf.

After I left Sun in 2002, the Blueprints program continued but eventually ended with the various problems that Sun endured. Oracle bought Sun and the Blueprints articles and tools seemed to have displayed as well. 

I wanted to preserve the code here so that others can still find it and use it.

##Installation##

As root (or with sudo), execute the following commands:

    # cp <script> /etc/init.d/nddconfig
    # chmod 744 /etc/init.d/nddconfig
    # chown root:sys /etc/init.d/nddconfig
    # ln /etc/init.d/nddconfig /etc/rc2.d/S70nddconfig

##Command line use##

When installed using the commands above, nddconfig will make changes when the system boots into run-level 2. You can also use the following commands from the command line:

###Enable the changes###

    # /etc/init.d/nddconfig start

###Display the current settings###

    # /etc/init.d/nddconfig show

###Compare the current settings to recommended settings###

    # /etc/init.d/nddconfig compare