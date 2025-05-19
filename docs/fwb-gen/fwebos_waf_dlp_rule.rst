:source: fwebos_waf_dlp_rule.py

:orphan:

.. fwebos_waf_dlp_rule.py:

fwebos_waf_dlp_rule.py -- Config FortiWeb Data Loss Preventation Rule
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.1

.. contents::
   :local:
   :depth: 1


Synopsis
--------
Config FortiWeb Data Loss Preventation Rule


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
 <td>fwebos_waf_dlp_policy.py</td>
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
                      alert_deny,
                      block-period</span></li>
              <li><span class="li-head"> severity </span> Select which severity level FortiWeb uses when it logs a CSRF attack.<span class="li-normal"> type:string choice:
                      Info,
                      Low,
                      Medium,
                      High</span></li>    
              <li><span class="li-head"> host_status </span> Enable to apply this rule only to HTTP requests for specific web hosts. Disable to match the rule based on the URL and any parameter filter only.<span class="li-normal"> type:string choice:
                      enable,
                      disable,</span></li>   
              <li><span class="li-head"> host </span> Enter the IP address or FQDN of the host to which the DLP rule will be applied. Only available if Host Status is enabled.<span class="li-normal"> type:string 
                    maxLength:255</span></li> 
              <li><span class="li-head"> url_type</span> Simple string or regular expression <span class="li-normal"> type:string choice:
                      plain,
                      regular</span></li>
              <li><span class="li-head"> url </span> Expression to specify the URL.<span class="li-normal"> type:string 
                    maxLength:255 </span></li>    
              <li><span class="li-head"> direction </span> simple string or regular expression <span class="li-normal"> type:string choice:
                      request,
                      response,
                      both</span></li>
              <li><span class="li-head"> type </span> What type of data FortiWeb will scan.<span class="li-normal"> type:string choice:
                      http-payload,
                      files</span></li>     
              <li><span class="li-head"> email_attachments</span> Enable Attachments in Email to restrict the file scan exclusively to attachments in emails. Available only when 'files' is selected in Type. <span class="li-normal"> type:string choice:
                      enable,
                      disable,</span></li>   
              <li><span class="li-head"> owa_protocol</span> OWA Protocol. If enabled, FortiWeb will scan attachments in Email sent and received via a web browser login.<span class="li-normal"> type:string choice:
                      enable,
                      disable,</span></li>   
              <li><span class="li-head"> activesync_protocol </span> ActiveSync Protocol. If enabled, FortiWeb will scan attachments in Email sent and received via a mobile phone login. <span class="li-normal"> type:string choice:
                      enable,
                      disable,</span></li>
              <li><span class="li-head"> mapi_protocol </span> MAPI Protocol. If enabled, FortiWeb will scan attachments in Email sent and received via the Messaging Application Programming Interface (MAPI), a transport protocol implemented in Microsoft Exchange Server 2013 Service Pack 1 (SP1). <span class="li-normal"> type:string choice:
                      enable,
                      disable,</span></li>   
              <li><span class="li-head"> block_period </span> Enter the amount of time (in seconds) that you want to block subsequent requests from the same IP address after FortiWeb detects a DLP rule violation. This setting is available only when Data Loss Prevention is set to Period Block. The valid range is 1–3,600<span class="li-normal"> type:string 
                    maxLength:63</span></li>   
              <li><span class="li-head"> trigger </span> Select the trigger policy, if any, that FortiWeb carries out when it logs and/or sends an alert email about a DLP rule violation.<span class="li-normal"> type:string 
                    maxLength:255 </span></li>  
              <li><span class="li-head"> sensor </span> Select the DLP sensor.<span class="li-normal"> type:string 
                    maxLength:255 </span></li>                         
        <li><span class="li-head">mkey</span> If present, objects will be filtered on property with this name <span class="li-normal"> type:string </span></li><li><span class="li-head">vdom</span> Specify the Virtual Domain(s) from which results are returned or changes are applied to. If this parameter is not provided, the management VDOM will be used. If the admin does not have access to the VDOM, a permission error will be returned. The URL parameter is one of: vdom=root (Single VDOM) vdom=vdom1,vdom2 (Multiple VDOMs) vdom=* (All VDOMs)   <span class="li-normal"> type:array </span></li><li><span class="li-head">clone_mkey</span> Use *clone_mkey* to specify the ID for the new resource to be cloned.  If *clone_mkey* is set, *mkey* must be provided which is cloned from.   <span class="li-normal"> type:string </span></li>
  </ul>

Examples
--------
.. code-block:: yaml+jinja

---
- name:
  hosts: all
  vars:
  connection: httpapi
  gather_facts: false
  tasks:
    - name: add a policy of http payload type 
      fwebos_waf_dlp_rule:
       action: add 
       name: dlp3
       security_action: block-period
       severity: High
       host_status: enable
       url_type: plain
       direction: request
       type: http-payload
       block_period: 500
       host: myhost
       url: /folder2/*
       trigger: tp1
       sensor: sensor1

    - name: add a policy of file type
      fwebos_waf_dlp_rule:
       action: add 
       name: dlp4
       security_action: alert
       severity: Low
       host_status: enable
       direction: request
       type: files
       trigger: tp1
       sensor: sensor1     
       email_attachments: enable
       owa_protocol: enable
       activesync_protocol: disable
       mapi_protocol: disable

    - name: get a policy of file type
      fwebos_waf_dlp_rule:
       action: get 
       name: dlp4

    - name: edit a policy of file type
      fwebos_waf_dlp_rule:
       action: edit 
       name: dlp4
       security_action: alert
       severity: Info
       activesync_protocol: enable
       mapi_protocol: enable

    - name: delete a policy
      fwebos_waf_dlp_rule:
       action: delete 
       name: dlp4




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