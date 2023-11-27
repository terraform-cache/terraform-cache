# Terraform Cache

This action allows caching [Terraform](https://www.terraform.io) providers to improve workflow execution time.

[![LICENSE](https://img.shields.io/github/license/terraform-cache/terraform-cache?color=blue)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/terraform-cache/terraform-cache?style=social)](https://github.com/jongwooo/terraform-cache)

## Usage

### Pre-requisites

Create a workflow `.yml` file in your repositories `.github/workflows` directory. For more information, reference the GitHub Help Documentation for [Creating a workflow file](https://help.github.com/en/articles/configuring-a-workflow#creating-a-workflow-file).

### Cache Details

This action currently caches the following directories:

- `$HOME/.terraform.d/plugin-cache` (Path where the providers will be installed)

### Example workflow

```yaml
- uses: actions/checkout@v3

- name: Setup Terraform
  uses: hashicorp/setup-terraform@v2
  with:
    terraform_version: 1.4.6

- uses: terraform-cache/terraform-cache@v1

- name: Init
  run: |
    terraform init
```

## Contributing

Check out [Contributing guide](.github/CONTRIBUTING.md) for ideas on contributing and setup steps for getting our repositories up.

## License

Licensed under the [MIT License](LICENSE).
