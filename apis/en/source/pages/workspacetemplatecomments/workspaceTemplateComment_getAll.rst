.. Copyright 2017 FUJITSU LIMITED

.. _workspaceTemplateComment-getAll:

workspaceTemplateComment_getAll
-------------------------------

.. function:: GET /orgs/{oid}/workspaces/{wid}/templates/{tid}/comments

.. sidebar:: Summary

	* Method: ``GET``
	* Response Code: ``200 / 304``
	* Response Formats: ``application/xml`` ``application/json``
	* Since: ``UForge 3.3.2``

Retrieves all the comments posted in a shared appliance template. 

A list of :ref:`comment-object` objects are returned. 

You can use a ``search criteria`` to retrieve a subset of these comments.

Security Summary
~~~~~~~~~~~~~~~~

* Requires Authentication: ``true``
* Entitlements Required: ``None``

URI Parameters
~~~~~~~~~~~~~~

* ``wid`` (required): the id of the :ref:`workspace-object`
* ``oid`` (required): the id of the :ref:`org-object`
* ``tid`` (required): the id of the :ref:`gallerytemplate-object`

HTTP Request Body Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

None

Example Request
~~~~~~~~~~~~~~~

.. code-block:: bash

	curl "https://uforge.example.com/api/orgs/{oid}/workspaces/{wid}/templates/{tid}/comments" -X GET \
	-u USER_LOGIN:PASSWORD -H "Accept: application/xml"

.. seealso::

	 * :ref:`workspace-api-resources`
	 * :ref:`workspacetemplate-api-resources`
	 * :ref:`workspacecomments-api-resources`
	 * :ref:`comment-object`
	 * :ref:`workspaceTemplateComment-create`
	 * :ref:`workspaceTemplateComment-reply`
	 * :ref:`workspaceTemplateComment-getAll`
	 * :ref:`workspaceTemplateComment-get`
	 * :ref:`workspaceTemplateComment-update`
	 * :ref:`workspaceTemplateComment-deleteAll`
	 * :ref:`workspaceTemplateComment-delete`
	 * :ref:`workspaceTemplateComment-reportAbuse`
	 * :ref:`workspaceTemplateComment-like`
	 * :ref:`workspaceTemplateComment-dislike`
