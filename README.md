 Execute Terraform Environment Destroy.

# Environment Variables

This Action uses the Cloudify Profile environment variables described in the official
Cloudify documentation (see [More Information](#more-information) below).

# Inputs

(Certain commonly-used inputs are documented in our official website; see [More Information](#more-information) below)

## Notes

* this action handles environment name and labels collision, and it will handle that by passing [environment-id]
* it will check if the environment exists or not [ if it doesn't exist it will not do anything ] and if it exists it will trigger terraform_destroy then delete the environment

# Example

```yaml
jobs:
  test_job:
    steps:
      - name: Delete terraform environment
        uses: cloudify-cosmo/terraform-destroy-action@v1.2
        with:
          environment-name: "test-$GITHUB_RUN_ID"
          labels: some_label:label_value,yet_another_label:some_value
```

# More Information

Refer to [Cloudify CI/CD Integration](https://docs.cloudify.co/latest/working_with/integration/) for additional information about
Cloudify's integration with CI/CD tools.
