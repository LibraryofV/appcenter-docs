.. Copyright 2017 FUJITSU LIMITED

.. _projectArtifact-get:

projectArtifact_get
-------------------

.. function:: GET /orgs/{oid}/projects/{pid}/artifacts/{said}

.. sidebar:: Summary

	* Method: ``GET``
	* Response Code: ``200 / 304``
	* Response Formats: ``application/xml`` ``application/json``
	* Since: ``UForge 1.0``

Retrieves the information of a software artifact contained in a project.  This only retrieves the meta-data of the project.  If you wish to download the binaries, please use :ref:`projectArtifact-download`.

Security Summary
~~~~~~~~~~~~~~~~

* Requires Authentication: ``true``
* Entitlements Required: ``org_projects_administrate``

URI Parameters
~~~~~~~~~~~~~~

* ``pid`` (required): the id of the :ref:`project-object`
* ``oid`` (required): the id of the :ref:`org-object`
* ``said`` (required): the id of the :ref:`softwareartifact-object`

HTTP Request Body Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

None

Example Request
~~~~~~~~~~~~~~~

.. code-block:: bash

	curl "https://uforge.example.com/api/orgs/{oid}/projects/{pid}/artifacts/{said}" -X GET \
	-u USER_LOGIN:PASSWORD -H "Accept: application/xml"

.. seealso::

	 * :ref:`project-object`
	 * :ref:`softwareartifact-object`
	 * :ref:`project-create`
	 * :ref:`project-getAll`
	 * :ref:`project-get`
	 * :ref:`project-delete`
	 * :ref:`project-update`
	 * :ref:`projectOs-getAll`
	 * :ref:`projectArtifact-create`
	 * :ref:`projectArtifact-getAll`
	 * :ref:`projectArtifact-updateAll`
	 * :ref:`projectArtifact-update`
	 * :ref:`projectArtifact-upload`
	 * :ref:`projectArtifact-deleteAll`
	 * :ref:`projectArtifact-delete`
	 * :ref:`projectArtifact-download`
	 * :ref:`projectArtifact-downloadFile`
	 * :ref:`projectArtifact-createFromRemoteServer`
	 * :ref:`projectArtifact-addOrRemoveFileFromCache`
	 * :ref:`projectArtifact-addChild`
	 * :ref:`projectLogo-download`
	 * :ref:`projectLogo-downloadFile`
	 * :ref:`projectLogo-upload`
	 * :ref:`projectLogo-delete`
