
Release Notes
==============================

|

Release Galaxy 1.3.2
--------------------

Release Targets
^^^^^^^^^^^^^^^

FortiWeb Galaxy 1.3.2 is based on 1.3.2.

Features
^^^^^^^^^^^^^^^
- Add Ansible check mode support.
- Add Ansible diff mode support.

Notice
^^^^^^^^^^^^^^^
- Please run 'ansible-galaxy collection install fortinet.fortiweb' again to update libraries after upgrade to 1.3.2.

Release Galaxy 1.3.1
--------------------

Release Targets
^^^^^^^^^^^^^^^

FortiWeb Galaxy 1.3.1 is based on 1.3.0.

Features
^^^^^^^^^^^^^^^
- Add Application Delivery Modules(Site Publish, URL Rewriting, Waiting Room).
- Add Advanced Protection Modules(Data Loss Prevention).
- Add Bot Mitigation Modules(Known Bots, ML Based Bot Detection).
- Add API Protection Modules(JSON Protection, ML Based API Protection).
- Add error handling when checking VDOM status.
- FortiWeb version: v7.2.x, v7.4.x and v7.6.x.

Notice
^^^^^^^^^^^^^^^
- Please run 'ansible-galaxy collection install fortinet.fortiweb' again to update libraries after upgrade to 1.3.1.

Release Galaxy 1.3.0
--------------------

Release Targets
^^^^^^^^^^^^^^^

FortiWeb Galaxy 1.3.0 is based on 1.2.0.

Features
^^^^^^^^^^^^^^^
- Add HTTP Content Routing modules.
- Add support of HTTP/3 service and redirect-naked-domain configuration in Server Policy module
- Add Advanced Protection Modules(HTTP Header Security, Custom Policy, and CSRF Protection).
- Add 'fwebos_json_generic.py', a module can send HTTP requests to the API of all FortiWeb configuration services
- FortiWeb version: v7.2.x, v7.4.x and v7.6.x.

Release Galaxy 1.2.0
--------------------

Release Targets
^^^^^^^^^^^^^^^

FortiWeb Galaxy 1.2.0 is based on 1.0.1.

Features
^^^^^^^^^^^^^^^
- Add idempotency support.
- FortiWeb version: v7.2.x, v7.4.x and v7.6.x.

Notice
^^^^^^^^^^^^^^^
- When users attempt to add a duplicated entry, the ansible modules will not execute the action and generate message "A duplicate entry has already existed.". However, the ansible modules do not consider this action 'failed' and will continue executing the following tasks in a playbook.
- When users attempt to edit or delete a non-existent entry, the ansible modules will not execute the action and generate message "The entry is not found.". However, the ansible modules do not consider this action 'failed' and will continue executing the following tasks in a playbook. 

Release Galaxy 1.0.1
--------------------

Release Targets
^^^^^^^^^^^^^^^

FortiWeb Galaxy 1.0.1 is based on 1.0.0.

Features
^^^^^^^^^^^^^^^
- Add document.
- FortiWeb JRPC URLs coverage (82 modules).
- FortiWeb version: v7.0.0, v7.0.1, v7.0.2 and v7.0.3.

Release Galaxy 1.0.0
--------------------

Release Targets
^^^^^^^^^^^^^^^

It is the initial release of FortiWeb Ansible Project.

Features
^^^^^^^^^^^^^^^
- FortiWeb JRPC URLs coverage (78 modules).
- FortiWeb version: v7.0.0, v7.0.1 and v7.0.2.

