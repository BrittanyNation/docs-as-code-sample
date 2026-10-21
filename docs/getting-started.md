# Getting Started

This guide takes you from a clean machine to a running instance in about 10 minutes.

## Before you begin
- A machine with 4 GB of free memory
- Administrator (sudo) access
- An internet connection for the initial download

## Install
1. Download the installer for your operating system from the product download page.
2. Run the installer and accept the default install location.
3. Open a terminal and check the version:

   ```bash
   sampleproduct --version
   ```

## Verify
Run the built-in health check:

```bash
sampleproduct doctor
```

You should see `All checks passed`. If any check fails, the output names the failing component and the log file to inspect.

## Next steps
- Automate your first process with the [Workflow Automation Guide](workflow-automation-guide.md).
- Connect a production database with the [PostgreSQL Quickstart](postgresql-quickstart.md).
