system CHANGELOG
================

This file is used to list changes made in each version of the system cookbook.

0.0.1
-----
- Initial pre-release version

0.1.0
-----
- Initial 'pre 1' minor release

0.2.2
-----
- Includes bug fixes, revised code and more testing files

0.2.3
-----
- Fix missing quote for rs_tag command in hostname provider

0.3.2
-----
- Fix missing equals sign for service_action variable
- Fix notifies for service[hostname] for Debian
- Set 127.0.1.1 on Debian if needed
- Fix for OHAI-389
- Set supports status false for hostname service
- Use service_name for hostname resource name
- Minor log text improvements for show host info
- Notify the hostname service immediately.
- Address FC037: Invalid notification action
- Add chefignore
- Add TESTING.md

0.3.3
-----
- Revision only to address https://github.com/xhost-cookbooks/system/issues/6

0.3.4
-----
- Revision only to address https://github.com/xhost-cookbooks/system/issues/8

0.4.0
-----
- Better platform support for default cron service
- timezone provider ensures inclusion of cron recipe
- Other minor fixes for cron
- Improve test suite, add basic tests
- Add a recipe to test setting of the fqdn
- New attribute, permanent_ip to affect usage of 127.0.1.1 on debian
- Fix setting hosts in /etc/hosts by using lazy loading of fqdn
- Set fqdn in compile phase, to be sure

0.4.1
-----
- Revision only to address https://github.com/xhost-cookbooks/system/issues/10

0.5.0
-----
- Add a hostsfile entry for 127.0.0.1 against localhost.localdomain when not using permanent_ip
- Include the FQDN in the hostfile entry for for 127.0.0.1 when not on Debian
- Add resource for the network service in RHEL platform family (restart it on hostname change)
- Use Chef::Util::FileEdit instead of sed to update /etc/sysconfig/network
- permanent_ip is now true by default
- Add support for hostnamectl (mostly for EL 7)
- Fix missing trailing line return for /etc/hostname
- Test Debian and CentOS with test-kitchen

0.6.0
-----
- Mac OS X support (including NetBIOS and Workgroup names)!
- Pull request #11 (default timezone is now 'Etc/UTC')
- Fail when an invalid timezone is provided
- Support providing a zone with a space instead of underscore (for the humans)
- Make before and after tz-info log resources debug log level
- update_package_list recipe will now sync MacPorts tree
- upgrade_packages recipe will now upgrade installed ports for MacPorts
- Improved test suite including use of chef_zero with test-kitchen, more platforms/versions
- Add a good handful of Serverspec tests

0.6.1
-----
- Ensure the crond service is available for restarting in timezone provider
- Add mac_os_x to supports in metadata

0.6.2
-----
- Fix cron daemon usage for arch linux (uses cronie which is not yet supported in the cron cookbook yet)
- Fix cron_service_name for arch linux (cronie) in default attributes
- Fix supports for arch linux in metadata.rb

0.6.3
-----
- Use regex with readlines grep when checking for hostname in /etc/sysconfig/network on EL-based distros (fix for issue #14)
- Help bad images/systems that have a null hostname (fix for issue #15)

0.6.4
-----
- Fix for issue #17 removing unique hostfile entry for 127.0.0.1
- Fix render of static_hosts via node attributes
- Add hostfile entries for ipv6 hosts
- Let the cron cookbook manage the cron resources entirely
- Various test elements added/improved
