:source: fwebos_waf_url_rewriting_rule_condition.py

:orphan:

.. fwebos_waf_url_rewriting_rule_condition.py:

fwebos_waf_url_rewriting_rule_condition.py -- Config FortiWeb URL Rewriting Rule Condition
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.1

.. contents::
   :local:
   :depth: 1


Synopsis
--------
Config FortiWeb URL Rewriting Rule Condition


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
 <td>fwebos_waf_url_rewriting_rule_condition.py</td>
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
              <li><span class="li-head"> name </span> The name of rewriting rule.<span class="li-normal"> type:string 
                    maxLength:63</span></li>  
              <li><span class="li-head"> id </span> The index of rewriting rule condition.<span class="li-normal"> type:integer</span></li>     
              <li><span class="li-head"> object </span> Select which part of the HTTP request will be tested for a match.<span class="li-normal"> type:string choice:
                      http-host,
                      http-url,
                      http-location</span></li>  
              <li><span class="li-head"> reg_exp </span> A regular Expression that defines either all matching or all non-matching objects..<span class="li-normal"> type:string 
                    maxLength:255</span></li>   
              <li><span class="li-head"> protocol_filter </span> Protocol Filter.<span class="li-normal"> type:string choice:
                      enable,
                      disable,</span></li>  
              <li><span class="li-head"> http_protocol </span> Select which protocol will match this condition, either HTTP or HTTPS..<span class="li-normal"> type:string choice:
                      http,
                      https,</span></li> 
              <li><span class="li-head"> reverse_match </span> Indicate how to use Regular Expression when determining whether or not this URL rewriting condition is met.<span class="li-normal"> type:string choice:
                      "yes" (Object does not match the regular expression),
                      "no" (Object matches the regular expressionn)</span></li>                                           
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
    - name: add a URL rewriting rule condition
      fwebos_waf_url_rewriting_rule_condition:
       action: add 
       name: aa2
       object: http-refer
       is_referer_essential: "yes"
       reg_exp: tttttt
       reverse_match: "no"
       content_type_filter: enable
       
    - name: get a URL rewriting rule condition
      fwebos_waf_url_rewriting_rule_condition:
       action: get 
       name: aa2
       id: 1

    - name: edit a URL rewriting rule condition
      fwebos_waf_url_rewriting_rule_condition:
       action: edit 
       name: aa2
       id: 3
       object: http-host
       protocol_filter: enable
       http_protocol: https
       reg_exp: abcd

    - name: delete a URL rewriting rule condition
      fwebos_waf_url_rewriting_rule_condition:
       action: delete 
       name: aa2
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