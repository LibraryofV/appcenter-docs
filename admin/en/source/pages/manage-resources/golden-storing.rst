.. Copyright 2017 FUJITSU LIMITED

.. _store-updated-golden:

Storing Golden Images on the NAS
--------------------------------

Each time you have a new Golden Image, you need to store them in the right NAS location.

.. note:: To store the golden images (all profiles in one language) you will need about 40Gb of disk space on the UForge NAS.

The golden images should be stored in::

	Base dir = Windows/releases/Server2008R2/x86_64/

The path is::

	{Language}/{Edition}/{Type}/{generation date}(YYYY-MM-DD)/goldenImagePathCompressedInGz

So for example:

``Windows/releases/Server2008R2/x86_64/English/Standard/Core/2012-10-19/Windows_2008R2_Standard_Core_2012-10-19.raw.gz``

.. note:: If you plan to deploy generated Windows instances onto `K5 Fujitsu Public Cloud <http://www.fujitsu.com/global/solutions/cloud/k5/>`_, only "Standard" and "Enterprise" editions are supported.

 For convenience, you can use an edition name starting by "Standard" or "Enterprise". For example: "StandardK5" will be recognized as a "Standard" edition, "EnterpriseMDR" will be recognized as "Enterprise".

 For more detailed information, please refer to `official Fujitsu K5 IaaS Documentation <http://www.fujitsu.com/uk/Images/k5-iaas-features-handbook.pdf>`_.

.. _add-golden-toAppCenter:

Adding a Golden Image to UForge AppCenter
-----------------------------------------

Once you have your Golden Image, you need to add it to your UForge AppCenter in order to be able to use the Windows version to create appliance templates. Your golden image must be in one of the following formats:

	* raw.gz
	* raw.zip
	* raw.bz2
	* raw.lrz
	* vdi
	* vhd
	* vmdk

To add your Golden Image to UForge:

	1. Copy the image to:

		.. code-block:: shell

			$ /tmp/DISTROS/Windows/releases/<windows os version>/x86_64/<language>/<my custom profile name>/<Core|Full>/<YYYY-MM-DD>/golden.xxx

		For example: /tmp/DISTROS/Windows/releases/Server2008R2/x86_64/English/MyProfile/Core/2014- 04-28/Windows_2008R2_English_Datacenter_Core_2014-04-28.raw.gz

		Note:

			* File and directory ownership should be ``tomcat:tomcat``.
			* Permissions should be readable for all users
			* Disk name must be unique in the ``/tmp/DISTORS/Windows`` file tree

	2. You must ensure that the Windows distribution exists on your UForge AppCenter. If it does not, run::

		$ uforge org os add --name Windows --arch x86_64 --version Server2008R2

	3. In order to add the new golden image to the distribution, run:

		.. code-block:: shell

			$ uforge org golden create --name Windows --arch x86_64 --version Server2008R2 --edition Standard --goldenDate 2014-04-28 --language English --type Full --goldenName Windows_2008R2_English_Standard_Full_2014-04-28.raw.gz

		.. note:: The parameters set when running ``org golden create`` should correspond to the path on the NAS, that is: {Language}/{Edition}/{Type}/{generation date}(YYYY-MM-DD)/goldenImagePathCompressedInGz

		For example to install the golden image saved to the following path: ``Windows/releases/Server2008R2/x86_64/English/Standard/Full/2012-10-19/Windows_2008R2_Standard_Full_2012-10-19.raw.gz``, you need to run::

		$ org golden create --name Windows --arch x86_64 --version Server2008R2 --language English --edition Standard --type Full --goldenDate 2012-10-19 --goldenName Windows_2008R2_Standard_Full_2012-10-19.raw.gz
