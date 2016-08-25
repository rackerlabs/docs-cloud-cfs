.. _using-cloud-load-balancers:

================================
Create and manage load balancers
================================

.. COMMENT: Use this section to describe the main tasks that users can perform
   by using the product API. The content that is presented here is an example.
   You can have more than one high-level section like this one, as needed, or
   organize all your tasks under one high-level section. Replace this content
   with relevant content for your product.

You can use the examples in this section to create and manage load balancers
by using Cloud Load Balancers API operations. Before running the examples,
review the :ref:`Cloud Load Balancers concepts<concepts>` to understand the
API workflow, messaging patterns, and use cases.

.. note::
     These examples use the ``$API_ENDPOINT``, ``$AUTH_TOKEN``, and
     ``$TENANT_ID`` environment variables to specify the API endpoint,
     authentication token, and project ID values for accessing the service.
     Be sure to :ref:`configure these
     variables<configure-environment-variables>` before running the
     code samples.


.. COMMENT: The following topics are provided as examples. Replace them with
   relevant content for your product, and provide as much content as is
   necessary for your product.

.. include:: examples/create-cloud-servers-to-lb.rst
.. include:: examples/create-load-balancer.rst
.. include:: examples/list-load-balancer-details.rst
