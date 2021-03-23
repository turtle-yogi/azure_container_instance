# azure_container_instance

HCL```

variable "resource_group_name" {
  default = "test-aci-rg01"
}


module "aci" {
  source              = "./terraform-azurerm-aci-master"
  dns_name_label      = "cont01-example"
  os_type             = "linux"
  image_name          = "microsoft/aci-helloworld"
  resource_group_name = var.resource_group_name
  }

output "fqdn" {
  value = module.aci.containergroup_fqdn
}

output "ip" {
  value = module.aci.containergroup_ip_address
}

output "id" {
  value = module.aci.containergroup_id
}
```