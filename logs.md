Category	Description	File (Ubuntu)	Example

Authentication - auth.log - This log file contains all authentication (log in). This is usually attempted either remotely or on the system itself (i.e., accessing another user after logging in).	

Package Management - dpkg.log - This log file contains all events related to package management on the system. When installing a new software (a package), this is logged in this file. This is useful for debugging or reverting changes in case this installation causes unintended behaviour on the system.

Syslog - syslog - This log file contains all events related to things happening in the system's background. For example, crontabs executing, services starting and stopping, or other automatic behaviours such as log rotation. This file can help debug problems.

Kernel - kern.log - This log file contains all events related to kernel events on the system. For example, changes to the kernel, or output from devices such as networking equipment or physical devices such as USB devices.