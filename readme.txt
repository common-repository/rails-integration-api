=== Rails Integration API ===
Contributors: robbpdx
Donate link: http://greenfabric.com/page/integration_api_home_page
Tags: authentication, login, rails, single sign-on, integration
Requires at least: 2.6.3
Tested up to: 2.6.3
Stable tag: 1.0.3

The Rails Integration_API plugin enables single sign-on between a
Rails application and any number of Wordpress installations.

== Description ==

This plugin enables single sign-on between a Rails application and any
number of Wordpress installations.  You can view an 
[online demo](http://greenfabric.com:3000/) showing a Rails app integrated
with a Wordpress app.

The key idea of the Integration API is to add a web services API into
the existing Rails application, which allows one or more 3rd party
apps to get the information they need, when they need it.

The API code can be added to any Rails app without modification. The
Rails app stays in control of all sign-in and sign-out functions.

The 3rd party app, such as Wordpress, is installed in a subdirectory
of the Rails app on the same host.  Alternatively, it can be installed
running on a different port.  These configurations will allow it to
access the Rails cookie, which it needs to do to verify that the
current user is logged in.

This plugin gives the administrator a couple of options about how the
tight the integration should be (see the screenshots):

1. *Single sign-on* This can be switched on or off.  When on,
Wordpress will check the user's Rails login state on every page view,
and update the Wordpress cookie and login state automatically.  When
off, the user will need to explicitly click the Wordpress login and
logout links.
2. *Automatically create new users* This can also be switched on and
off.  It determines what happens when a user, logged in to Rails,
first accesses Wordpress.  It allows the administrator to maintain
manual control of who has login access, vs. allowing all Rails users
to have login access to Wordpress.


== Installation ==

1. Be sure that the Rails side is set up and working.  Instructions for this are in the readme file for it.  Download links are at the [Integration API home page](http://greenfabric.com/page/integration_api_home_page).
1. Unzip this plugin folder and copy the *integration-api* subfolder to your Wordpress's plugin directory.
1. Activate the plugin through the 'Plugins' menu in Wordpress.
1. Configure the settings according to the prompts in the 'Integration API' settings tab.


== Frequently Asked Questions ==

= What about CAS? =

CAS is definitely another option.  The best choice for you will depend
on your development needs.  CAS was designed to enable single sign-on
(SSO) across an enterprise.  On the other hand, this plugin was
designed to allow a Wordpress blog to transparently appear to be part
of a Rails app.  So there's a lot of overlap, and a few differences.
CAS has a couple of benefits over the plugin:

1. It enables single sign-on between web apps running on different
machines, whereas this plugin requires Wordpress to be on the same
webserver and have read access to Rails' session cookie.
1. CAS is a standardized protocol, and is probably implemented by a wide
variety of enterprise software.

And this plugin has a couple of advantages over CAS:

1. It supports OpenID as the back-end authorization --- that's how I
use it, and you can see this in the screenshots.  This plugin is
completely 'agnostic' as to how the real authentication is performed
by the Rails app, whereas CAS is generally tied to the
'username/password' concept.  CAS can theoretically be used with OpenID
as the back end, but this is either 'on hold' (Ruby CAS server), or
appears fairly complex to configure (ja-sig CAS server).
1. This plugin plus its corresponding Rails app seems to be easier to
configure than a CAS client/server pair: On the Rails side, one
controller needs to be dropped into the app, and a few constants set.
CAS requires more configuration, plus another server to be running.


== Screenshots ==

1. Top of the settings page for administrators.
1. The rest of the page.
