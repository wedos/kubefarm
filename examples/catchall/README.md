# Catchall cluster

This setup illustrates the deployment of catchall cluster with tje dynamic DHCP-range.  
It might be used to catch all unknown clients in the network.

#### Deploying

[values.yaml](values.yaml) contains following DHCP settings:

* DHCP-range: `10.28.72.10-10.28.72.250` (`12h`)
* Netmask: `255.255.0.0`
* Broadcast: `10.28.255.255`
* Gateway: `10.28.0.1`
* DNS Server: `10.28.0.1`

apply:

```
helm upgrade --install catchall ../../deploy/helm/kubefarm -f values.yaml --wait
```