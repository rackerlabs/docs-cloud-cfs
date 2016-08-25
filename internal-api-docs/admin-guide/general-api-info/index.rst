.. _general-api-info:

=======================
General API information
=======================

The information in this section is relevant to all operations of the API.
For details about specific operations, see the
:ref:`API reference <api-reference>`.

The |apiservice| is implemented using a RESTful web
service interface. Like other Rackspace Cloud services, this service
shares a common token-based authentication system that allows seamless
access between products and services.


.. note::

    All requests to authenticate and operate the service are performed using
    HTTPS on TCP port 443. For authentication instructions, see
    :ref:`Authenticate to the Rackspace Cloud <authenticate-to-cloud>`.

.. COMMENT: The topics in the toctree vary based on the API being documented. 
   Update topics and adapt information in topics based on your product.

.. toctree::
   :maxdepth: 1

   service-access
   request-response
   content-compression
   persistent-connections
   paginated-collections
   limits
   faults
   http-status-codes
   date-time-format
   api-behavior
   role-based-access-control
