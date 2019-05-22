# cloud-backup

Dockerfile S3 backup set-ups for Consul and Nomad for cloud usage.

## Consul Backup

This module can only be applied by users with the right policies. You will need
to provide a valid Nomad and Vault token.

This sets up a "cron" job in Nomad to backup Consul to S3.

It runs an Ansible playbook to download a snapshot from Consul, and then uploads
it to S3.

For more information about the variables to run with the playbook, check:

- [site.yml](consul/site.yml)

## Nomad Backup

This image can only be applied by users with the right policies. You will need
to provide a valid Nomad and Vault token.

This sets up a "cron" job in Nomad to backup Nomad to S3.

It runs an Ansible playbook to retrieve all the jobs and definition from Nomad's
API, and then uploads it to S3.

For more information about the variables to run with the playbook, check:

- [site.yml](nomad/site.yml)
- [job_detail.yml](nomad/job_detail.yml)
