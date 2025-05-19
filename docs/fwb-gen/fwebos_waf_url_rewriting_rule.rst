:source: fwebos_waf_url_rewriting_rule.py

:orphan:

.. fwebos_waf_url_rewriting_rule.py:

fwebos_waf_url_rewriting_rule.py -- Configure FortiWeb URL Rewriting Rules
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.1

.. contents::
   :local:
   :depth: 1


Synopsis
--------
Configure FortiWeb URL Rewriting Rules


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
 <td>fwebos_waf_url_rewriting_rule.py</td>
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
              <li><span class="li-head"> name </span> The name of  URL Rewriting Rule.<span class="li-normal"> type:string
                    maxLength:63</span></li>
              <li><span class="li-head"> action_type </span> Action Type. <span class="li-normal"> type:string choice:
                      redirect,
                      403-forbidden,
                      http-header-rewrite,
                      http-response-body-rewrite,
                      http-response-header-rewrite,
                      redirect-301,
                      http-request-body-rewrite</span></li>
              <li><span class="li-head"> status_code_status </span> Status of Replacement Status Code. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> status_code </span> Number of Replacement Status Code.<span class="li-normal"> type:integer
                      maximum:599
                      minimum:100</span></li>   
              <li><span class="li-head"> location_status </span> Status of Replacement String.<span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> location_replace </span> Value of Replacement String.<span class="li-normal"> type:string
                    maxLength:1023 </span></li>
              <li><span class="li-head"> body_replace </span> The string that will replace content in the body of HTTP responses..<span class="li-normal"> type:string
                    maxLength:255 </span></li>
              <li><span class="li-head"> response_replace_existing_headers </span>Only available when 'action_type' is 'http-response-header-rewrite'. Enable or Disable Replace Existing Headers which overwrites the value of the existing header with your specified header value.  On the other hand, if this option is disabled, the system will insert the header directly without checking if there is an existing header with the same header name.<span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> response_insert_list </span>Only available when 'action_type' is 'http-response-header-rewrite'. Value of the existing header to be replaced. And the specified header value to be placed.<span class="li-normal"> type:list</span></li>
              <li><span class="li-head"> request_replace_existing_headers </span>Only available when 'action_type' is 'http-header-rewrite'. Enable or Disable Replace Existing Headers which overwrites the value of the existing header with your specified header value.  On the other hand, if this option is disabled, the system will insert the header directly without checking if there is an existing header with the same header name.<span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> insert_list </span>Only available when 'action_type' is 'http-header-rewrite'. Value of the existing header to be replaced. And the specified header value to be placed. Only when request_replace_existing_headers is enabled.<span class="li-normal"> type:list</span></li>
              <li><span class="li-head"> response_remove_duplicate_headers </span>Only available when 'action_type' is 'http-response-header-rewrite'. Enabling this option will remove all multiple items that match your specified header name. However, if this option is disabled, only the first matching item will be removed.<span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> response_removal_list </span>Only available when 'action_type' is 'http-response-header-rewrite'. The name of the header field that you want to remove. Up to 10 header names can be added in the list..<span class="li-normal"> type:list</span></li>
              <li><span class="li-head"> request_remove_duplicate_headers </span> Only available when 'action_type' is 'http-header-rewrite'. Enabling this option will remove all multiple items that match your specified header name. However, if this option is disabled, only the first matching item will be removed.<span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> removal_list </span>Only available when 'action_type' is 'http-header-rewrite'. The name of the header field that you want to remove. Up to 10 header names can be added in the list..<span class="li-normal"> type:list</span></li>
              <li><span class="li-head"> request_replace_existing_cookies</span> Only available when 'action_type' is 'http-header-rewrite'. If there is already a cookie with the same name existing in the request, enabling this option will overwrite the value of the existing cookie with your specified cookie value.<span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> cookie_insert_list </span>Only available when 'action_type' is 'http-header-rewrite'. The list containing the name of the cookie that you want to insert to a request, and the value of the cookie that you want to insert.. <span class="li-normal"> type:list</span></li>
              <li><span class="li-head"> request_remove_duplicate_cookies</span> Only available when 'action_type' is 'http-header-rewrite'. If the system finds multiple items that match your specified cookie name, enabling this option will remove all of them. However, if this option is disabled, only the first matching item will be removed.<span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> cookie_removal_list</span>Only available when 'action_type' is 'http-header-rewrite'. The list containing the name of the cookie that you want to remove. Up to 10 header names can be added in the list. <span class="li-normal"> type:list</span></li>
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
    - name: add a URL rewriting policy
      fwebos_waf_url_rewriting_rule:
        action: add 
        name: test1
        action_type: http-response-header-rewrite
        host_status: disable
        url_status: disable
        referer_status: disable
        location_replace:
        location_status: disable
        http_method_status: disable
        http_method: get
        status_code_status: disable
        status_code: 404
        request_replace_existing_headers: disable
        response_replace_existing_headers: disable
        request_remove_duplicate_headers: enable
        response_remove_duplicate_headers: enable
        request_remove_duplicate_cookies: disable
        request_replace_existing_cookies: disable
        response_removal_list: 
         - { "response-removal-header-name": "to-remove5"}
         - { "response-removal-header-name": "to-remove4"}
        response_insert_list:
         - { "response-header-name": "to-insert", "response-header-value": "inserted" }
        flag_operation: 0

    - name: get a URL rewriting policy
      fwebos_waf_url_rewriting_rule:
        action: get 
        name: test1

    - name: add a URL rewriting policy
      fwebos_waf_url_rewriting_rule:
        action: add 
        name: test2
        action_type: http-header-rewrite
        host_status: enable
        host_use_pserver: enable
        host: FORTIWEB_PSERVER
        url_status: enable
        url: www.url1.com
        referer_status: enable
        referer_use_pserver: enable
        referer: http://FORTIWEB_PSERVER/
        location_replace:
        location_status: disable
        http_method_status: enable
        http_method: get
        status_code_status: enable
        status_code: 404
        request_replace_existing_headers: enable
        response_replace_existing_headers: disable
        request_remove_duplicate_headers: enable
        response_remove_duplicate_headers: enable
        request_remove_duplicate_cookies: enable
        request_replace_existing_cookies: enable


    - name: edit a URL rewriting policy
      fwebos_waf_url_rewriting_rule:
        action: edit 
        name: test1
        action_type: http-response-header-rewrite
        request_remove_duplicate_headers: enable
        response_remove_duplicate_headers: enable
        response_removal_list: 
         - { "response-removal-header-name": "r1"}
         - { "response-removal-header-name": "r2"}
         - { "response-removal-header-name": "r3"}
         - { "response-removal-header-name": "r4"}         
        response_insert_list:
         - { "response-header-name": "i1", "response-header-value": "iv1" }
         - { "response-header-name": "i2", "response-header-value": "iv2" }
         - { "response-header-name": "i3", "response-header-value": "iv3" }               

    - name: edit a URL rewriting policy
      fwebos_waf_url_rewriting_rule:
        action: edit 
        name: test2
        action_type: http-request-body-rewrite
        body_replace: replacement301

    - name: delete a URL rewriting policy
      fwebos_waf_url_rewriting_rule:
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

- Jie Li
- Brad Zhang

.. hint::
	If you notice any issues in this documentation, you can create a pull request to improve it.