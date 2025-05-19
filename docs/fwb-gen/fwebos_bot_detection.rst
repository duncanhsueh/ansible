:source: fwebos_bot_detection.py

:orphan:

.. fwebos_bot_detection.py:

fwebos_bot_detection.py -- Config FortiWeb Bot Detection Policy
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.1

.. contents::
   :local:
   :depth: 1


Synopsis
--------
Config FortiWeb Bot Detection Policy


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
 <td>fwebos_bot_detection.py</td>
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
              <li><span class="li-head"> id </span> The numerical index of bot detection policy.<span class="li-normal"> type:string 
                    maxLength:63</span></li>  
              <li><span class="li-head"> policy_id </span> The numerical policy ID of the Server Policy. It is the same one as used in CLI.<span class="li-normal"> type:string 
                    maxLength:63</span></li>  
              <li><span class="li-head"> allow_ip </span> Limit Sample Collections From IPs.<span class="li-normal"> type:list 
                    maxLength:63</span></li>  
              <li><span class="li-head"> advanced_mode </span> Enable or disable Advanced Mode. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> client_identification_method </span> Client Identification Method.<span class="li-normal"> type:string choice:
                      IP-and-User-Agent,
                      IP,
                      Cookie</span></li>
              <li><span class="li-head"> sampling_count </span> Sample Count.<span class="li-normal"> type:integer
                    maximum:1000
                    minimum:1</span></li>
              <li><span class="li-head"> sampling_count_per_client </span> Sample Count per Client per Hour. <span class="li-normal"> type:integer
                    maximum:60
                    minimum:1</span></li>
              <li><span class="li-head"> sampling_time_per_vector </span> Sampling Time per Vector. <span class="li-normal"> type:integer
                    maximum:10
                    minimum:1</span></li>
              <li><span class="li-head"> selected_model </span> Model Type for Model Building Settings.<span class="li-normal">  type:string choice:
                      Strict,
                      Moderate</span></li>
              <li><span class="li-head"> anomaly_count </span>Anomaly Count.<span class="li-normal"> type:integer
                    maximum:65535
                    minimum:1</span></li>
              <li><span class="li-head"> bot_confirmation </span> Enable or disable Bot Confirmation. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> verification_method </span> Bot Verification Method. <span class="li-normal"> type:string choice:
                      Real-Browser-Enforement,
                      Disable,
                      Captcha-Enforcement</span></li>
              <li><span class="li-head"> security </span> Select security level.<span class="li-normal"> type:string choice:
                      Info,
                      Low,
                      Medium,
                      High</span></li>       
              <li><span class="li-head"> security_action </span> Choose the action FortiWeb takes when a user client is confirmed as a bot.<span class="li-normal"> type:string choice:
                      alert,
                      deny_no_log,
                      alert_deny,
                      block-period,
                      client-id-block-period,</span></li>
              <li><span class="li-head"> block_period </span> Block Period.<span class="li-normal"> type:integer
                    maximum:3600
                    minimum:1</span></li>
              <li><span class="li-head"> security </span> Select security level.<span class="li-normal"> type:string choice:
                      Info,
                      Low,
                      Medium,
                      High</span></li>
              <li><span class="li-head"> trigger </span> Select the trigger policy, if any, that FortiWeb carries out when it logs and/or sends an alert email about a violation.<span class="li-normal"> type:string 
                    maxLength:255 </span></li>  
              <li><span class="li-head"> global_exception </span> Select New Bot Mitigation Exception Policy.<span class="li-normal"> type:string 
                    maxLength:255 </span></li>  
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
    - name: add a bot detection policy
      fwebos_bot_detection:
        action: add 
        policy_id: 6814698978843458079
        allow_ip:
          - 11.2.3.4
          - 192.168.253.1

    - name: get a bot detection policy
      fwebos_bot_detection:
        action: get 
        id: 1

    - name: edit a bot detection policy
      fwebos_bot_detection:
        action: edit 
        id: 1
        anomaly_count: 14456
        sampling_count: 999
        security_action: alert_deny
    
    - name: delete a bot detection policy
      fwebos_bot_detection:
        action: delete 
        id: 1

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