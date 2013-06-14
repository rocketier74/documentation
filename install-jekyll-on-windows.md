---
layout: default
title: How to Install Ruby and Jekyll on Windows
---

How To Install Ruby and Jekyll on Windows
===

1. If Ruby is not installed, download RubyInstaller Version 1.9.3 (have not tried Version 2.0) from <http://rubyinstaller.org/downloads/>
2. Install RubyInstaller to any whitespace free location e.g. ```C:\ruby_1.9.3```
3. Download "Development Kit" from <http://rubyinstaller.org/downloads/> (see "Which Development Kit?" for the right version)
4. unpack "Development Kit" files to e.g. ```C:\ruby_1.9.3\DevKit```
8. Create a shortcut within the *ruby_home* folder with the following link
   - Ziel/Target: ```C:\Windows\System32\cmd.exe /E:ON /K C:\ruby1.9.3\bin\setrbvars.bat```
   - Ausführen in/Excecute in: ```%USERPROFILE%```
5. open ruby command line (use the created shortcut) and go to the DevKit folder
   - type ```ruby dk.rb init```
   - check config.yml in the DevKit folder and edit it to your concerns (check the path to ruby)
   - type ```ruby dk.rb install```
6. Install required gems type following commands in ruby command (see [Developers Guide]({{site.url}}/developers-guide.html#install_required_gems) for an updated gem list)
   - ```gem install jekyll   # needed for testing building the site```
   - ```gem install RedCloth # needed for .md rendering```
   - ```gem install serve    # needed for resolving .html files w/o extension```
7. extend ```ruby_home/bin/setrbvars.bat```, if you get "error: incompatible character encodings: UTF-8 and CP850.", with the following (see [below](#setrbvars_does_not_exist) if strbvars.bat does not exist):
   - ```set LC_ALL=en_US.UTF-8```
9. use the created shortcut to open the Ruby Console
   - go to your jekyll project e.g. ```cd %userprofile%\tmp\github-pages\```
   - start jekyll using[^jekyll_serve_config]
   {% highlight bash %}jekyll serve --watch --config _config.yml,_config_local.yml
   {% endhighlight %}
    - open your browser and visit <http://localhost:4000>

*setrbvars* does not exist
---
if setrbvars.bat does not exist, create it with the following content:

{% highlight bash %}
@ECHO OFF
REM Determine where is RUBY_BIN (where this script is)
PUSHD %~dp0.
SET RUBY_BIN=%CD%
POPD

REM Add RUBY_BIN to the PATH
REM RUBY_BIN takes higher priority to avoid other tools
REM conflict with our own (mainly the DevKit)
SET PATH=%RUBY_BIN%;%PATH%
SET RUBY_BIN=

set LC_ALL=en_US.UTF-8
REM set LANG=en_US.UTF-8

REM Display Ruby version
ruby.exe -v
{% endhighlight %}

[^jekyll_serve_config]: With explicitly specifying the config files we overwrite parameters in the first config file with parameters specified in the second config file, thus we can define in the second file e.g. a local url.