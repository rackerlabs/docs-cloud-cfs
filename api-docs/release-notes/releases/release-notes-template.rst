.. _latest-release-notes:

.. Template instructions: Specify the version number and date in the title. If
   there is no version number, use the API contract version and date. Revise the
   content in this template to be relevant for your release.

|release|, Month DD, YYYY
~~~~~~~~~~~~~~~~~~~~~~~~~

This release provides updates to |apiservice| |contract version|. These
changes are backward compatible and are not intended to break
any existing code that relies on the API (SDK, web applications, scripts, an so
on). However, you might want to update your code to take advantage of new
features, enhancements, and fixes.

To report issues related to these changes, submit feedback in the Rackspace
Community or contact Rackspace Support.

.. Template instructions: Content categories are "What's new,"
   "Resolved issues," "Known issues," and "Documentation changes."
   Include the "What's new," "Resolved issues," and "Known issues" sections
   in every RN file, even if you have no content for one of those sections.
   Include the "Documentation changes" section only if you have significant
   content changes, such as adding an extended example, a tutorial, or new
   content. Limit documentation changes to content important to API users and
   developers, for example "added extended example to illustrate use of xxx
   operation" or something like that.

.. whats-new:

What's new
----------

.. Comment: Use sentences to describe new features and enhancements, such as
   new operations, changed operations, and schema changes. Provide details as
   needed, and provide a link to any section in the documentation that
   describes that feature. If you have more than one new feature or enhancement
   to describe, use a bulleted list. If there are no new features and
   enhancements for the release, use the |no changes| variable for the body
   text. This variable inserts the boilerplate text "None for this release."

This release is a maintenance release that resolves existing issues with
version |contract version| of the |apiservice|.

.. resolved-issues:

Resolved issues
---------------

.. Comment: Provide an initial phrase that describes the issue that was fixed.
   Start the phrase with a past-tense verb. If necessary, include sentences to
   further explain the fix. If you list only phrases, do not use ending
   punctuation. If there are no resolved issues for the release, use the
   |no changes| variable for the body text. This variable inserts the
   boilerplate text "None for this release."

* Added support for Debian 8 (Jessie)
* Trimmed the Monitoring ID and Monitoring Token configuration variables to
  ensure correctness
* Fixed the Xen Server 6 package repo


Known issues
------------

.. Comment: Use sentences to describe the issue. If a workaround is available,
   explain it. If there are no known issues for the release, use the
   |no changes| variable for the body text. This variable inserts the
   boilerplate text "None for this release," as shown here.

|no changes|


.. doc-changes:

Documentation changes
---------------------

.. Comment: Include this section only if you have significant content changes,
   such as adding an extended example, a tutorial, or new content. If you have
   no significant content changes for a release, omit this section entirely.
   Provide an initial phrase that describes the issue that was fixed. Start the
   phrase with a past-tense verb. If necessary, include sentences to further
   explain the fix. If you list only phrases, do not use ending punctuation.
   Provide a link to the relevant section in the documentation.

* Added volume and flavor information to the API operation to list HA database
  instance details.

* Added a note about converting an automated backup schedule, if a
  source/replica has automated backups enabled, to the API operation  to
  convert replication setup to HA. In this case, the schedule is converted to
  an HA group automated backup schedule with the source ID set to the HA ID.
  The day, hour, and minute settings are the same as the source or replica
  schedule.

* Documented source changes to the RESTART state when enabling as master
  during replication setup.
