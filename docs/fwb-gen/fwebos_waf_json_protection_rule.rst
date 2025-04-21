:source: fwebos_waf_json_protection_rule.py

:orphan:

.. fwebos_waf_json_protection_rule.py:

fwebos_waf_json_protection_rule.py -- Config FortiWeb JSON Protection Rule
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.1

.. contents::
   :local:
   :depth: 1


Synopsis
--------
Config FortiWeb JSON Protection Rule


Requirements
------------
The below requirements are needed on the host that executes this module.

- ansible>=2.11


FortiWeb Version Compatibility
------------------------------


.. raw:: html

 <br>
 <table>
 <tr>
 <td></td>
 <td><code class="docutils literal notranslate">v7.0.0 </code></td>
 <td><code class="docutils literal notranslate">v7.0.1 </code></td>
 <td><code class="docutils literal notranslate">v7.0.2 </code></td>
 <td><code class="docutils literal notranslate">v7.0.3 </code></td>
 </tr>
 <tr>
 <td>fwebos_waf_json_protection_rule.py</td>
 <td>yes</td>
 <td>yes</td>
 <td>yes</td>
 <td>yes</td>
 </tr>
 </table>
 <p>



Parameters
----------


.. raw:: html


  <ul>
  <li><span class="li-head">body</span> Possible parameters to go in the body for the request <span class="li-required">required: True </li>
        <ul class="ul-self">
              <li><span class="li-head"> name </span> name of the JSON protection rule<span class="li-normal"> type:string 
                    maxLength:63</span></li>
              <li><span class="li-head"> host_status </span> Enable to compare the JSON rule to the Host. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li> 
              <li><span class="li-head"> host </span> Select the IP address or FQDN of a protected host. <span class="li-normal"> type:string 
                    maxLength:255</span></li> 
              <li><span class="li-head"> request_type</span> URL Type. Simple string ('plain') or regular expression ('regular'). <span class="li-normal"> type:string choice:
                      plain,
                      regular</span></li>   
              <li><span class="li-head"> request_url </span> Post URL. <span class="li-normal"> type:string 
                    maxLength:255</span></li>
              <li><span class="li-head"> json_limits </span> Enable to define limits for data size, key, and value, etc. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li> 
              <li><span class="li-head"> json_data_size </span> Total Size of JSON Data.<span class="li-normal"> type:integer
                    maximum:10240
                    minimum:1</span></li> 
              <li><span class="li-head"> key_size </span> Key Size.<span class="li-normal"> type:integer
                    maximum:10240
                    minimum:1</span></li>   
              <li><span class="li-head"> key_number </span> Total Key Number.<span class="li-normal"> type:integer
                    maximum:2147483647
                    minimum:1</span></li> 
              <li><span class="li-head"> value_size </span> Enter the value size of each key.<span class="li-normal"> type:integer
                    maximum:10240
                    minimum:1</span></li>  
              <li><span class="li-head"> value_number_in_array </span>Enter the total value number of each JSON file. <span class="li-normal"> type:integer
                    maximum:10240
                    minimum:1</span></li>       
              <li><span class="li-head"> object_depth </span>Enter the number of the nested objects. <span class="li-normal"> type:integer
                    maximum:2147483647
                    minimum:1</span></li> 
              <li><span class="li-head"> schema_type</span> URL Type. Simple string ('plain') or regular expression ('regular'). <span class="li-normal"> type:string choice:
                      schema-group,
                      single-schema</span></li>   
              <li><span class="li-head"> schema_file </span> According to your selection in Schema Type, enter the name of either the schema file. <span class="li-normal"> type:string 
                    maxLength:255</span></li>   
              <li><span class="li-head"> schema_group </span> According to your selection in Schema Type, enter the name of either the schema group. <span class="li-normal"> type:string 
                    maxLength:255</span></li>     
              <li><span class="li-head"> security_action </span> Select which action FortiWeb takes when it detects a JSON protection rule violation.<span class="li-normal"> type:string choice:
                      alert,
                      redirect,
                      alert_deny,
                      deny_no_log,
                      block-period,
                      send_403_forbidden,
                      client-id-block-period</span></li>      
              <li><span class="li-head"> block_period </span>Enter the amount of time (in seconds) that you want to block subsequent requests from a client after FortiWeb detects a rule violation. <span class="li-normal"> type:integer
                    maximum:3600
                    minimum:1</span></li>                                                                                                                                    
              <li><span class="li-head"> severity </span> Select which severity level FortiWeb uses when it logs a CSRF attack.<span class="li-normal"> type:string choice:
                      Info,
                      Low,
                      Medium,
                      High</span></li>
              <li><span class="li-head"> trigger </span> Select the trigger, if any, that FortiWeb uses when it logs or sends an alert email about a CSRF attack.<span class="li-normal"> type:string </span></li>    
        <li><span class="li-head">mkey</span> If present, objects will be filtered on property with this name  <span class="li-normal"> type:string </span></li><li><span class="li-head">vdom</span> Specify the Virtual Domain(s) from which results are returned or changes are applied to. If this parameter is not provided, the management VDOM will be used. If the admin does not have access to the VDOM, a permission error will be returned. The URL parameter is one of: vdom=root (Single VDOM) vdom=vdom1,vdom2 (Multiple VDOMs) vdom=* (All VDOMs)   <span class="li-normal"> type:array </span></li><li><span class="li-head">clone_mkey</span> Use *clone_mkey* to specify the ID for the new resource to be cloned.  If *clone_mkey* is set, *mkey* must be provided which is cloned from.   <span class="li-normal"> type:string </span></li>
  </ul>

Examples
--------
.. code-block:: yaml+jinja

   - name:
   hosts: all
   vars:
   connection: httpapi
   gather_facts: false
   tasks:
    - name: add a json protection rule
      fwebos_waf_json_protection_rule:
        action: add 
        name: jspr1
        severity: High
        host_status: enable
        host: myhost2
        request_type: plain
        request_file: /folder1/f2
        security_action: alert
        block_period: 600
        severity: Low
        trigger: tp1
        schema_type: single-schema
        schema_file: js1
        json_limits: disable


    - name: get a json protection rule
      fwebos_waf_json_protection_rule:
        action: get 
        name: jspr1

    - name: edit a json protection rule
      fwebos_waf_json_protection_rule:
        action: edit 
        name: jspr1
        severity: Low
        json_limits: enable
        json_data_size: 1034
        key_size: 69
        key_number: 300
        value_size: 128
        value_number: 256
        value_number_in_array: 256
        object_depth: 32
        schema_type: schema-group
        schema_group: jsg1

    - name: delete a json protection rule
      fwebos_waf_json_protection_rule:
        action: delete 
        name: jspr1


Return Values
-------------
Common return values are documented: https://docs.ansible.com/ansible/latest/reference_appendices/common_return_values.html#common-return-values, the following are the fields unique to this module:

.. raw:: html

    <ul><li><span class="li-return"> 200 </span> : OK: Request returns successful</li>
      <li><span class="li-return"> 400 </span> : Bad Request: Request cannot be processed by the API</li>
      <li><span class="li-return"> 401 </span> : Not Authorized: Request without successful login session</li>
      <li><span class="li-return"> 403 </span> : Forbidden: Request is missing CSRF token or administrator is missing access profile permissions.</li>
      <li><span class="li-return"> 404 </span> : Resource Not Found: Unable to find the specified resource.</li>
      <li><span class="li-return"> 405 </span> : Method Not Allowed: Specified HTTP method is not allowed for this resource. </li>
      <li><span class="li-return"> 413 </span> : Request Entity Too Large: Request cannot be processed due to large entity </li>
      <li><span class="li-return"> 424 </span> : Failed Dependency: Fail dependency can be duplicate resource, missing required parameter, missing required attribute, invalid attribute value</li>
      <li><span class="li-return"> 429 </span> : Access temporarily blocked: Maximum failed authentications reached. The offended source is temporarily blocked for certain amount of time.</li>
      <li><span class="li-return"> 500 </span> : Internal Server Error: Internal error when processing the request </li>
      
    </ul>

For errorcode please check FortiWeb API errorcode at : https://documenter.getpostman.com/view/11233300/TVetbkaK#887b9eb4-7c13-4338-a8db-16cc117f0119

Status
------

- This module is not guaranteed to have a backwards compatible interface.


Authors
-------

- Joseph Chen

.. hint::
	If you notice any issues in this documentation, you can create a pull request to improve it.