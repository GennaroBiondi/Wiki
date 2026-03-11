# `systemctl`
`systemctl` is a command used to interact with `systemd`, the init process.

## Services
Services are programs that `systemd` manages. Here's how to interact with them:

| Subcommand                       | Action                                 | Notes                           |
| -------------------------------- | -------------------------------------- | ------------------------------- |
| `enable`                         | Enable a service to start at boot      | Affects next boot               |
| `disable`                        | Disable a service to not start at boot | Affects next boot               |
| `start`                          | Start a service immediately            | Runtime only                    |
| `stop`                           | Stop a service immediately             | Runtime only                    |
| `restart`                        | Restart a service                      | Runtime only                    |
| `status`                         | Check the status of a service          | Shows active state and logs     |
| `list-units --type=service`      | List all currently running services    | Runtime snapshot                |
| `list-unit-files --type=service` | List all services and their state      | Shows enabled/disabled/static   |
| `mask`                           | Prevent a service from starting        | Blocks manual & automatic start |
| `unmask`                         | Allow a masked service to start        | Reverts `mask`                  |

## System
`systemd` can also control the system:

| Subcommand | Action                | Notes                |
| ---------- | --------------------- | ------------------- |
| `poweroff` | Shut down the computer | Immediate           |
| `reboot`   | Reboot the computer    | Immediate           |
| `suspend`  | Suspend the computer   | Saves state to RAM  |
