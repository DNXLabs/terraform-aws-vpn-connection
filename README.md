# terraform-aws-vpn-connection

This module creates the VPN site-to-site network resources.

The following resources will be created:
 - Private Gateway
 - Customer Gateway 
 - VPN Site-to-site connection


## Execution Diagram of `terraform-aws-vpn-connection`
![](_docs/assets/vpn.png)

## Usage

```hcl
module "vpn" {
  source = "git::https://github.com/DNXLabs/terraform-aws-vpn-connection?ref=1.0.0"
  vpc_id                                    = module.network[0].vpc_id
  vpn_gateway_amazon_side_asn               = 64512
  customer_gateway_bgp_asn                  = 65000
  customer_gateway_ip_address               = "172.0.0.1"
  route_table_ids                           = []
  vpn_connection_static_routes_only         = true
  vpn_connection_static_routes_destinations = ["10.80.1.0/24"]
  vpn_connection_tunnel1_inside_cidr        = null
  vpn_connection_tunnel2_inside_cidr        = null
  vpn_connection_tunnel1_preshared_key      = null
  vpn_connection_tunnel2_preshared_key      = null
}
```

<!--- BEGIN_TF_DOCS --->

Error: Missing newline after argument: An argument definition must end with a newline.

<!--- END_TF_DOCS --->

## Authors

Module managed by [DNX Solutions](https://github.com/DNXLabs).

## License

Apache 2 Licensed. See [LICENSE](https://github.com/DNXLabs/terraform-aws-vpn-connection/blob/master/LICENSE) for full details.
