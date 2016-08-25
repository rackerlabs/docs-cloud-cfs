.. _list-load-balancer-details:

.. COMMENT: This topic is an example of a task that you might include in the
   getting started portion of your API guide. Use gerunds for the titles of
   these tasks, so that these titles don't conflict with titles in the API
   reference section. Provide steps as necessary, and example data. 

Retrieving load balancer details
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To retrieve details about a load balancer that is
configured and associated with your account, use the retrieve load balancer
details operation.

The following examples request the details for the load balancer that you
created in the preceding section. The value from the ``load_balancer_id``
field, ``5355``, is used in the URL in the examples.

The following examples show the cURL requests to retrieve load balancer details.

**Example: cURL retrieve load balancer details request: XML**

.. code::

    curl -s  \
    -H "X-Auth-Token: $AUTH_TOKEN"  \
    -H "X-Project-Id: $TENANT_ID" \
    -H "Accept: application/xml"  \
    "$API_ENDPOINT/loadbalancers/5355" | ppxml

**Example: cURL retrieve load balancer details request: JSON**

.. code::

    curl -s  \
    -H "X-Auth-Token: $AUTH_TOKEN"  \
    -H "X-Project-Id: $TENANT_ID" \
    -H "Accept: application/json"  \
    "$API_ENDPOINT/loadbalancers/5355" | python -m json.tool


The following examples show the responses for retrieving load balancer details.

**Example: Retrieve load balancer details response: XML**

.. code::

    <loadBalancer xmlns="http://docs.openstack.org/loadbalancers/api/v1.0"
        id="5355"
        name="a-new-loadbalancer"
        protocol="HTTP"
        port="80"
        algorithm="RANDOM"
        status="ACTIVE"
        timeout="30">
        <connectionLogging enabled="false" />
        <virtualIps>
            <virtualIp
                id="1163"
                address="50.56.166.100"
                ipVersion="IPV4"
                type="PUBLIC" />
            <virtualIp
                id="9002499"
                address="2001:4800:7901:0000:9c92:6fca:0000:0001"
                ipVersion="IPV6"
                type="PUBLIC"/>
        </virtualIps>
        <nodes>
            <node
                id="44615"
                address="50.56.207.146"
                port="80"
                condition="ENABLED"
                status="ONLINE" />
        </nodes>
        <cluster name="ztm-n02.lbaas.dfw1.rackspace.net" />
        <created time="2010-11-30T03:23:42Z" />
        <updated time="2010-11-30T03:23:44Z" />
        <sourceAddresses ipv4Servicenet="10.183.250.133" ipv4Public="174.143.139.133" ipv6Public="2001:4800:7901::2/64"/>
    </loadBalancer>

**Example: Retrieve load balancer details response: JSON**

.. code::

    {
        "loadBalancer":{
            "id": 5355,
            "name":"a-new-loadbalancer",
            "protocol":"HTTP",
            "port": 80,
            "algorithm":"RANDOM",
            "status":"ACTIVE",
            "timeout": 30,
            "connectionLogging":{
                "enabled":false
            },
            "virtualIps":[
                {
                    "id": 1163,
                    "address":"50.56.166.100",
                    "ipVersion":"IPV4",
                    "type":"PUBLIC"
                },
                {
                    "id": 9002499,
                    "address":"2001:4800:7901:0000:9c92:6fca:0000:0001",
                    "ipVersion":"IPV6",
                    "type":"PUBLIC"
                }
            ],
            "nodes":[
                {
                    "id": 44615,
                    "address":"50.56.207.146",
                    "port": 80,
                    "condition":"ENABLED",
                    "status":"ONLINE"
                }
            ],
            "cluster":{
                "name":"ztm-n02.lbaas.dfw1.rackspace.net"
            },
            "created":{
                "time":"2010-11-30T03:23:42Z"
            },
            "updated":{
                "time":"2010-11-30T03:23:44Z"
            },
            "accountLoadBalancerServiceEvents":{
                "accountId":406271
            },
            "sourceAddresses":{"ipv6Public":"2001:4800:7901::2/64","ipv4Servicenet":"10.183.250.133","ipv4Public":"174.143.139.133"}
        }
    }
