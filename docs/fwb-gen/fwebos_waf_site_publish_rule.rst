:source: fwebos_waf_site_publish_rule.py

:orphan:

.. fwebos_waf_site_publish_rule.py:

fwebos_waf_site_publish_rule.py -- Config FortiWeb Published Site Policy
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.1

.. contents::
   :local:
   :depth: 1


Synopsis
--------
Config FortiWeb Published Site Policy


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
 <td>fwebos_waf_site_publish_rule.py</td>
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
              <li><span class="li-head"> published_site </span> Name of Published Site.<span class="li-normal"> type:string 
                    maxLength:255</span></li>  
              <li><span class="li-head"> published_site_type </span> Published Site Type. Simple string ('plain') or regular expression ('regular'). <span class="li-normal"> type:string choice:
                      plain,
                      regular</span></li>
              <li><span class="li-head"> path </span> Path of Published Site.<span class="li-normal"> type:string 
                    maxLength:2071</span></li>
              <li><span class="li-head"> account_lockout </span> Enable or disable Account Lockout. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> cookieless </span> Enable or disable cookieless. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> max_login_failures </span> Max Login Failures. Only available when 'account_lockout' is enabled.<span class="li-normal"> type:integer
                    maximum:30
                    minimum:1</span></li>
              <li><span class="li-head"> within </span> The number of minutes allowing max login login failures. Only available when 'account_lockout' is enabled.<span class="li-normal"> type:integer
                    maximum:30
                    minimum:1</span></li>
              <li><span class="li-head"> account_block_period </span> Account Block Period. Only available when 'account_lockout' is enabled.<span class="li-normal"> type:integer
                    maximum:3600
                    minimum:1</span></li>
              <li><span class="li-head"> limit_users </span> Enable or disable Limit Concurrent Users Per Account. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> maximum_users </span> Maximum Concurrent Users. Only available when 'limit_users' is enabled.<span class="li-normal"> type:integer
                    maximum:128
                    minimum:1</span></li>
              <li><span class="li-head"> session_idle_timeout </span>Session Idle Timeout (Unit: minute). Only available when 'limit_users' is enabled.<span class="li-normal"> type:integer
                    maximum:1440
                    minimum:1</span></li>
              <li><span class="li-head"> credential_stuffing_online_query </span> Enable or disable Credential Stuffing Defense. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> credential_stuffing_protection </span> Enable or disable Credential Stuffing Online Check. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> match_type </span> Select Match type.<span class="li-normal"> type:string choice:
                      any,
                      all</span></li>       
              <li><span class="li-head"> security_action </span> Choose the action FortiWeb takes when a rule is violated.<span class="li-normal"> type:string choice:
                      alert,
                      deny_no_log,
                      alert_deny,
                      block-period,
                      client-id-block-period,</span></li>
              <li><span class="li-head"> block_period </span> Block Period. Only available when 'security_action' is 'block-period'.<span class="li-normal"> type:integer
                    maximum:30
                    minimum:1</span></li>
              <li><span class="li-head"> security </span> Select security level.<span class="li-normal"> type:string choice:
                      Info,
                      Low,
                      Medium,
                      High</span></li>
              <li><span class="li-head"> trigger </span> Select the trigger policy, if any, that FortiWeb carries out when it logs and/or sends an alert email about a violation.<span class="li-normal"> type:string 
                    maxLength:255 </span></li> 
              <li><span class="li-head"> client_auth_method </span> Client Authentication Method. Only available when 'cookieless' is enabled.<span class="li-normal"> type:string choice:
                      html-form-auth,
                      http-auth,
                      client-cert-auth,
                      saml-auth,
                      oauth-auth,
                      ntlm-auth</span></li>
              <li><span class="li-head"> cookie_timeout </span> Authentication Cookie Timeout. <span class="li-normal">  type:integer
                    maximum:216000
                    minimum:1</span></li>
              <li><span class="li-head"> redirect_url </span> Redirect URL After Authentication (Optional).<span class="li-normal"> type:string 
                    maxLength:255 </span></li> 
              <li><span class="li-head"> append_custom_header </span> Append Custom Header. <span class="li-normal"> type:string choice:
                      enable,
              <li><span class="li-head"> sso_support </span> SSO Support. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li> 
              <li><span class="li-head"> sso_domain </span> SSO Domain. Only available when 'sso_support' is enabled. <span class="li-normal"> type:string 
                    maxLength:255 </span></li> 
              <li><span class="li-head"> auth_server_pool</span> Authentication Server Pool. Only available when 'client_auth_method' is 'html-form-auth'. <span class="li-normal"> type:string 
                    maxLength:255 </span></li> 
              <li><span class="li-head"> auth_delegation </span> Authentication Delegation.<span class="li-normal"> type:string choice:
                      no-delegation,
                      kerberos,
                      ntlm,
                      form-based-delegation,
                      kerberos-constrained-delegation,
                      radius-constrained-delegation</span></li>
              <li><span class="li-head"> form_based_delegation</span> Form based delegation. Only available when 'client_auth_method' is 'html-form-auth' and 'auth_delegation' is 'form-based-delegation'. <span class="li-normal"> type:string 
                    maxLength:255 </span></li> 
              <li><span class="li-head"> ntlm_server</span> NTLM Server. Only available when 'client_auth_method' is 'ntlm-auth'. <span class="li-normal"> type:string 
                    maxLength:255 </span></li> 
              <li><span class="li-head"> alert_type </span> Select Alert Type.<span class="li-normal"> type:string choice:
                      fail (Failed Only),
                      success (successful Only),
                      none,
                      all</span></li>
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
    - name: add a site_publish rule
      fwebos_waf_site_publish_rule:
        action: add
        name: spr_test
        published_site: testsite.com
        published_site_type: plain
        status: enable
        cookieless: disable
        cookieless_cache: 3600
        client_auth_method: html-form-auth
        auth_server_pool: asp1
        ntlm_server: 
        auth_delegation: no-delegation
        form_based_delegation: 
        sso_support: enable
        sso_domain: domin1
        prefix_support: enable
        prefix_domain: prefix1
        path: /path1/path2/*
        alert_type: fail
        logoff_path_type: plain
        Published_Server_Logoff_Path: /abc/efg
        redirect_url: 
        cookie_timeout: 222
        csrf_enhancement: enable
        append_custom_header: enable
        pass_failed_auth: enable
        cache_tgs_ticket: enable

    - name: get a site_publish rule
      fwebos_waf_site_publish_rule:
        action: get
        name: spr_test


    - name: edit a site_publish rule
      fwebos_waf_site_publish_rule:
        action: edit
        name: spr_test
        published_site: testsite1.com
        published_site_type: plain
        status: enable
        client_auth_method: http-auth

    - name: delete a site_publish rule
      fwebos_waf_site_publish_rule:
        action: delete
        name: spr_test

    - name: delete a site_publish rule again
      fwebos_waf_site_publish_rule:
        action: delete
        name: spr_test


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