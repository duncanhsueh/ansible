:source: fwebos_waf_known_bots.py

:orphan:

.. fwebos_waf_known_bots.py:

fwebos_waf_known_bots.py -- Config FortiWeb Known Bots
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.1

.. contents::
   :local:
   :depth: 1


Synopsis
--------
Config FortiWeb Known Bots


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
 <td>fwebos_waf_known_bots.py</td>
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
              <li><span class="li-head"> dos_status</span> Enable or disable the DoS Bot check for this rule. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li> 
              <li><span class="li-head"> dos_action</span> Select the action that FortiWeb takes when it detects a DoS Bot violation of the rule. <span class="li-normal"> type:string choice:
                      bypass,
                      alert
                      alert_deny,
                      redirect,
                      deny_no_log,
                      block-period,
                      send_http_response</span></li> 
              <li><span class="li-head"> dos_severity</span> Select which severity level the FortiWeb appliance will use when it logs a violation of the rule. <span class="li-normal"> type:string choice:
                      Low,
                      Medium,
                      High,
                      Info</span></li>     
              <li><span class="li-head"> dos_threat_weight</span> Set the weight for the threat. <span class="li-normal"> type:string choice:
                      informational,
                      low,
                      moderate,
                      substantial,
                      severe,
                      critical</span></li>  
              <li><span class="li-head"> dos_trigger </span> Select which trigger, if any, that the FortiWeb appliance will use when it logs and/or sends an alert email about a violation of each rule.<span class="li-normal"> type:string 
                    maxLength:63</span></li>   
              <li><span class="li-head"> dos_block_period</span> The number of seconds that you want to block subsequent requests from the client after the FortiWeb appliance detects that the client has violated the rule. Only available when 'dos_action' is 'block-period'.<span class="li-normal"> type:string 
                    maxLength:63</span></li>      
              <li><span class="li-head"> spam_status</span> Enable or disable the Spam Bot check for this rule. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li> 
              <li><span class="li-head"> spam_action</span> Select the action that FortiWeb takes when it detects a spam Bot violation of the rule. <span class="li-normal"> type:string choice:
                      bypass,
                      alert
                      alert_deny,
                      redirect,
                      deny_no_log,
                      block-period,
                      send_http_response</span></li> 
              <li><span class="li-head"> spam_severity</span> Select which severity level the FortiWeb appliance will use when it logs a violation of the rule. <span class="li-normal"> type:string choice:
                      Low,
                      Medium,
                      High,
                      Info</span></li>     
              <li><span class="li-head"> spam_threat_weight</span> Set the weight for the threat. <span class="li-normal"> type:string choice:
                      informational,
                      low,
                      moderate,
                      substantial,
                      severe,
                      critical</span></li>  
              <li><span class="li-head"> spam_trigger </span> Select which trigger, if any, that the FortiWeb appliance will use when it logs and/or sends an alert email about a violation of each rule.<span class="li-normal"> type:string 
                    maxLength:63</span></li>   
              <li><span class="li-head"> spam_block_period</span> The number of seconds that you want to block subsequent requests from the client after the FortiWeb appliance detects that the client has violated the rule. Only available when 'spam_action' is 'block-period'.<span class="li-normal"> type:string 
                    maxLength:63</span></li>  
              <li><span class="li-head"> trojan_status</span> Enable or disable the trojan Bot check for this rule. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li> 
              <li><span class="li-head"> trojan_action</span> Select the action that FortiWeb takes when it detects a trojan Bot violation of the rule. <span class="li-normal"> type:string choice:
                      bypass,
                      alert
                      alert_deny,
                      redirect,
                      deny_no_log,
                      block-period,
                      send_http_response</span></li> 
              <li><span class="li-head"> trojan_severity</span> Select which severity level the FortiWeb appliance will use when it logs a violation of the rule. <span class="li-normal"> type:string choice:
                      Low,
                      Medium,
                      High,
                      Info</span></li>     
              <li><span class="li-head"> trojan_threat_weight</span> Set the weight for the threat. <span class="li-normal"> type:string choice:
                      informational,
                      low,
                      moderate,
                      substantial,
                      severe,
                      critical</span></li>  
              <li><span class="li-head"> trojan_trigger </span> Select which trigger, if any, that the FortiWeb appliance will use when it logs and/or sends an alert email about a violation of each rule.<span class="li-normal"> type:string 
                    maxLength:63</span></li>   
              <li><span class="li-head"> trojan_block_period</span> The number of seconds that you want to block subsequent requests from the client after the FortiWeb appliance detects that the client has violated the rule. Only available when 'trojan_action' is 'block-period'.<span class="li-normal"> type:string 
                    maxLength:63</span></li>
              <li><span class="li-head"> scanner_status</span> Enable or disable the scanner Bot check for this rule. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li> 
              <li><span class="li-head"> scanner_action</span> Select the action that FortiWeb takes when it detects a scanner Bot violation of the rule. <span class="li-normal"> type:string choice:
                      bypass,
                      alert
                      alert_deny,
                      redirect,
                      deny_no_log,
                      block-period,
                      send_http_response</span></li> 
              <li><span class="li-head"> scanner_severity</span> Select which severity level the FortiWeb appliance will use when it logs a violation of the rule. <span class="li-normal"> type:string choice:
                      Low,
                      Medium,
                      High,
                      Info</span></li>     
              <li><span class="li-head"> scanner_threat_weight</span> Set the weight for the threat. <span class="li-normal"> type:string choice:
                      informational,
                      low,
                      moderate,
                      substantial,
                      severe,
                      critical</span></li>  
              <li><span class="li-head"> scanner_trigger </span> Select which trigger, if any, that the FortiWeb appliance will use when it logs and/or sends an alert email about a violation of each rule.<span class="li-normal"> type:string 
                    maxLength:63</span></li>   
              <li><span class="li-head"> scanner_block_period</span> The number of seconds that you want to block subsequent requests from the client after the FortiWeb appliance detects that the client has violated the rule. Only available when 'scanner_action' is 'block-period'.<span class="li-normal"> type:string 
                    maxLength:63</span></li> 
              <li><span class="li-head"> crawler_status</span> Enable or disable the crawler Bot check for this rule. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li> 
              <li><span class="li-head"> crawler_action</span> Select the action that FortiWeb takes when it detects a crawler Bot violation of the rule. <span class="li-normal"> type:string choice:
                      bypass,
                      alert
                      alert_deny,
                      redirect,
                      deny_no_log,
                      block-period,
                      send_http_response</span></li> 
              <li><span class="li-head"> crawler_severity</span> Select which severity level the FortiWeb appliance will use when it logs a violation of the rule. <span class="li-normal"> type:string choice:
                      Low,
                      Medium,
                      High,
                      Info</span></li>     
              <li><span class="li-head"> crawler_threat_weight</span> Set the weight for the threat. <span class="li-normal"> type:string choice:
                      informational,
                      low,
                      moderate,
                      substantial,
                      severe,
                      critical</span></li>  
              <li><span class="li-head"> crawler_trigger </span> Select which trigger, if any, that the FortiWeb appliance will use when it logs and/or sends an alert email about a violation of each rule.<span class="li-normal"> type:string 
                    maxLength:63</span></li>   
              <li><span class="li-head"> crawler_block_period</span> The number of seconds that you want to block subsequent requests from the client after the FortiWeb appliance detects that the client has violated the rule. Only available when 'crawler_action' is 'block-period'.<span class="li-normal"> type:string 
                    maxLength:63</span></li> 
              <li><span class="li-head"> known_engines_status</span> Enable or disable the known_engines Bot check for this rule. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li> 
              <li><span class="li-head"> known_engines_action</span> Select the action that FortiWeb takes when it detects a known_engines Bot violation of the rule. <span class="li-normal"> type:string choice:
                      bypass,
                      alert
                      alert_deny,
                      redirect,
                      deny_no_log,
                      block-period,
                      send_http_response</span></li> 
              <li><span class="li-head"> known_engines_severity</span> Select which severity level the FortiWeb appliance will use when it logs a violation of the rule. <span class="li-normal"> type:string choice:
                      Low,
                      Medium,
                      High,
                      Info</span></li>     
              <li><span class="li-head"> known_engines_threat_weight</span> Set the weight for the threat. <span class="li-normal"> type:string choice:
                      informational,
                      low,
                      moderate,
                      substantial,
                      severe,
                      critical</span></li>  
              <li><span class="li-head"> known_engines_trigger </span> Select which trigger, if any, that the FortiWeb appliance will use when it logs and/or sends an alert email about a violation of each rule.<span class="li-normal"> type:string 
                    maxLength:63</span></li>   
              <li><span class="li-head"> known_engines_block_period</span> The number of seconds that you want to block subsequent requests from the client after the FortiWeb appliance detects that the client has violated the rule. Only available when 'known_engines_action' is 'block-period'.<span class="li-normal"> type:string 
                    maxLength:63</span></li>  
              <li><span class="li-head"> marketing_status</span> Enable or disable the marketing Bot check for this rule. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li> 
              <li><span class="li-head"> marketing_action</span> Select the action that FortiWeb takes when it detects a marketing Bot violation of the rule. <span class="li-normal"> type:string choice:
                      bypass,
                      alert
                      alert_deny,
                      redirect,
                      deny_no_log,
                      block-period,
                      send_http_response</span></li> 
              <li><span class="li-head"> marketing_severity</span> Select which severity level the FortiWeb appliance will use when it logs a violation of the rule. <span class="li-normal"> type:string choice:
                      Low,
                      Medium,
                      High,
                      Info</span></li>     
              <li><span class="li-head"> marketing_threat_weight</span> Set the weight for the threat. <span class="li-normal"> type:string choice:
                      informational,
                      low,
                      moderate,
                      substantial,
                      severe,
                      critical</span></li>  
              <li><span class="li-head"> marketing_trigger </span> Select which trigger, if any, that the FortiWeb appliance will use when it logs and/or sends an alert email about a violation of each rule.<span class="li-normal"> type:string 
                    maxLength:63</span></li>   
              <li><span class="li-head"> marketing_block_period</span> The number of seconds that you want to block subsequent requests from the client after the FortiWeb appliance detects that the client has violated the rule. Only available when 'marketing_action' is 'block-period'.<span class="li-normal"> type:string 
                    maxLength:63</span></li>  
              <li><span class="li-head"> page_preview_status</span> Enable or disable the page_preview Bot check for this rule. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li> 
              <li><span class="li-head"> page_preview_action</span> Select the action that FortiWeb takes when it detects a page_preview Bot violation of the rule. <span class="li-normal"> type:string choice:
                      bypass,
                      alert
                      alert_deny,
                      redirect,
                      deny_no_log,
                      block-period,
                      send_http_response</span></li> 
              <li><span class="li-head"> page_preview_severity</span> Select which severity level the FortiWeb appliance will use when it logs a violation of the rule. <span class="li-normal"> type:string choice:
                      Low,
                      Medium,
                      High,
                      Info</span></li>     
              <li><span class="li-head"> page_preview_threat_weight</span> Set the weight for the threat. <span class="li-normal"> type:string choice:
                      informational,
                      low,
                      moderate,
                      substantial,
                      severe,
                      critical</span></li>  
              <li><span class="li-head"> page_preview_trigger </span> Select which trigger, if any, that the FortiWeb appliance will use when it logs and/or sends an alert email about a violation of each rule.<span class="li-normal"> type:string 
                    maxLength:63</span></li>   
              <li><span class="li-head"> page_preview_block_period</span> The number of seconds that you want to block subsequent requests from the client after the FortiWeb appliance detects that the client has violated the rule. Only available when 'page_preview_action' is 'block-period'.<span class="li-normal"> type:string 
                    maxLength:63</span></li>  
              <li><span class="li-head"> feed_fetcher_status</span> Enable or disable the feed_fetcher Bot check for this rule. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li> 
              <li><span class="li-head"> feed_fetcher_action</span> Select the action that FortiWeb takes when it detects a feed_fetcher Bot violation of the rule. <span class="li-normal"> type:string choice:
                      bypass,
                      alert
                      alert_deny,
                      redirect,
                      deny_no_log,
                      block-period,
                      send_http_response</span></li> 
              <li><span class="li-head"> feed_fetcher_severity</span> Select which severity level the FortiWeb appliance will use when it logs a violation of the rule. <span class="li-normal"> type:string choice:
                      Low,
                      Medium,
                      High,
                      Info</span></li>     
              <li><span class="li-head"> feed_fetcher_threat_weight</span> Set the weight for the threat. <span class="li-normal"> type:string choice:
                      informational,
                      low,
                      moderate,
                      substantial,
                      severe,
                      critical</span></li>  
              <li><span class="li-head"> feed_fetcher_trigger </span> Select which trigger, if any, that the FortiWeb appliance will use when it logs and/or sends an alert email about a violation of each rule.<span class="li-normal"> type:string 
                    maxLength:63</span></li>   
              <li><span class="li-head"> feed_fetcher_block_period</span> The number of seconds that you want to block subsequent requests from the client after the FortiWeb appliance detects that the client has violated the rule. Only available when 'feed_fetcher_action' is 'block-period'.<span class="li-normal"> type:string 
                    maxLength:63</span></li>  
              <li><span class="li-head"> likely_good_bot_status</span> Enable or disable the likely_good_bot Bot check for this rule. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li> 
              <li><span class="li-head"> likely_good_bot_action</span> Select the action that FortiWeb takes when it detects a likely_good_bot Bot violation of the rule. <span class="li-normal"> type:string choice:
                      bypass,
                      alert
                      alert_deny,
                      redirect,
                      deny_no_log,
                      block-period,
                      send_http_response</span></li> 
              <li><span class="li-head"> likely_good_bot_severity</span> Select which severity level the FortiWeb appliance will use when it logs a violation of the rule. <span class="li-normal"> type:string choice:
                      Low,
                      Medium,
                      High,
                      Info</span></li>     
              <li><span class="li-head"> likely_good_bot_threat_weight</span> Set the weight for the threat. <span class="li-normal"> type:string choice:
                      informational,
                      low,
                      moderate,
                      substantial,
                      severe,
                      critical</span></li>  
              <li><span class="li-head"> likely_good_bot_trigger </span> Select which trigger, if any, that the FortiWeb appliance will use when it logs and/or sends an alert email about a violation of each rule.<span class="li-normal"> type:string 
                    maxLength:63</span></li>   
              <li><span class="li-head"> likely_good_bot_block_period</span> The number of seconds that you want to block subsequent requests from the client after the FortiWeb appliance detects that the client has violated the rule. Only available when 'likely_good_bot_action' is 'block-period'.<span class="li-normal"> type:string 
                    maxLength:63</span></li>               
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
    - name: add a known bot profile
      fwebos_waf_known_bots:
        action: add 
        name: Bot1
        dos_status: enable
        dos_action: alert_deny
        dos_block_period: 600
        dos_severity: High
        dos_threat_weight: critical
        dos_trigger: 


    - name: edit a known bot profile
      fwebos_waf_known_bots:
        action: edit 
        name: Bot1
        feed_fetcher_status: enable
        feed_fetcher_action: redirect
        feed_fetcher_severity: Info
        feed_fetcher_threat_weight: moderate #substantial 

    - name: get a known bot profile
      fwebos_waf_known_bots:
        action: get
        name: Bot1

    - name: delete a known bot profile
      fwebos_waf_known_bots:
        action: delete
        name: Bot1



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