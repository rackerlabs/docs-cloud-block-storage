.. _extension-lunr-session:

lunr session
~~~~~~~~~


Description:
This extension enables members with the correct role to view iscsi status.
Unlike attachment status, which pulls its contents out of the cinder database,
this information is discovered from storage server in real time and is guaranteed
to be accurate and appropriate as a diagnostic tool.

This extension extensions adds to the existing volume template the following information:

  * rs-vol-lunr-sessions iscsi initiator IP
  * rs-vol-lunr-sessions-error

Applied roles:

  * cbs:support
