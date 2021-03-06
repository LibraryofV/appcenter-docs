.. Copyright 2017 FUJITSU LIMITED

Changelog
=========

3.7.fp1
-------

Release Date: 2017-01-09

New Features
~~~~~~~~~~~~

* Multi-NIC support for Linux based appliance templates.
* Driver injection improvements (internal mechanism) for Windows-based appliance templates. 

Bug Fixes
~~~~~~~~~

* 6326 Impossible to publish an ``OpenStack VDI`` image
* 6323 Cloud account name appears twice in the public informations in UI for all Cloud formats
* 6234 Sticky package of imported template is not shown in the UI
* 6141 User gets a 500 call failed if a custom target platform has been added but not enabled specifically for the user
* 6042 OS packages are not sortable in the ``Repository`` column
* 6237 Spelling mistakes in the API docs
* 6222 Format enabling/disabling not working when updating the UI config
* 6453 Impossible to generate image when install profile contains users
* 6199 Migration fails because the user ID taken from a scan and user ID that the package makes overlap.
* 6409 OE-lite can't fetch QT source file
* 6206 Filter inactive pkgs on ``DistributionPackages.getAll()`` method
* 6200 Scanning a disabled OS is possible
* 6190 Scanning an azure vm with advance partitioning : install profile partioning not correct
* 6180 Errors outputted into ``/oar/oar_scan_job*.stderr`` when scanning CentOS 6
* 6154 Launching windows scan binary from command line with API key does not launch the scan
* 6134 Pkg overlay archive are built differently if a black box migration is done first or if it's a scan import to appliance
* 6309 Several concurrent generations could fail if there are uncached software bundles files in it
* 6211 Creating a two bootscripts with same name does not show an error message
* 6194 Japanese Characters are OK to use but encoded incorrectly for ``Tag`` and ``Maintainer`` fields of a software component
* 6193 Same rpm file can be uploaded without overwritten to a software component
* 6178 Errors outputted into ``/oar/job_finalize.log`` when generating CentOS image
* 6169 Total Disk Usage doesn't count the size of files uploaded to software components
* 6027 Exported template has lost some information on MySoftware
* 6346 WARP should skip to inject uforge agent in the specific condition
* 6327 Scripts are not imported when sharing a template in a ``Workspace``
* 6057 Yum update error ``uforge_update.sh: line 660: [: too many arguments``
* 6055 The volume shadow copy is not deleted after scan of Windows.
* 6007 Code in ``distrotools/lib/str.[c|h]`` in function ``repl_str()`` cannot compile for windows using ``mingw c++``
* 6440 Can't display ``Projects`` as guest user
* 6453 Impossible to generate image when install profile contains users


3.7
---

Release Date: 2016-12-27

New Features
~~~~~~~~~~~~
None (released based 3.6-fp2)

Bug Fixes
~~~~~~~~~

* 6537 Removed AMI format for AWS S3
* 6521 Launching windows scan binary from command line with API key does not launch the scan
* 6517 Impossible to know which publish image on UForge corresponds to which Image in K5 portal
* 6515 CentOS 6 images can be accessed with SSH on K5
* 6513 Validation for K5 publish view is not properly handled
* 6511 Launching uforge-scan.exe from command prompt still fails if the file path includes Japanese characters
* 6507 The ``uforge-install-config`` binary for windows does not start because ``uforge-install-profile-1-1.noarch.zip`` does not contain the correct directory structure.
* 6505 The ``no_console`` file is not created for Windows.
* 6504 Problem with OpenDJ port 4444 usage in several UForge config scripts
* 6503 The ``uforge.conf.ORIG`` contains plain passwords with very weak permission
* 6502 AWS connector uses a fixed size 3.4 GB disk and publication fails for larger images
* 6422 Uploading an avatar image twice, the first image is still used
* 6410 Loading page empty during 5 seconds for the first time in ``Sofware Library`` view
* 5897 If a space is used in cloud accounts in openstack in the URL, then an internal error is observed
* 5849 Displaying the logo in view package details of a target format is not displayed
* 6488 Impossible to generate image when install profile contains users
* 6362 AWS resource connector no longer work due to credential changes
* 6064 The CLI command ``org repo update`` returns exception if ``--type`` param value is invalid.
* 5900 Generation sometimes fails if the second disk of the appliance is too small


3.6-fp2
-------

Release Date: 2016-12-05

New Features
~~~~~~~~~~~~

* Fujitsu K5 support.  Can now register machine images generated on the platform to Fujitsu K5.

	.. note:: The following operating systems are supported for the moment (others will be supported soon):

		* CentOS 7.0
		* Ubuntu 14.04

* SELinux support when creating appliance templates and during migration
* Docker machine image generation support.  This allows users to build docker base images.
* When scanning Windows machines, the scan report now includes the services detected.

	.. note:: The platform does not support the comparison of windows-based scans at this time.

RFEs
~~~~

* Better progress status when scanning Windows machines
* Less restrictive validation of website information in the MySoftware/Project Overview
* New icons for 'pull' and 'upload' for software/project files management
* Added directory icon when displaying all the files for software/project files view
* When deleting a folder, the confirm message should be more explicit (that all sub folders and files will also be deleted)
* Better explanation of the "cached" option for software/project files in the UI
* Managing licenses for software/project components; there is now an explicit delet button to remove an uploaded license file 

Bug Fixes
~~~~~~~~~

* 6123 Publishing a generation from a scan results in 500 error in UI
* 6089 Member's role on workspace couldn't be changed if language is set as French or Japanese
* 6017 Canceling from Appliance Create no longer returns to previous page
* 5946 Publishing to CloudStack fails with the next error: vhd.gz: No such file or directory
* 5942 RHEL is added despite launching `org os add` for Oracle Linux or Scientific Linux with cli
* 5909 User ID and group ID of the install profile can be set 0
* 5906 UserResourcesAccessRights database mapping not proxied
* 5896 Deployment fails due to NIC settings
* 5892 Deployment fails when using eth1
* 5843 "org category delete" raises an error
* 5777 Launching uforge-scan.exe from command prompt fails with an error if the file path to the binary includes Japanese characters.
* 5762 Cannot register the third disk with a VirtualBox image
* 5756 New users, the defaukt country is: Abkhasia
* 5754 opening the Dashboard > Generations page first shows progress bar for all publications
* 5752 Number of MySoftware components not properly refreshed in the UI
* 5750 Number of Appliance not properly refreshed in the UI
* 5748 The diskusage of "uforge user quota list" is displayed by byte
* 5684 Invite the same user in the collaboration members list does not show error message
* 5676 Duplicated variable in /etc/default/grub if distribution provides default values.
* 5647 Keyboard and kernel parameters are not taken into the scan report on CentOS 7 scan.
* 5635 Broken incremental scan for windows 2012R2
* 5627 Cancelling scan via ctrl+c is not correctly displayed in the UI
* 5625 uforge-scan does not respect bandwidth limit
* 5623 When the image of CentOS7 is generated, RPM-GPG-KEY-CentOS import read fails
* 5621 rpmgen fails to build package if file path in %file includes space.
* 5570 Impossible to delete an incremental scan
* 5562 UForge CLI accesses to interactive mode even if the user or password are wrong
* 5560 The input value of the activation key is not saved in a Windows appliance
* 5342 Scan incremental with Ubuntu does not appear in UI
* 5265 No dialog box displayed after running an instance on Azure


3.6-fp1
-------

Release Date: 2016-10-31

New Features
~~~~~~~~~~~~

* Import/Export of appliance templates in the user interface
* Software (MySoftware) and Project bundles now consolidated.  New features added including:
	- pulling files from remote locations (HTTP, FTP endpoints) so the user no longer requires to upload software components to the platform
	- pulling files can be cached for future generations or pulled on each generation
	- file permissions added for files and directories
	- can create directory structures in a software bundle
	- can add tagging information to a software bundle
	- can add native packages from OS respositories to a software bundle
	- can add boot scripts to a software bundle
	- identify the software bundle only being supported on a subset of operating systems

* API keys can be used for authentication when running a scan for migration.
* Scan messages and error messages cleaned up and more understandable
* Japanese language localization for the UI


Bug Fixes
~~~~~~~~~

* 5293 Image generation error: Windows image must have at least 512 MB of memory
* 5729 Issues with migration from 3.5.1. to 3.6
* 5465 Build fails due to unreachable rpm-4.11.2.tar.bz2
* 5740 Fix DB schema checks
* 5331 AWS publish no longer works
* 5637 Windows generation from scan fails at boot
* 5427 Unable to generate a virtual machine with LVM inside a MSDOS disk
* 5291 All combo boxes are empty when a value has been selected
* 5876 Logo broken on Dashboard
* 5444 Unable to populate Fedora/RHEL distributions
* 5420 When a template is remobed from a workspace, a DELETE error appears in the log file
* 5527 Subscription info does not list the frequency of quotas
* 5494 Scan fails because of files of type c (character device file)
* 5483 The service command not found in a machine generated by UForge
* 5442 The file deletion of Project fails
* 5429 Root can disable root account in UForge CLI
* 5746 Timeout of 10 seconds for the UForge CLI is not usable
* 5563 Internal error in Migration tab
* 5558 500 Call Fail Error when generating an image from scan
* 5556 The targetformat of Amazon is not displayed when generating an image
* 5553 If a scan is deleted, the image generated from the same scan is not deleted
* 5551 Spelling mistake in UI when publishing to Flexiant
* 5549 The error of Keystone version is displayed in Keystone Server URL
* 5403 Scan fails when trying to rebuild a non repo package
