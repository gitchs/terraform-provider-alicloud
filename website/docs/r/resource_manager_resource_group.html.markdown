---
subcategory: "Resource Manager"
layout: "alicloud"
page_title: "Alicloud: alicloud_resource_manager_resource_group"
sidebar_current: "docs-alicloud-resource-resource-manager-resource-group"
description: |-
  Provides a Alicloud Resource Manager Resource Group resource.
---

# alicloud_resource_manager_resource_group

Provides a Resource Manager Resource Group resource. If you need to group cloud resources according to business departments, projects, and other dimensions, you can create resource groups.
For information about Resource Manager Resoource Group and how to use it, see [What is Resource Manager Resource Group](https://www.alibabacloud.com/help/en/doc-detail/94485.htm)

-> **NOTE:** Available since v1.82.0.

## Example Usage

Basic Usage

```terraform
variable "name" {
  default = "tfexample"
}

resource "alicloud_resource_manager_resource_group" "example" {
  resource_group_name = var.name
  display_name        = var.name
}
```
## Argument Reference

The following arguments are supported:

* `name` - (Optional, ForceNew, Deprecated from v1.114.0) Field `name` has been deprecated from version 1.114.0. Use `resource_group_name` instead.
* `resource_group_name` - (Optional, ForceNew, Available since v1.114.0) The unique identifier of the resource group.The identifier must be 3 to 12 characters in length and can contain letters, digits, periods (.), hyphens (-), and underscores (_). The identifier must start with a letter.
* `display_name` - (Required) The display name of the resource group. The name must be 1 to 30 characters in length and can contain letters, digits, periods (.), at signs (@), and hyphens (-).
* `create_date` - (Removed form v1.114.0) The time when the resource group was created.
* `region_statuses` - (Optional) The status of the resource group in all regions. See [`region_statuses`](#region_statuses) below.

### `region_statuses`

The region_statuses supports the following:
* `region_id` - (Optional) The region ID.
* `status` - (Optional) The status of the regional resource group.

## Attributes Reference

* `id` - The ID of the resource group.
* `status` - The status of the resource group.
* `account_id` - The ID of the Alibaba Cloud account to which the resource group belongs.

## Import

Resource Manager Resource Group can be imported using the id, e.g.

```shell
$ terraform import alicloud_resource_manager_resource_group.example abc123456
```
