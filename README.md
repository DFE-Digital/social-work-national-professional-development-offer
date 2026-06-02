# Social Work National Professional Development Offer

The repository will be used to store project source code for the social work national professional development offer

## Getting started

### Prerequisites

### Setup

To set up the development environment, restore the required .NET tools:

```bash
dotnet tool restore
dotnet husky install
```

This will install the tools specified in `.config/dotnet-tools.json`, including Husky.Net for pre-commit hooks to ensure consistent code style.
Commits also run a GitLeaks pre-commit scan via Husky. The hook will use a pinned GitLeaks `8.30.0` binary and download it into a user cache directory if it is not already available on your machine. The auto-install path currently supports macOS and Linux on x64 and arm64, plus Windows on x64.

If you need to refresh the repository baseline for tracked fixtures, run:

```bash
dotnet pwsh ./scripts/security/run-gitleaks.ps1 -Mode Baseline
```

If GitLeaks blocks a commit and you are certain the finding is expected, update `.gitleaks.toml` or regenerate `.gitleaks.baseline.json`. For urgent one-off commits only, you can bypass the local scan with:

```bash
SW_SKIP_GITLEAKS=1 git commit
```

Also, ensure the .NET self-signed certificate is installed (to enable HTTPS use locally):

```bash
dotnet dev-certs https --trust
```

If encountering problems with the .NET dev certificate, run `dotnet dev-certs https --clean` first, then run `dotnet dev-certs https --trust`.
