## What is this?
This is a collection of tools (mostly aliases) for working with [terragrunt](https://terragrunt.gruntwork.io/).
## Aliases
| Alias     | Command                   |
| --------- | ------------------------- |
| `tg`      | `terragrunt`              |
| `tga`     | `terragrunt apply`        |
| `tgp`     | `terragrunt plan`         |
| `tgd`     | `terragrunt destroy`      |      
| `tgas`    | `terragrunt apply --terragrunt-source /path/to/terraform/module`                                                                  |
| `tgps`    | `terragrunt plan --terragrunt-source /path/to/terraform/module`                                                                   |
| `tgds`    | `terragrunt destroy --terragrunt-source /path/to/terraform/module`                                                                |
| `tgis`    | `terragrunt import $1 $2 --terragrunt-source /path/to/terraform/module`                                                           |
| `tgsps`   | `terragrunt state push --terragrunt-source /path/to/terraform/module /path/to/statefile`                                          |
| `tgaall`  | `terragrunt run-all apply --terragrunt-non-interactive --terragrunt-parallelism 10`                                               |
| `tgpall`  | `terragrunt run-all plan --terragrunt-non-interactive --terragrunt-parallelism 10`                                                |
| `tgdall`  | `terragrunt run-all destroy --terragrunt-non-interactive --terragrunt-parallelism 10`  `                                          |
| `tgasall` | `terragrunt run-all apply --terragrunt-non-interactive --terragrunt-parallelism 10 --terragrunt-source $TERRAFORM_MODULES_PATH`   |
| `tgpsall` | `terragrunt run-all plan --terragrunt-non-interactive --terragrunt-parallelism 10 --terragrunt-source $TERRAFORM_MODULES_PATH`    |
| `tgdsall` | `terragrunt run-all destroy --terragrunt-non-interactive --terragrunt-parallelism 10 --terragrunt-source $TERRAFORM_MODULES_PATH` | 
## Dependencies
- [ripgrep](https://github.com/BurntSushi/ripgrep)
