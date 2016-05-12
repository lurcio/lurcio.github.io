---
layout: post
title:  "Tidying Emacs Autosave Files"
date:   2016-05-05 16:13:45 +0100
categories: emacs
---
As part of my on again/off again quest to learn Emacs I thought I would document some of the changes I make to my configuration.

I found that Emacs was littering my filesystem with a lot of backup and autosave files. Firstly, I created a directory for the files to live in:

{% highlight bash %}
mkdir ~/.emacs-autosave
{% endhighlight %}

Then I added the following to my .emacs file to gently persuade Emacs to save the files there instead:

{% highlight elisp %}
(setq backup-directory-alist
      `((".*" . ,"~/.emacs-autosave")))
(setq auto-save-file-name-transforms
      `((".*" ,"~/.emacs-autosave" t)))
{% endhighlight %}
