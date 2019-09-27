---
layout: post
title: Register Jabber User's from Rails...
---

On a recent project I needed the ability to register and unregister
users from a Rails app, specifically a simple User model. At first I
just added the necessary capabilities to the model itself…then realized
the functionality really should exist as a library/helper. Well, if I’m
going that far - might as well just drop it into a “plugin”.

You can find the plugin here:
[xmmp4rails](http://github.com/kitplummer/xmpp4rails/wikis/home).

xmmp4rails is a simple method-level layer around a “few” of the
capabilities provided by the awesome
[xmpp4r](http://home.gna.org/xmpp4r/) library.

To get the plugin:

    <code>
    git clone git://github.com/kitplummer/xmpp4rails.git
    </code>

Here’s how I’ve used it - in my model I’ve got this:

    <code>
    ...
    before_create :xmpp_register?
    ...
    def xmpp_register?
        begin
          register_account(self.login + "@" + CONFIG['hostname'], self.password)
        rescue StandardError
          return false
        else
          simple_send('gateway@' + CONFIG['hostname'], 
                             'CONFIG['jabberpw'], 
                             'admin@' + CONFIG['hostname'], 
                             "new account: #{identity_url}")
          return true
        end
    end
    </code>

  
So, if the registration fails, so the does the account creation.
Obviously with the library called from the model you can do different
things with it. Notice the simple\_send method too. When an account gets
created in the app - the model sends me a notification via Jabber.

I’ve also provide a simple stub so the models can still test out
completely.

Hopefully this will be useful for someone else. I’d also love a reason
to keep extending the functionality wrapped, as well as flesh out the
tests with RSpec. Let me know.
