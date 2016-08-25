.. _create-load-balancer:

.. COMMENT: This topic is an example of a task that you might include in the
   getting started portion of your API guide. Use gerunds for the titles of
   these tasks, so that these titles don't conflict with titles in the API
   reference section. Provide steps as necessary, and example data.

Creating a load balancer
~~~~~~~~~~~~~~~~~~~~~~~~

Cloud Load Balancers make it easy to develop scalable, high-availability
configurations in the cloud. By leveraging Cloud Load Balancers, you
are provided with a dedicated IP address that you can use to reach
your service.

You use the create load balancer API operation (``POST /loadbalancers``)
to create a load balancer with the configuration that you specify.

In this case, assume that you want to create a load balancer with the
following configuration:

-  Protocol = HTTP(80)

-  Virtual IP type = PUBLIC

   .. note::
      When your resources reside in the same region as your load balancer,
      devices are in close proximity to each other and can take
      advantage of ServiceNet connectivity (by specifying Virtual IP Type =
      SERVICENET) for free data transfer between services.

-  Nodes = Enter the IP address that you recorded for the first cloud
   server that you created in
   :ref:`Creating cloud servers <create-cloud-servers>`:

   ``node address="<ipAddressFirstCloudServer>" port="80" condition="ENABLED"/``

   .. note::
      Although you could add the nodes for both of your cloud servers in
      this operation, you will instead add the node for your second server by
      using the separate add node operation.

The following examples show the cURL requests for creating a load balancer with
the preceding configuration.

**Example: cURL create load balancer request: XML**

.. code::

    curl -s -d \
    '<?xml version="1.0" ?>
    <loadBalancer xmlns="http://docs.openstack.org/loadbalancers/api/v1.0"
        name="a-new-loadbalancer"
        port="80"
        protocol="HTTP">
        <virtualIps>
            <virtualIp type="PUBLIC"/>
        </virtualIps>
        <nodes>
            <node address="<IP address of FIRST cloud server>" port="80" condition="ENABLED"/>
        </nodes>
    </loadBalancer>' \
    -H "X-Auth-Token: $AUTH_TOKEN" \
    -H "X-Project-Id: $TENANT_ID" \
    -H "Content-Type: application/xml" \
    -H "Accept: application/xml" \
    "$API_ENDPOINT/loadbalancers" | ppxml

**Example: cURL create load balancer request: JSON**

.. code::

    curl -s -d \
    '{
        "loadBalancer": {
            "name": "a-new-loadbalancer",
            "port": 80,
            "protocol": "HTTP",
            "virtualIps": [
                {
                    "type": "PUBLIC"
                }
             ],
            "nodes": [
                {
                    "address": "<IP address of FIRST cloud server>",
                    "port": 80,
                    "condition": "ENABLED"
                }
            ]
        }
    }' \
    -H "X-Auth-Token: $AUTH_TOKEN" \
    -H "X-Project-Id: $TENANT_ID" \
    -H "Content-Type: application/json" \
    "$API_ENDPOINT/loadbalancers" | python -m json.tool


The following examples show the responses for creating a load balancer.

**Example: Create load balancer response: XML**

.. code::

    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
    <loadBalancer xmlns="http://docs.openstack.org/loadbalancers/api/v1.0" id="5355" name="a-new-loadbalancer"
        algorithm="RANDOM" protocol="HTTP" port="80" status="BUILD">
        <virtualIps>
            <virtualIp id="1163" address="50.56.166.100" ipVersion="IPV4" type="PUBLIC"/>
            <virtualIp id="9002499" address="2001:4800:7901:0000:9c92:6fca:0000:0001" ipVersion="IPV6" type="PUBLIC"/>
        </virtualIps>
        <nodes>
            <node id="44615" address="50.56.207.146" port="80" condition="ENABLED" status="ONLINE" weight="1"/>
        </nodes>
        <cluster name="ztm-n02.lbaas.dfw1.rackspace.net"/>
        <created time="2012-02-29T18:20:44Z"/>
        <updated time="2012-02-29T18:20:44Z"/>
        <connectionLogging enabled="false"/>
        <sourceAddresses ipv4Servicenet="10.183.250.133" ipv4Public="174.143.139.133" ipv6Public="2001:4800:7901::2/64"/>
    </loadBalancer>

**Example: Create load balancer response: JSON**

.. code::

    {
        "loadBalancer":{
            "name":"a-new-loadbalancer",
            "id":5355,
            "port":80,
            "protocol":"HTTP",
            "algorithm":"RANDOM",
            "status":"BUILD",
            "cluster":{
            "name":"ztm-n02.lbaas.dfw1.rackspace.net"
            },
            "nodes":[{
                    "address":"50.56.207.146",
                    "id":44615,
                    "port":80,
                    "status":"ONLINE",
                    "condition":"ENABLED",
                    "weight":1
                }
            ],
            "virtualIps":[{
                    "address":"50.56.166.100",
                    "id":1163,
                    "type":"PUBLIC",
                    "ipVersion":"IPV4"
                },
                {
                    "address":"2001:4800:7901:0000:9c92:6fca:0000:0001",
                    "id":9002499,
                    "type":"PUBLIC",
                    "ipVersion":"IPV6"
                }
            ],
            "created":{
                "time":"2012-02-29T18:20:44Z"
            },
            "updated":{
                "time":"2012-02-29T18:20:44Z"
            },
            "connectionLogging":{
                "enabled":false
            },
            "sourceAddresses":{
                "ipv6Public":"2001:4800:7901::2/64",
                "ipv4Servicenet":"10.183.250.133",
                "ipv4Public":"174.143.139.133"
            }
        }
    }

These examples show that one node (with IP address 50.56.166.100) has
been added to your new load balancer with an ID of 5355. You will need
the load balancer ID for the retrieve load balancer details operation in the
next section, and you should supply this value wherever you see the 
``load_balancer_id`` placeholder in the examples in this guide.
