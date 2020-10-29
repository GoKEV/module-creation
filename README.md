[![GoKEV](http://GoKEV.com/GoKEV200.png)](http://GoKEV.com/)

<div style="position: absolute; top: 40px; left: 200px;">

# module-creation

This is a project to help teach the concepts behind Ansible modules -- how they work and how to create your own.  As this is a WIP, the general outline for the project is to divide the work into a few sections: 
1. Ansible basics (deck / doc)
   * This will be the foundational baseline knowledge.
   * To proceed beyond this section, users should have a general understanding of Ansible and ability to write a playbook
2. Understanding how modules work in relation to Ansible (deck / doc / example module)
   * Examples of add-on modules in the ./library/ directory of a role
   * Demonstration of how input is received to the module
   * Seeing how advanced Python code can parse / process / digest data inside the module
   * Understanding the output from the module
   * Additional items?  Debug, check, required pieces... plenty I'm sure could be added here
3. Example working code
   * A ready-made file with demo functionality already working
   * Example playbook to leverage the module
   * Should be operable without any additional python libraries -- drop it in place and use it
   * 2 or 3 variations where this example code could be modified for different results (either in input types, output format, or function)


## Become A Certified Red Hat Content Provider:

Please visit these links to learn more about certifying your content and partnering with Red Hat.  It's actually quite simple and great for recognition that your modules have gone the extra step to be recognized and supportable:

* [Red Hat Ansible Automation Platform Partners](https://www.ansible.com/partners "Red Hat Ansible Automation Platform Partners"){:target="_blank"}
* [Ansible Certified Content FAQ](https://access.redhat.com/articles/4916901 "Ansible Certified Content FAQ"){:target="_blank"}



Author(s) Information
------------------
Kevin Holmes :: kev@GoKEV.com
Add your name here.  


This project was created in 2020 by [Kevin Holmes](http://GoKEV.com/), based on the need to offer simple spoon-fed instructions for building a module.  This is, in no way, an advanced module course, no a Python lesson.  This is meant to be a very simple introduction to the conduit and to help stimulate your brain into different ways you can use it.

- Initial Update 2020-10-29 :: Documentation and overview created in hopes to evangelize the effort and the message to those who can help and contribute
