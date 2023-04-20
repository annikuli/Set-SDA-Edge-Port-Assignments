# Set-SDA-Edge-Port-Assignments

This API collection is built to gather static port assignments of access ports on SDA Edge.
Collection workflow:
- Get list of all access interfaces of Fabric Edge. Routed interfaces are excluded from the list.
- Iterate through this list and save configuration in two separate lists:
    - user_interface_configuration – for user ports
    - ap_interface_configuration – for ap ports


You have to run the collection instead of separate requests in order to allow Postman to iterate through list of interfaces.
INITIAL SETUP:
- Set mandatory collection variables.(Select "Get SDA Edge Port Assignments" collection and open Variables tab. Set proper values in both INITIAL and CURRENT VALUE fields):
    - "dnac_ip" - Specify DNAC IP or FQDN
    - "edge_ip_address" - Specify Loopback0 IP of target Fabric Edge
    - "user_interfaces_configuration" – set value: []
    - "ap_interfaces_configuration" – set value: []
    - Don't forget to Save changes
- Specify DNAC credentials in DNAC/Authentication request. Authorization field.
    - Don't forget to Save changes


"interfaces_start_index" - this variable points to the first interface of the Edge. It is required for "Get all interfaces" request.

"interfaces_records_to_return" - this variable define maximum number of interfaces to iterate through. It is required for "Get all interfaces" request. It is set to maximum possible value, meaning that this request can iterate over 500 interfaces maximum.



Built for:
DNAC 2.3.3.6 (API v1.0)

API versions can be changed via collection variables


