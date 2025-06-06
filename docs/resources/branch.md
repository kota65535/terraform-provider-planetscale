---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "planetscale_branch Resource - terraform-provider-planetscale"
subcategory: ""
description: |-
  A PlanetScale branch.
---

# planetscale_branch (Resource)

A PlanetScale branch.

## Example Usage

```terraform
resource "planetscale_branch" "example" {
  organization  = "example"
  database      = "example_db"
  name          = "antoinewritescode"
  parent_branch = "main"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `database` (String) The database this branch belongs to.
- `name` (String) The name of the branch.
- `organization` (String) The organization this branch belongs to.
- `parent_branch` (String) The name of the parent branch from which the branch was created.

### Optional

- `production` (Boolean) Whether or not the branch is a production branch.
- `seed_data` (String) Seed data using the Data Branching® feature. Valid value is `last_successful_backup`

### Read-Only

- `actor` (Attributes) The actor who created this branch. (see [below for nested schema](#nestedatt--actor))
- `created_at` (String) When the branch was created.
- `html_url` (String) Planetscale app URL for the branch.
- `id` (String) The ID of the branch.
- `mysql_address` (String) The MySQL address for the branch.
- `mysql_edge_address` (String) The address of the MySQL provider for the branch.
- `ready` (Boolean) Whether or not the branch is ready to serve queries.
- `region` (Attributes) The region in which this branch lives. (see [below for nested schema](#nestedatt--region))
- `restore_checklist_completed_at` (String) When a user last marked a backup restore checklist as completed.
- `restored_from_branch` (Attributes) todo (see [below for nested schema](#nestedatt--restored_from_branch))
- `schema_last_updated_at` (String) When the schema for the branch was last updated.
- `shard_count` (Number) The number of shards in the branch.
- `sharded` (Boolean) Whether or not the branch is sharded.
- `updated_at` (String) When the branch was last updated.

<a id="nestedatt--actor"></a>
### Nested Schema for `actor`

Read-Only:

- `avatar_url` (String) The URL of the actor's avatar
- `display_name` (String) The name of the actor
- `id` (String) The ID of the actor


<a id="nestedatt--region"></a>
### Nested Schema for `region`

Read-Only:

- `display_name` (String) Name of the region.
- `enabled` (Boolean) Whether or not the region is currently active.
- `id` (String) The ID of the region.
- `location` (String) Location of the region.
- `provider` (String) Provider for the region (ex. AWS).
- `public_ip_addresses` (List of String) Public IP addresses for the region.
- `slug` (String) The slug of the region.


<a id="nestedatt--restored_from_branch"></a>
### Nested Schema for `restored_from_branch`

Read-Only:

- `created_at` (String) When the resource was created.
- `deleted_at` (String) When the resource was deleted, if deleted.
- `id` (String) The ID for the resource.
- `name` (String) The name for the resource.
- `updated_at` (String) When the resource was last updated.

## Import

Import is supported using the following syntax:

```shell
# Branches can be imported using "org,database,branch" as the identifier.
terraform import planetscale_branch.example "org,database,branch"
```
