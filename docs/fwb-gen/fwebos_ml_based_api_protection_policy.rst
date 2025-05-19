:source: fwebos_ml_based_api_protection_policy.py

:orphan:

.. fwebos_ml_based_api_protection_policy.py:

fwebos_ml_based_api_protection_policy.py -- Config FortiWeb ML Based API Protection Policy
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.1

.. contents::
   :local:
   :depth: 1


Synopsis
--------
Config FortiWeb ML Based API Protection Policy


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
 <td>fwebos_ml_based_api_protection_policy.py</td>
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
              <li><span class="li-head"> policy_id </span> The numerical policy ID of the Server Policy. It is the same one as used in CLI.<span class="li-normal"> type:string 
                    maxLength:63</span></li>
              <li><span class="li-head"> rule_domain </span> List of Domains.<span class="li-normal"> type:list </span></li>
              <li><span class="li-head"> rule_ip </span> List of IPs.<span class="li-normal"> type:list </span></li>
              <li><span class="li-head"> action_mlapi </span> Schema Protection action.<span class="li-normal"> type:string choice:
                      alert,
                      alert_deny,
                      standby,
                      block-period</span></li>     
              <li><span class="li-head"> block_period_mlapi </span> Block Period for Schema Protection.<span class="li-normal"> type:string
                    maxLength:255</span></li>   
              <li><span class="li-head"> severity_mlapi </span> Severity for Schema Protection.<span class="li-normal"> type:string choice:
                      Info,
                      Low,
                      Medium,
                      High</span></li>
              <li><span class="li-head"> trigger_mlapi </span>Name of the Trigger Policy for Schema Protection.<span class="li-normal"> type:string
                    maxLength:255</span></li> 
              <li><span class="li-head"> action_anomaly </span>Threat Detection action.<span class="li-normal"> type:string choice:
                      alert,
                      alert_deny,
                      disable,
                      block-period</span></li>     
              <li><span class="li-head"> block_period_anomaly </span> Block Period for Threat Detection.<span class="li-normal"> type:string
                    maxLength:255</span></li>   
              <li><span class="li-head"> severity_anomaly </span> Severity for Threat Detection.<span class="li-normal"> type:string choice:
                      Info,
                      Low,
                      Medium,
                      High</span></li>
              <li><span class="li-head"> trigger_anomaly </span>Name of the Trigger Policy for Threat Detection.<span class="li-normal"> type:string
                    maxLength:255</span></li>  
              <li><span class="li-head"> url_replacer_policy </span>Name of the URL Replacer Policy.<span class="li-normal"> type:string
                    maxLength:255</span></li>  
              <li><span class="li-head"> ip_list_type </span> Severity for Schema Protection.<span class="li-normal"> type:string choice:
                      Block,
                      Trust</span></li>
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
    - name: add a ML Based API protection policy
      fwebos_ml_based_api_protection_policy:
        action: add 
        policy_id: 11987745072721173265
        rule_domain:
          - ddccd
          - aadddc
        rule_ip:
          - 1.2.3.4
          - 10.2.41.34

    - name: get a ML Based API protection policy
      fwebos_ml_based_api_protection_policy:
        action: get 
        id: 1

    - name: edit a ML Based API protection policy
      fwebos_ml_based_api_protection_policy:
        action: edit 
        id: 1
        action_mlapi: block-period
        block_period_mlapi: 567
        severity_mlapi: High
    
    - name: delete a ML Based API protection policy
      fwebos_ml_based_api_protection_policy:
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