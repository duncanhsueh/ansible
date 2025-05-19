:source: fwebos_content_routing_policy_match_list.py

:orphan:

.. fwebos_content_routing_policy_match_list.py:

fwebos_content_routing_policy_match_list.py -- Config FortiWeb Content Routing Policy Match Details.
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.1

.. contents::
   :local:
   :depth: 1


Synopsis
--------
Config FortiWeb Content Routing Policy Match Details


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
 <td>fwebos_content_routing_policy_match_list.py</td>
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
              <li><span class="li-head"> policy_name </span> name of content routing policy <span class="li-normal"> type:string
                    maxLength:63</span></li>
              <li><span class="li-head"> match_object </span> Match against the input types in the HTTP Request Header.<span class="li-normal"> type:string choice:
                      http-host,
                      http-request,
                      url-parameter,
                      http-referer,
                      http-cookie,
                      http-header,
                      source-ip,
                      x509-certificate-Subject,
                      x509-certificate-Extension,
                      https-sni,
                      geo-ip</span></li>
              <li><span class="li-head"> match_condition </span> How the values in match object interact with the match string. This field is used when 'match_object' is 'http-host', 'http-request', 'http-referer', 'source-ip', 'x509-certificate-Subject', 'x509-certificate-Extension', or 'https-sni'.<span class="li-normal"> type:string choice:
                      match-begin (The match object ends with the match string),
                      match-sub (The match object contains the match string),
                      match-end (The match object ends with the match string),
                      match-domain (The match object contains the match string between dots),
                      equal (The match object is equal to the match string),
                      match-reg (The match object matches the specified regular expression)</span></li>
              <li><span class="li-head"> match_expression </span> The content of match string. <span class="li-normal"> type:string
                    maxLength:2071</span></li>
              <li><span class="li-head"> concatenate </span> Choose the relationship with the previous rule. The AND relationship has higher precedence than OR in the match sequence. <span class="li-normal"> type:string choice:
                      enable,
                      disable</span></li>
              <li><span class="li-head"> parameter_name_match_condition </span> Parameter Name match type. Use this field when 'match_object' is 'url-parameter', 'http-cookie', or 'http-header'. <span class="li-normal"> type:string choice:
                      match-begin (The match object ends with the match string),
                      match-sub (The match object contains the match string),
                      match-end (The match object ends with the match string),
                      equal (The match object is equal to the match string),
                      match-reg (The match object matches the specified regular expression)</span></li>
              <li><span class="li-head"> parameter_name_match_condition_val </span> Parameter Name match string. <span class="li-normal"> type:string
                    maxLength:2071</span></li>    
              <li><span class="li-head"> parameter_value_match_condition </span> Parameter Value match type. <span class="li-normal"> type:string choice:
                      match-begin (The match object ends with the match string),
                      match-sub (The match object contains the match string),
                      match-end (The match object ends with the match string),
                      equal (The match object is equal to the match string),
                      match-reg (The match object matches the specified regular expression)</span></li>
              <li><span class="li-head"> parameter_value_match_condition_val </span> Parameter Value match string. <span class="li-normal"> type:string
                    maxLength:2071</span></li>    
              <li><span class="li-head"> x509_subject_name </span>X509 Field Name. <span class="li-normal"> type:string choice:
                      E,
                      CN,
                      OU,
                      O,
                      L,
                      ST,
                      C</span></li>
              <li><span class="li-head"> country_list </span> Country list when 'match_object' is 'geo-ip'<span class="li-normal"> type:list</span></li>
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
     - name: Create a url-parameter
       fwebos_content_routing_policy_match_list:
        action: add
        policy_name: crp1
        match_object: url-parameter
        parameter_name_match_condition: equal
        parameter_value_match_condition: equal
        parameter_name_match_condition_val: YYYY
        parameter_value_match_condition_val: ZZZZ
        concatenate: and

     - name: Create a http post
       fwebos_content_routing_policy_match_list:
        action: add
        policy_name: crp1
        match_object: http-post
        match_condition: equal
        match_expression: pattern
        concatenate: and

     - name: Create a x509-certificate-Subject
       fwebos_content_routing_policy_match_list:
        action: add
        policy_name: crp1
        match_object: x509-certificate-Subject
        match_condition: equal
        match_expression: 888
        x509_subject_name: CN
        concatenate: and

     - name: Create a geo-ip
       fwebos_content_routing_policy_match_list:
        action: add
        policy_name: crp1
        match_object: geo-ip
        country_list:
         - Angola
         - Bahrain
        concatenate: and

     - name: edit a http post
       fwebos_content_routing_policy_match_list:
        action: edit
        policy_name: crp1 
        id: 1
        match_expression: new_expression 

     - name: edit a url-parameter
       fwebos_content_routing_policy_match_list:
        action: edit
        policy_name: crp1
        match_object: url-parameter
        id: 2
        parameter_name_match_condition: match-reg
        parameter_value_match_condition: match-reg
        parameter_name_match_condition_val: xxxx1
        parameter_value_match_condition_val: yyyy1
        concatenate: or

     - name: get
       fwebos_content_routing_policy_match_list:
        action: get
        policy_name: crp1    
        id: 1

     - name: delete
       fwebos_content_routing_policy_match_list:
        action: delete
        policy_name: crp1    
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

- Jie Li
- Brad Zhang

.. hint::
	If you notice any issues in this documentation, you can create a pull request to improve it.