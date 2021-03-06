RuMeMe
======

Ruby SDK for Message Media SMS Gateway API.
Since Message Media doesn't provide any ruby projects support, we decided to port it from available SDKs (mainly from PHP SDK; and some .NET usage).
For more information checkout [Message Media SMS APIs](http://www.message-media.com/sms-gateway.html).

Help
====

Installation
------------

Just execute

    gem install rumeme

Usage
-----

First, add Rumeme initialization

```ruby
Rumeme.configure do |config|
  config.username = 'xxx'
  config.password = 'yyy'
  config.use_message_id = true
  config.secure = true
 config.allow_splitting = false
  config.allow_long_messages = true
end
```

Where xxx and yyy is your username and password consequently.
Then you can use SmsInterface class to add and send messages.

```ruby
si = SmsInterface.new

si.add_message :phone_number => 'xxxxxxxxxxx', :message => 'Message text 1'
si.add_message :phone_number => 'xxxxxxxxxxx', :message => 'Message text 2'
si.add_message :phone_number => 'xxxxxxxxxxx', :message => 'Message text 3'
si.add_message :phone_number => 'xxxxxxxxxxx', :message => 'Message text 4'
si.add_message :phone_number => 'xxxxxxxxxxx', :message => 'Message text 5'

si.send_messages
```

Where xxxxxxxxxxx is phone number.

To Do
=====

* Refactoring to make api more rubyish,
* Add unit tests,

Credits
=======

RuMeMe is maintained by Anatoliy Plastinin, and is funded by [Cloud Castle, LLC](http://cloudcastlegroup.com/).

Contributors
============

* Stan Carver II
* Rafael Fonseca

License
=======

Still looking for license. But the software is provided "as is", without warranty of any kind.
