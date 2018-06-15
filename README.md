# pre-commit-terraform hook

Several [pre-commit](http://pre-commit.com/) hooks to keep Terraform configurations (both `*.tf` and `*.tfvars`) in a good shape:
* `terraform_docs` - Inserts input and output documentation into `README.md`.

## Notes about hooks

1. `terraform_docs` We end up with these single byte READMEs, when we run terraform-docs in folders that have no Terraform inputs or outputs. We could be more intelligent about not running terraform-docs in these folders, but for a quick fix, simply deleting them after they are created gets the job done. If you have any alternate implementations please reach out and share them!

## Example

`.pre-commit-config.yaml`:

```yaml
- repo: git://github.com/mirodanov/pre-commit-terraform-docs
  rev: v0.0.1
  hooks:
    - id: terraform_docs
```

Enjoy the documented code!
