# Gcloud
## bq command not found in gitbash on windows
use `bq.cmd` instead of `bq`
i.e `bq.cmd ls`

[I want to use the output of `gcloud` in a script, but the format changes. What should I do? - Stack Overflow](https://stackoverflow.com/questions/34600588/i-want-to-use-the-output-of-gcloud-in-a-script-but-the-format-changes-what-s)

## Python was not found; run without arguments to install from the Microsoft Store, or disable this shortcut from Settings > Manage App Execution Aliases.

need to check for the solution

# VPC
## Firewall rules
Default source range: When you omit a source specification in an ingress rule, Google Cloud uses the default source IPv4 address range **0.0.** **0.0/0** (any IPv4 address). The default value does not include IPv6 sources.

# DNS Suffix
GCP dns suffix can be any string, i.e "comp2"
This is used while creating the dns records in dns zones
existing dns zones can be checked under - GCP console -> cloud DNS

# Logs not available
Error: Logs are not showing.
Resolution: Check the logsync is enabled or not in logs explorer.