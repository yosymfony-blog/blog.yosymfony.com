---
layout: post
author: Víctor
title: "Exception classes without &quot;Exception&quot; suffix?"
categories: []
tags: []
header_img:
  url: "header-code.png"
  author: "Yuri Samoilov"
  author_url: "https://flic.kr/p/mjhDwB"
---
<blockquote class="twitter-tweet" data-lang="es"><p lang="en" dir="ltr">Try to remove the &quot;Exception&quot; suffix of your exceptions. Forces you to choose good names!</p>&mdash; Bernhard Schussek (@webmozart) <a href="https://twitter.com/webmozart/status/768463723254124544">24 de agosto de 2016</a></blockquote>

Exceptions are a mechanic of most programming languages used to express exceptional situations
to the normal flow of a program execution. Exceptions are represented by classes
that typically extend from a base class provided by the language. Each language
has its own convencion for naming. In case of PHP, every not regular class should
be visible by suffixes: `Exception`, `Interface`, `Trait` or `Abstract` but, sometime,
as Bernhard Schussek ([@webmozart](https://twitter.com/webmozart)) said in his twit,
the use of `Exception` suffix leads developers to be lazy at naming.

```
class UserNotification
{
    public function sendWelcomeMessage()
    {
        try {
            $mailManager = new MailManager($this->user->getEmail(), $this->user->getName());
        } catch (EmailException $e) {
            ...
        }
    }
}
```

In the prior example, to use a single exception to communicate all exceptional things
occurring during an Email sending could be poor although that depends on your situation.
Maybe, a more appropriate code could be the following:

```
class UserNotification
{
    public function sendWelcomeMessage()
    {
        try {
            $mailManager = new MailManager($this->user->getEmail(), $this->user->getName(), $content);
        } catch (EmailNotDeliverable $e) {
            ...
        } catch (EmailMessage $e) {
                ...
        } catch (SmtpException $e) {
            ...
        }
    }
}
```

In the previous snippet of code, `EmailNotDeliverable` could be used to communicate
issues related with the email delivery (address not valid or non-existent),
`EmailMessage` for issues related with the body of the Email (null content for example)
and `SmtpException` for all issues related with the connection between your code
and the SMTP server: operation timed out, bad authentication... etc.

Exceptions are regular classes that follow the same rules that the others.
Finding an appropriate name is just the beginning.
