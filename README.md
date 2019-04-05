AWS DC/OS Additional EBS Volumes and Attachments (NOTE: THIS IS CURRENTLY EXPERIMENTAL AND NOT YET SUPPORTED)
===========
This module creates additional ebs volumes and attaches them to the instances. This is based on best practices for DC/OS.

EXAMPLE
-------

```hcl
module "agent_volumes" {
 source = "dcos-terraform/volumes-dcos/aws"
 num                     = "3"
 instance_id             = ["id-ablsldhfa123", "id-blahblah1234", "id-abncsss43112"]
 availability_zone       = ["us-east-1a", "us-east-1b", "us-east-1c"]
 mesos_size              = "500"
 docker_size             = "250"
 log_size                = "800"
 disk_type               = "gp2"
}
```

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| availability\_zone | AZ(s) of where to create the Volumes | list | n/a | yes |
| disk\_type | Disk Type to Leverage | string | `"gp2"` | no |
| docker\_size | Size of the /var/lib/docker disk | string | `"100"` | no |
| extra\_volume\_size | Size of an extra Volume | string | `"50"` | no |
| instance\_id | The instance ID to attach the disks to | list | n/a | yes |
| log\_size | Size of the /var/log disk | string | `"500"` | no |
| mesos\_size | Size of the /var/lib/mesos disk | string | `"250"` | no |
| num | How many instances should be created | string | `"1"` | no |

