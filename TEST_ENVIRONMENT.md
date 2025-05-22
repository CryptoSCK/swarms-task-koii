# Test Environment Setup and Prerequisites

## Overview
This document provides comprehensive guidelines for setting up the test environment across our project's components, including Node, Coordinator, and Orca Agent.

## Prerequisites

### General Requirements
- Node.js (version 18.x or later)
- Yarn or npm
- Python 3.8+
- Docker (optional, but recommended)
- Git

### System Dependencies
1. Install required package managers:
```bash
# Install Yarn
npm install -g yarn

# Install Python dependencies
pip install -r node/orca-agent/requirements.txt
```

## Environment Configuration

### Node Component
1. Navigate to the node directory:
```bash
cd node
```

2. Create environment file:
```bash
cp .env.example .env
```

3. Configure environment variables:
- `NODE_ENV`: Set to `development` or `production`
- `TASK_ID`: Your specific task identifier
- `WALLET_PRIVATE_KEY`: Your wallet private key

### Coordinator Component
1. Navigate to the coordinator/middle-server directory:
```bash
cd coordinator/middle-server
```

2. Create environment file:
```bash
cp .env.example .env
```

3. Configure environment variables:
- `DATABASE_URL`: Connection string for your database
- `SLACK_WEBHOOK`: Slack integration webhook (optional)
- `GITHUB_TOKEN`: GitHub authentication token

### Orca Agent
1. Navigate to the node/orca-agent directory:
```bash
cd node/orca-agent
```

2. Create environment file:
```bash
cp .env.example .env
```

3. Configure environment variables:
- `API_KEY`: Your API key
- `LOGGING_LEVEL`: Set logging verbosity
- `WORKER_ID`: Unique worker identification

## Running Tests

### Node Tests
```bash
cd node
yarn test
```

### Coordinator Tests
```bash
cd coordinator/middle-server
yarn test
```

### Orca Agent Tests
```bash
cd node/orca-agent
python -m pytest tests/
```

## Troubleshooting

### Common Issues
- Ensure all dependencies are installed
- Check environment variable configurations
- Verify network connectivity
- Review log files for specific error messages

### Debugging
- Use `yarn test:debug` for verbose test output
- Check `.env` files for correct configurations
- Validate package versions in `package.json`

## Best Practices
- Never commit sensitive information like private keys
- Use `.env.example` as a template
- Rotate credentials regularly
- Keep dependencies updated

## Contributing
When adding new tests or modifying the test environment:
1. Update this documentation
2. Ensure backward compatibility
3. Add comments explaining complex configurations

## Version
Last Updated: $(date +"%Y-%m-%d")
```