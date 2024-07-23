## What is this?
This is a collection of tools (mostly aliases) for working with [terragrunt](https://terragrunt.gruntwork.io/).
## How to use?
Just copy `terragrunt.zsh` file to your zsh custom folder (usually `$ZSH/custom`) and reload terminal.
## Requirements
- [ripgrep](https://github.com/BurntSushi/ripgrep) needs to be installed
- [fd](https://github.com/sharkdp/fd) needs to be installed
## Environment variables
- `TERRAFORM_MODULES_PATH` must point to your current terraform modules root directory.
## Functions
The `_tgts` functions extracts the subdirectories defined in the `source` variable in the current `terragrunt.hcl` file and executes `terragrunt ACTION --terragrunt-source $TERRAFORM_MODULES_PATH/source`. Take for example the following `terragrunt.hcl` file:
```bash
include "root" {
  path = find_in_parent_folders()
  expose = true
}

terraform {
  source = "${include.root.locals.source_base_url}/sqs-queue?ref=v0.0.1"
}

inputs = {}
```
Then for example the call `_tgas apply` will execute
```bash
terragrunt apply --terragrunt-source $TERRAFORM_MODULES_PATH/sqs-queue
```

## Aliases
| Alias     | Command                   |
| --------- | ------------------------- |
| `tg`      | `terragrunt`              |
| `tga`     | `terragrunt apply`        |
| `tgp`     | `terragrunt plan`         |
| `tgd`     | `terragrunt destroy`      |
| `tgas`    | `_tgts apply`                                                                                                                     |
| `tgps`    | `_tgts plan`                                                                                                                      |
| `tgds`    | `_tgts destroy`                                                                                                                   |
| `tgis`    | `_tgts import`                                                                                                                    |
| `tgsps`   | `_tgts state push`                                                                                                                |
| `tgaall`  | `terragrunt run-all apply --terragrunt-non-interactive --terragrunt-parallelism 10`                                               |
| `tgpall`  | `terragrunt run-all plan --terragrunt-non-interactive --terragrunt-parallelism 10`                                                |
| `tgdall`  | `terragrunt run-all destroy --terragrunt-non-interactive --terragrunt-parallelism 10`                                             |
| `tgasall` | `terragrunt run-all apply --terragrunt-non-interactive --terragrunt-parallelism 10 --terragrunt-source $TERRAFORM_MODULES_PATH`   |
| `tgpsall` | `terragrunt run-all plan --terragrunt-non-interactive --terragrunt-parallelism 10 --terragrunt-source $TERRAFORM_MODULES_PATH`    |
| `tgdsall` | `terragrunt run-all destroy --terragrunt-non-interactive --terragrunt-parallelism 10 --terragrunt-source $TERRAFORM_MODULES_PATH` |
| `clearTerragruntCache` | `fd -t d -H -I .terragrunt-cache -X rm -rf`                                                                          |
