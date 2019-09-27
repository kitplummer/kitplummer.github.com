---
layout: post
title: Phidgets and Ruby...
---

![](http://www.phidgets.com/images/2001tn.jpg)

Well, I’ve been looking for a reason to play with
[JRuby](http://jruby.codehaus.org/) for some time now. It finally came
time, in the shape of a [Phidgets](http://www.phidgets.com) servo. Ok,
so maybe it isn’t “Phidgets and Ruby” exactly. I can’t say what I’m
using the Phidgets for but being able to access them from
[Ruby](http://www.ruby-lang.org) is a huge bonus (if for no other reason
than I prefer looking at Ruby). Problem is…no Ruby API to access them
directly. Python yes, Ruby no. Although I really have nothing against
[Python](http://www.python.org) this particular project already
implicates Java. So, what’s one more library like JRuby?

I will admit that I had quite a few problems getting through outdated
documentation for JRuby. Just getting setup with the initial ‘include
Java’ instead of ‘require java’ was almost torture. Ruby community’s
documentation is already suspect - therefore JRuby must just want to
follow suit \[Ruby itself, is fairly well
[documented](http://www.ruby-doc.org/) - thanks to James and the Happy
Camper guys\]. Then I had to figure out how to work the Java interfaces
for the servo’s “attach” listener. The documentation for how to do this
is a bit of a struggle too. Just need to remember that JRuby is early
1.x version.

I was actually able to get Phidget servo to respond and set it to a
given position. Cool. And, I will admit the code is much cleaner,
simpler and a lot less of it.

    <code>
    include Java

    require 'phidget21.jar'

    include_class Java::com.phidgets.ServoPhidget
    include_class Java::com.phidgets.event.AttachListener
    include_class Java::com.phidgets.event.AttachEvent
    include_class Java::com.phidgets.PhidgetException

    class ServoAttachListener

      servo = ServoPhidget.new()

      def attached(ae)
        begin
          puts "Getting Device Name..."
          servo = ae.getSource()
          puts "Device Name: " + servo.getDeviceName()

          puts "Getting Servo Count..."
          puts "Servo Count: " + servo.getMotorCount().to_s

          puts "Getting Servo Max Position..."
          puts "Position: " + servo.getPositionMax(0).to_s

          puts "Getting Servo Min Position..."
          puts "Position: " + servo.getPositionMin(0).to_s

          puts "Setting Servo to Max Position..."
          servo.setPosition(0, 232.0)

        rescue PhidgetException => e
          puts "Java or Ruby exception: #{e}"
          raise
        end
      end

    end

    puts "Hello Phidget Servo"

    servo = ServoPhidget.new()
    attach_listener = ServoAttachListener.new()

    servo.addAttachListener(attach_listener)
    servo.openAny()

    while true

    end
    puts "Goodbye Phidget Servo"
    </code>
