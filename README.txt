================
Mobility Helpers
================

Version : 0.2
Author : Thomas Weholt <thomas@weholt.org>
License : Modified BSD
WWW : https://bitbucket.org/weholt/django-mobilityhelpers
Status : Beta - Experimental.


About
-----
Mobility Helpers are a small reusable django app making it easier to target mobile platforms/devices. It comes as a piece of middleware
and a helper function to render a view.

In short using a special function to render your views will detect requests from mobile devices and look for a special template for that devices. Normal clients
will get a normal template. So if you access a page with your tablet the app will use templatename.mobile.html to render the view instead of templatename.html.


Installtion
-----------
* pip install django-mobilityhelpers
* add 'mobilityhelpers.middleware.MobileDetectionMiddleware' to your middleware section in settings.py
* in your views do a 'from mobilityhelpers import smart_response'

Usage
-----

* After installation your should have a 'is_mobile' property on your request instances. You can use this to tune your queryset etc. for mobile devices.
* Instead of using render_to_response use smart_response(request, template_name, context_data).


Configuration options
---------------------
* You can settings.DISABLE_MOBILITY_HELPERS = False to disable rendering of templates aimed at mobile devices.
* settings.DETECT_MOBILE_FLAVOUR = True will add a specific tag to the template being rendered, ie. for ipad ( the only supported device so far ) will
 render index.ipad.html instead of index.mobile.html when accessed with an iPad. All other supported mobile devices will use index.mobile.html.


Changelog
---------

0.2.0 - Python 3.x support.

0.1.0 - Initial release.


Requirements
------------
* django


Credits
-------
* http://djangosnippets.org/snippets/2001/