Aim of this Project
------

This project is the first attempt to establish a cooperation between German universities which use Moodle as an e-Learning platform and need a simple manual for their users.
The aim is not to replace the official moodle documentation under <docs.moodle.org/‎>, instead it should give a university-focused overview about moodle and reference to <docs.moodle.org/> for detailed information.
This manual should be configurable, in the way that the e-learning providers at the universities can fork this project, edit \_config.yml and enable only pages they need.
In the best scenario this would be it. 

Usually, there are some university specific customizations. Hopefully these university specific customizations could be handled with adding additional private chapters and changing content in \_includes/uni-spezifisch.

Possible Future Changes:
======
- Tagging pages with moodle activities in such a way, that the university specifies activities they use in \_config.yml and then pages documenting activities that are not specified are disabled.
- tagging pages with a target audience: [student, teacher, all(?)] to generate student and teacher specific manuals.
- section FAQ based on Jekylls blogging functionality. With tagging, tag clouds and maybe a quick search

Why GIT
------
It is easy to share content, other universities can easily maintain there own changes while keeping the documentation up to date.

Why Jekyll
------

This manual is currently implemented as a jekyll site. Jekyll lets us focus on content during writing, thus layout and any boilerplate code is not within the focus.

* [Site](http://jekyllrb.com/)
* [Code](https://github.com/mojombo/jekyll)
* [Wiki](https://github.com/mojombo/jekyll/wiki)

License
-------

This site and all contributions are [licensed]({{site.url}}/LICENSE-CC-BY) under the Creative Commons Attribution 3.0 Unported (CC BY 3.0) license. By submitting information to this site you agree to grant this license to all users of the site, and that your editing of the authors page constitutes satisfactory attribution.