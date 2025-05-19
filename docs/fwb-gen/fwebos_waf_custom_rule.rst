:source: fwebos_waf_custom_rule.py

:orphan:

.. fwebos_waf_custom_rule.py:

fwebos_waf_custom_rule.py -- Config FortiWeb Advanced Protection Custom Policy Rule
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.1

.. contents::
   :local:
   :depth: 1


Synopsis
--------
Config FortiWeb Advanced Protection Custom Policy Rule


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
 <td><code class="docutils literal notranslate">v7.0.x </code></td>
 <td><code class="docutils literal notranslate">v7.2.x </code></td>
 <td><code class="docutils literal notranslate">v7.4.x </code></td>
 <td><code class="docutils literal notranslate">v7.6.x </code></td>
 </tr>
 <tr>
 <td>fwebos_waf_custom_rule.py</td>
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
              <li><span class="li-head"> name </span> A unique name that can be referenced in other parts of the configuration.<span class="li-normal"> type:string 
                    maxLength:63</span></li>
              <li><span class="li-head"> security_action </span> Select which action the FortiWeb appliance will take when it detects a violation of the rule.<span class="li-normal"> type:string choice:
                      alert,
                      redirect,
                      deny_no_log,
                      block-period,
                      client-id-block-period</span></li>       
              <li><span class="li-head"> severity </span> Select which severity level the FortiWeb appliance will use when it logs a violation of the rule.<span class="li-normal"> type:string choice:
                      Info,
                      Low,
                      Medium,
                      High</span></li>     
              <li><span class="li-head"> trigger </span> Select which trigger, if any, that the FortiWeb appliance will use when it logs and/or sends an alert email about a violation of the rule.<span class="li-normal"> type:string 
                    maxLength:63</span></li> 
              <li><span class="li-head"> bot_confirmation </span> Enable to confirm if the client is indeed a bot.<span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li> 
              <li><span class="li-head"> bot_recognition </span> Select what type of bots the client is.<span class="li-normal"> type:string choice:
                      enable,
                      real-browser-enforcement,
                      captcha-enforcement</span></li> 
              <li><span class="li-head"> validation_timeout </span> FortiWeb applies the actions in 'trigger' if the client fails the test or does not return results before the Validation Timeout expires. <span class="li-normal"> type:string </span></li>
              <li><span class="li-head"> max_attempt_times </span> FortiWeb applies the actions in 'trigger' if the client cannot successfully fulfill the request within the 'max_attempt_times'. <span class="li-normal"> type:string </span></li>   
              <li><span class="li-head"> mobile_app_identification </span> Available only when Mobile Application Identification is enabled.<span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>                                    
        <li><span class="li-head">mkey</span> If present, objects will be filtered on property with this name <span class="li-normal"> type:string </span></li><li><span class="li-head">vdom</span> Specify the Virtual Domain(s) from which results are returned or changes are applied to. If this parameter is not provided, the management VDOM will be used. If the admin does not have access to the VDOM, a permission error will be returned. The URL parameter is one of: vdom=root (Single VDOM) vdom=vdom1,vdom2 (Multiple VDOMs) vdom=* (All VDOMs)   <span class="li-normal"> type:array </span></li><li><span class="li-head">clone_mkey</span> Use *clone_mkey* to specify the ID for the new resource to be cloned.  If *clone_mkey* is set, *mkey* must be provided which is cloned from.   <span class="li-normal"> type:string </span></li>
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
    - name: add a rule
      fwebos_waf_custom_rule:
       action: add 
       name: test1
       security_action: alert
       severity: Medium
       block_period: 500
       bot_confirmation: enable
       bot_recognition: real-browser-enforcement
       mobile_app_identification: disabled
       validation_timeout: 30
       trigger: tp1

    - name: get a rule
      fwebos_waf_custom_rule:
       action: get 
       name: test1

    - name: edit a rule
      fwebos_waf_custom_rule:
       action: edit 
       name: test1
       severity: High
       security_action: client-id-block-period
       block_period: 400
       bot_confirmation: disable

    - name: delete a rule
      fwebos_waf_custom_rule:
       action: delete 
       name: test1

    - name: delete a rule
      fwebos_waf_custom_rule:
       action: delete 
       name: test1

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