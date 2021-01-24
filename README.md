[![GoKEV](http://GoKEV.com/GoKEV200.png)](http://GoKEV.com/)

<div style="position: absolute; top: 40px; left: 200px;">
# Why????  WHY!?!??

This repo is full of some turn-key custom module examples, written in simple languages.  
They don't require a python guru to understand the function, and they're part of a greater
effort to demystify the interaction between Ansible and the module itself.

These are absolutely not a complete functional project.  They are meant to assist in learning
the process to build your own custom module and make it work inside a custom Ansible collection.

Current existing examples of custom modules, written in:
* Python (relatively classless, simple)
* Perl (God's perfect language)
* PHP (because who doesn't want an Ansible module written in PHP?)
* Bash (never underestimate the need for converting a shell script into a module)

# Existing (Working) Examples of custom modules all share the same basic playbook:


<pre>ansible-playbook ./custom($language).yml


---
- hosts: localhost
  gather_facts: false
  connection: local

  vars:
    - object: Pink Floyd
    - condition: comfortably numb

  tasks:
    - name: This is an ansible module written in $language
      modulename:
        object: "{{ object }}"
        condition: "{{ condition }}"
      register: modoutput
      ignore_errors: true

    - debug:
        var: modoutput
</pre>


TASK [debug] **************************************************************************************************************************
ok: [localhost] => {
    "modoutput": {
        "changed": true,
        "failed": false,
        "message": {
            "'Pink Floyd'": "Object includes a vowel aeiouyAEIOUY and therefore we will mark this as changed"
        }
    }
}
</pre>
# OR
<pre>
TASK [This is an ansible module written in $language] ***************************************************************************************
fatal: [localhost]: FAILED! => {"changed": true, "message": "Comfortably Numbz": "Condition includes a jJzZ and therefore we will mark this as failed"}}
...ignoring

TASK [debug] **************************************************************************************************************************
ok: [localhost] => {
    "modoutput": {
        "changed": true,
        "failed": true,
        "message": {
            "'Pink Floyd'": "Object includes a vowel aeiouyAEIOUY and therefore we will mark this as changed",
            "Comfortably Numbz": "Condition includes a jJzZ and therefore we will mark this as failed"
        }
    }
}

</pre>



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

* [Red Hat Ansible Automation Platform Partners](https://www.ansible.com/partners "Red Hat Ansible Automation Platform Partners")
* [Ansible Certified Content FAQ](https://access.redhat.com/articles/4916901 "Ansible Certified Content FAQ")
* [Ansible Docs on Module Creation](https://docs.ansible.com/ansible/latest/dev_guide/developing_modules_general.html "Ansible Docs on Module Creation")


Author(s) Information
------------------
* Kevin Holmes :: kev@GoKEV.com
* Phil Avery
* Add your name here.  


This project was created in 2020 by [Kevin Holmes](http://GoKEV.com/), based on the need to offer simple spoon-fed instructions for building a module.  This is, in no way, an advanced module course, no a Python lesson.  This is meant to be a very simple introduction to the conduit and to help stimulate your brain into different ways you can use it.

- 2020-01-23  Added working PHP module example
- 2020-01-14  Added working Python module example
- 2020-11-02  Working examples of Perl and Bash language modules have been added.
- Initial Update 2020-10-29 :: Documentation and overview created in hopes to evangelize the effort and the message to those who can help and contribute
