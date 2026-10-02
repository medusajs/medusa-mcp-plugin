# Medusa

Work with your Medusa Cloud account from Claude in plain language. This plugin connects Claude to Medusa's hosted MCP server, so Claude can read data from the stores in your Medusa Cloud organization, such as orders, products, customers, and custom API routes, and answer questions about building with Medusa from the official Medusa documentation.

## What it does

The plugin bundles one remote MCP server, `medusa`, at `https://cloud.medusajs.com/mcp`. It contains no skills, commands, agents, hooks, scripts, or local executables, and it installs no packages.

Through that server, Claude can list the store environments you connected, retrieve data from your store like products and orders, list your publishable API keys, search the Medusa documentation, and more.

## Get started

For requirements and connection steps, see [Medusa MCP](https://docs.medusajs.com/cloud/medusa-mcp) in the Medusa Cloud docs.

## What it can and can't do

- It only reads. It can't create, change, or delete orders, products, customers, or any other store data, and it can't change your Medusa Cloud projects, environments, or settings.
- It acts with your own permissions, so Claude sees only what your Medusa admin user can see.
- It reaches only the environments you picked when you connected. To change them, disconnect and connect again.
- Sending feedback to Medusa is the only action that submits anything, and Claude does it only when you ask.

## Data

Every request from this plugin goes to `cloud.medusajs.com`. Medusa Cloud then calls your own Medusa store's Admin or Store API, or searches the Medusa documentation, and returns the result to Claude. The plugin sends nothing to any other destination, and it doesn't read credentials or files from your machine. Feedback you choose to submit goes to the Medusa team.

See Medusa's [privacy policy](https://medusajs.com/privacy-policy) and [terms of service](https://medusajs.com/terms-of-service).

## Example prompts

- "Which Medusa stores do I have connected?"
- "Show me the 5 most recent orders in my store, with each order's total and status."
- "What products are available to shoppers in my B2B sales channel?"
- "How do I add a custom field to products in Medusa?"

## Troubleshooting

- **"Commerce MCP is not enabled for your account"**: Medusa's MCP access isn't turned on for your Medusa Cloud organization yet. [Contact Medusa](https://medusajs.com/contact) to enable it, then connect again.
- **Store MFA re-authentication**: if a request fails because your store requires MFA, open the re-authentication link Claude shows, confirm MFA, and retry the request.
- **Several environments connected**: when more than one environment is connected, Claude asks which one to use. Name the store and environment in your prompt, for example "in my production store", to skip the question.

## Support

For help, go to [medusajs.com/contact](https://medusajs.com/contact).

## License

[MIT](LICENSE)
