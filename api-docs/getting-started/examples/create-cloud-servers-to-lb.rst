.. _create-cloud-servers:

.. COMMENT: This topic is an example of a task that you might include in
   the getting started portion of your API guide. Use gerunds for the titles
   of these tasks, so that these titles don't conflict with titles in the API
   reference section. Provide steps as necessary, and example data.

Creating cloud servers
~~~~~~~~~~~~~~~~~~~~~~

This section describes how to create two new cloud servers (or use two
existing cloud servers) to set up as nodes for your load balancer.

.. note::
   If you are using cloud servers that already exist in your account,
   skip to the last step in the following procedure.

#. Log in to the `Cloud Control Panel <http://mycloud.rackspace.com/>`__.

   .. note::
      You can also create a cloud server by using the Cloud Servers API. For
      details, see the
      `Cloud Servers API guide <http://developer.rackspace.com/>`__.

#. At the top of the page, click **Servers > Cloud Servers**.

#. On the Cloud Servers page, click **Create Server**.

#. Specify a name for the server, and select the region.

#. Select an image from a list of different operating systems, including
   Linux distributions and Windows images.

#. Specify the flavor for your server, and then click **Create Server**.

#. Create a second server by performing steps 3-6 again.

#. Go the the Cloud Servers page (**Servers > Cloud Servers**), and record the
   IP addresses of your servers, which are displayed in the list of servers. 
