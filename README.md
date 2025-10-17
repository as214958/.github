# as214958 Organization

This organization provides shared infrastructure for collaborative projects.

## Shared Self-Hosted Runner

This organization hosts a self-hosted GitHub Actions runner that is available to all repositories within the organization. The runner allows you to execute workflows with custom configurations and potentially better performance than GitHub's hosted runners.

### Using the Shared Runner

To use the shared runner in your GitHub Actions workflows, specify the runner label in your workflow file:

```yaml
jobs:
  your-job:
    runs-on: self-hosted
    steps:
      - uses: actions/checkout@v4
      - name: Your build steps
        run: echo "Running on shared runner"
```

### Runner Labels

The shared runner has the following labels:
- `self-hosted` - Main label to target the shared runner
- `Linux` - Operating system (if applicable)
- `X64` - Architecture (if applicable)

### Workflow Templates

Pre-configured workflow templates are available in this repository's `workflow-templates/` directory. You can use these as starting points for your own workflows.

### Best Practices

1. **Be considerate**: The runner is shared among multiple users. Keep your workflows efficient.
2. **Clean up**: Ensure your workflows clean up after themselves (remove temporary files, stop processes).
3. **Resource usage**: Monitor your workflow's resource consumption.
4. **Security**: Don't expose sensitive information in logs or artifacts.

### Support

For issues or questions about the shared runner, please open an issue in this repository.