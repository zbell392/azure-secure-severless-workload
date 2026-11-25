# Bootstrap — Day 2 (2026-11-24)

- Environment: dev, East US; one personal lab subscription.
- Persistent RGs: rg-asw-dev-tfstate-eus, rg-asw-dev-network-eus,
  rg-asw-dev-app-eus, rg-asw-dev-ops-eus.
- State account: StorageV2, Standard_LRS, standard endpoint.
- State container: tfstate; state key: dev.terraform.tfstate.
- Authentication: Entra ID; local Azure CLI; container-scoped
  Storage Blob Data Contributor; future CI uses OIDC.
- Shared Key and anonymous access: disabled.
- Blob versioning; blob/container soft delete: 14 days each.
- Network exception: public backend endpoint for local and hosted CI
  access; future workload storage remains private.
- Budget: $50/month; actual 50/80/100%; forecast 100% if supported.
- Flex East US support: [result]. Regional quota: [result or unverified].
- Providers: [registered/pending]. Account delete lock: [status].
- Verification: [actual read/write/delete, anonymous denial, init result].
- Known issues: [none or describe without sensitive identifiers].

## Local backend initialization

Set STATE_SA to the actual account name locally, then run:
terraform -chdir=terraform/environments/dev init \
  -backend-config="storage_account_name=$STATE_SA" \
  -backend-config="use_cli=true"

Bootstrap resources remain outside the workload Terraform lifecycle.
Do not commit state, keys, tokens, personal emails or raw Azure IDs.
