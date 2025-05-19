:source: fwebos_waf_http_header_security_policy_rule.py

:orphan:

.. fwebos_waf_http_header_security_policy_rule.py:

fwebos_waf_http_header_security_policy_rule.py -- Config FortiWeb HTTP Header Security Policy Rules
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.1

.. contents::
   :local:
   :depth: 1


Synopsis
--------
Config FortiWeb HTTP Header Security Policy Rules


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
 <td>fwebos_waf_http_header_security_policy.py</td>
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
              <li><span class="li-head"> request_status </span> Click to enable or disable request filter. It is also named URL filter. Enable it so that responses to the request will be processed with the security headers only if the URL of a request matches the specified Request URL. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>       
              <li><span class="li-head"> request_type </span> Select 'plain' (Simple String) to match the URL of requests with a literal URL specified in Request URL. Select 'regular' (Regular Expression) to match the URL of requests with a regular expression specified in Request URL. <span class="li-normal"> type:string choice:
                      plain,
                      regular</span></li> 
              <li><span class="li-head"> request_file </span> The Request URL. <span class="li-normal"> type:string 
                    maxLength:255</span></li>
              <li><span class="li-head"> secure_header_type </span> FortiWeb security headers Types. <span class="li-normal"> type:string choice:
                      x-xss-protection,
                      x-frame-options,
                      x-content-type-options,
                      content-security-policy,
                      feature-policy,
                      permissions-policy,
                      referrer-policy</span></li>    
              <li><span class="li-head"> exception </span> The name of HTTP Header Security Policy Exception. <span class="li-normal"> type:string 
                    maxLength:63</span></li>    
              <li><span class="li-head"> referrer_policy_value </span> The referrer policy options. Only available when 'secure_header_type' is 'referrer-policy'.<span class="li-normal">type:string choice:
                      no-referrer,
                      no-referrer-when-downgrade,
                      same-origin,
                      origin,
                      strict-origin,
                      origin-when-cross-origin,
                      strict-origin-when-cross-origin,
                      unsafe-url</span></li>     
              <li><span class="li-head"> protection_mode</span> Used to direct the browers to stop loading pages when reflected XSS attackes are detected. <span class="li-normal"> type:string choice:
                      deny  (when 'secure_header_type' is 'x-frame-options'),
                      sameorigin  (when 'secure_header_type' is 'x-frame-options'),
                      allow-from (when 'secure_header_type' is 'x-frame-options'),
                      nosniff (when 'secure_header_type' is 'x-content-type-options'),
                      sanitizing-mode (when 'secure_header_type' is 'x-xss-protection'),
                      block-mode (when 'secure_header_type' is 'x-xss-protection')</span></li> 
              <li><span class="li-head"> header_value </span> Used to reduce XSS risk and data injection attacks on browers. <span class="li-normal"> type:string 
                    maxLength:2047</span></li>          
              <li><span class="li-head"> allow_from_source </span> Allowed From URI. Only available when 'protection_mode' is 'allow-from'. <span class="li-normal"> type:string 
                    maxLength:255</span></li>                                          
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
    - name: add a New Secure Header Rule
      fwebos_waf_http_header_security_policy_rule:
       action: add 
       name: HP
       request_status: disable
       request_type: plain
       protection_mode: sanitizing-mode
       secure_header_type: x-xss-protection

    - name: edit a Secure Header Rule
      fwebos_waf_http_header_security_policy_rule:
       action: edit 
       name: HP
       id: 1
       secure_header_type: x-frame-options
       protection_mode: allow-from
       allow_from_source: "http://www.google.com"
       exception: hse1

    - name: edit a Secure Header Rule
      fwebos_waf_http_header_security_policy_rule:
       action: edit 
       name: HP
       id: 1
       secure_header_type: content-security-policy
       header_value: "http://www.amazon.ca"
       exception: hse1

    - name: edit a Secure Header Rule
      fwebos_waf_http_header_security_policy_rule:
       action: edit 
       name: HP
       id: 1
       secure_header_type: referrer-policy
       referrer_policy_value: no-referrer
       exception: ""

    - name: get a Secure Header Rule
      fwebos_waf_http_header_security_policy_rule:
       action: get 
       name: HP
       id: 1

    - name: delete a Secure Header Rule
      fwebos_waf_http_header_security_policy_rule:
       action: delete 
       name: HP
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