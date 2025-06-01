# AWS Amplify CLI Reference for React TypeScript

A comprehensive reference guide for AWS Amplify CLI commands when working with React TypeScript applications.

## Installation & Setup

### Install Amplify CLI globally
```bash
npm install -g @aws-amplify/cli
```

### Configure Amplify with AWS credentials
```bash
amplify configure
```

### Initialize new Amplify project
```bash
amplify init
```

### Create new React TypeScript app with Amplify
```bash
npx create-react-app my-app --template typescript
cd my-app
amplify init
```

## Project Management

### Check Amplify status
```bash
amplify status
```

### View current environment
```bash
amplify env list
```

### Create new environment
```bash
amplify env add
```

### Switch between environments
```bash
amplify env checkout <env-name>
```

### Remove environment
```bash
amplify env remove <env-name>
```

## Authentication

### Add authentication service
```bash
amplify add auth
```

### Update authentication configuration
```bash
amplify update auth
```

### Remove authentication
```bash
amplify remove auth
```

## API & GraphQL

### Add GraphQL API
```bash
amplify add api
# Select GraphQL, then configure schema
```

### Add REST API
```bash
amplify add api
# Select REST, then configure endpoints
```

### Update API
```bash
amplify update api
```

### Generate GraphQL statements (queries, mutations, subscriptions)
```bash
amplify codegen
```

### Add GraphQL codegen for TypeScript
```bash
amplify add codegen
```

### Push schema changes and generate types
```bash
amplify push --codegen
```

## Storage

### Add S3 storage
```bash
amplify add storage
```

### Update storage configuration
```bash
amplify update storage
```

## Hosting

### Add hosting (S3 + CloudFront)
```bash
amplify add hosting
```

### Add hosting (Amplify Console)
```bash
amplify add hosting
# Select Amplify Console
```

## Functions (Lambda)

### Add Lambda function
```bash
amplify add function
```

### Update function
```bash
amplify update function
```

### Invoke function locally
```bash
amplify function invoke <function-name>
```

## Analytics

### Add analytics (Pinpoint)
```bash
amplify add analytics
```

## Notifications

### Add push notifications
```bash
amplify add notifications
```

## Deployment & Building

### Deploy all changes to cloud
```bash
amplify push
```

### Deploy with codegen for TypeScript
```bash
amplify push --codegen
```

### Build and test locally
```bash
amplify serve
```

### Publish to hosting
```bash
amplify publish
```

### Deploy specific category
```bash
amplify push <category>
# Example: amplify push auth
```

## Development & Testing

### Mock API and functions locally
```bash
amplify mock
```

### Mock specific service
```bash
amplify mock api
amplify mock function
```

### Start local development server
```bash
npm start
# or
yarn start
```

## TypeScript Specific

### Install Amplify libraries for React
```bash
npm install aws-amplify @aws-amplify/ui-react
```

### Install TypeScript types
```bash
npm install --save-dev @types/node
```

### Generate TypeScript types from GraphQL schema
```bash
amplify codegen add --apiId <api-id>
amplify codegen
```

### Configure codegen for TypeScript
```bash
# Edit amplify/.config/project-config.json
{
  "frontend": "javascript",
  "framework": "react",
  "config": {
    "SourceDir": "src",
    "DistributionDir": "build",
    "BuildCommand": "npm run-script build",
    "StartCommand": "npm run-script start"
  }
}
```

## Troubleshooting & Utilities

### Pull existing Amplify project
```bash
amplify pull
```

### Pull with app ID (from Amplify Console)
```bash
amplify pull --appId <app-id> --envName <env-name>
```

### Delete entire Amplify project
```bash
amplify delete
```

### View Amplify console
```bash
amplify console
```

### View specific service console
```bash
amplify console auth
amplify console api
amplify console hosting
```

### Export Amplify configuration
```bash
amplify export
```

### Import existing AWS resources
```bash
amplify import <category>
```

### Override generated resources
```bash
amplify override <category>
```

## Common File Locations

### Key configuration files:
- `amplify/` - Amplify configuration directory
- `src/aws-exports.js` - Auto-generated Amplify configuration
- `src/graphql/` - Generated GraphQL operations
- `src/API.ts` - Generated TypeScript types for GraphQL
- `amplify/backend/` - Backend resource definitions

### Configure Amplify in React app (src/index.tsx):
```typescript
import { Amplify } from 'aws-amplify';
import awsExports from './aws-exports';

Amplify.configure(awsExports);
```

## Useful Flags

### Common flags for amplify push:
```bash
--yes, -y          # Skip confirmation prompts
--force, -f        # Force push without confirmation
--codegen          # Generate code after push
--minify           # Minify GraphQL schema
```

### Environment-specific commands:
```bash
--envName <name>   # Specify environment name
--profile <name>   # Use specific AWS profile
```

## Best Practices

1. **Always run `amplify status`** before pushing changes
2. **Use environment branches** for different stages (dev, staging, prod)
3. **Commit amplify folder** to version control (except sensitive files)
4. **Generate TypeScript types** after schema changes with `amplify codegen`
5. **Test locally** with `amplify mock` before pushing
6. **Use `amplify pull`** when working in teams to sync changes

## Contributing

Feel free to contribute additional commands or improvements to this reference guide.

## Resources

- [AWS Amplify Documentation](https://docs.amplify.aws/)
- [Amplify CLI Documentation](https://docs.amplify.aws/cli/)
- [Amplify React Documentation](https://docs.amplify.aws/lib/q/platform/js/)
- [GraphQL Code Generator](https://www.graphql-code-generator.com/)