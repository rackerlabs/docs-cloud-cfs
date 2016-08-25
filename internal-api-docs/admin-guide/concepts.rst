.. _concepts:

==================
|service| concepts
==================

To use the |apiservice| effectively, you should understand several key concepts.

.. COMMENT: The following concepts are provided as examples only. Replace
   them with relevant information for your product, and provide as many
   concepts as needed.  

.. _concept-load-balancer:

Load balancer
~~~~~~~~~~~~~
A logical device that belongs to a cloud account. A load balancer is used to
distribute workloads between multiple back-end systems or services, based on the
criteria that is defined as part of its configuration.

.. _concept-virtual-ip:

Virtual IP
~~~~~~~~~~
An Internet Protocol (IP) address configured on the load balancer for use by
clients connecting to a service that is load balanced. Incoming connections are
distributed to back-end nodes based on the configuration of the load balancer.

.. _concept-error-page:

Error page
~~~~~~~~~~

The HTML file that is shown to the end user when an error in the service is
generated. By default, every virtual server is provided with the default error
file. It is also possible to submit a custom error page via the Load Balancers
API.

.. _concept-node:

Node
~~~~

A back-end device that provides a service on a specified IP address and port.
