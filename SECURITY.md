# Security Policy

## Supported Versions

> ```mermaid
> ---
> title: Versions Status Flow
> ---
> flowchart LR
>   Unstable("Unstable")
>   Pre("Pre Release")
>   Release("Release")
>   LTS("Long Term Support")
>   Maintenance("Maintenance")
>   EOL("End Of Life")
>   Unstable --> Pre --> Release
>   subgraph Supported
>     Release -- Major = 0 --> Maintenance
>     Release -- Major > 0 --> LTS --> Maintenance
>   end
>   Maintenance --> EOL
> ```

| **Versions** | **Release Date** | **Long Term Support Date** | **End Of Life Date** |
|:-:|:-:|:-:|:-:|
| v2.X.X | 2024-01-15 | 2024-01-15 | *Unknown* |
| v1.X.X (For Non-NPM) | 2024-03-12 | 2024-03-12 | 2024-10-15 |
| v1.X.X (For NPM Only) | 2023-02-16 | 2023-03-08 | 2024-04-15 |

> **ℹ️ Note**
>
> - The date format is according to the specification ISO 8601.
> - Values in italic format are subject to change.
> - Versions which not in the list are also end of life.

## Report Vulnerabilities

You can report security vulnerabilities by [create security vulnerability report](https://github.com/hugoalh/hugoalh/blob/main/universal-guide/contributing.md#create-a-security-vulnerability-report).
