# Alter Documentation

![Alter Documentation Logo](/alter-documentation-logo.png)

This is the official documentation for [Alter](https://alterhq.com), a macOS AI assistant that lets you create custom Actions to automate tasks and integrate with your apps.

## About This Project

This documentation site is built on [Mintlify](https://mintlify.com). It contains:

- Getting started guides
- Action creation tutorials
- Custom Action reference
- How-to guides
- Common issues and troubleshooting

## Contributing

Contributors are very welcome. Community additions are encouraged as long as content is accurate, practical, and easy to verify.

AI-assisted writing is welcome, but it must be fact-checked and edited for clarity. Please avoid low-signal AI slop: submissions should be concise, digestible, and genuinely useful for the community. If you are contributing with an AI agent, use `ALTER.md` as the guideline source of truth before making changes.

### Commit Convention

Use [Conventional Commits](https://www.conventionalcommits.org/) for all commit messages.

Examples:

- `docs(guides): add url callbacks guide`
- `chore(ci): validate assets-doc mapping on pull requests`
- `fix(references): correct pricing faq fair-use wording`

## Development

Install the [Mintlify CLI](https://www.npmjs.com/package/mint) to preview your documentation changes locally:

```bash
npm i -g mint
```

Run the following command at the root of your documentation, where your `docs.json` is located:

```bash
mint dev
```

View your local preview at `http://localhost:3000`.

## Need help?

### Troubleshooting

- If your dev environment isn't running: Run `mint update` to ensure you have the most recent version of the CLI.
- If a page loads as a 404: Make sure you are running in a folder with a valid `docs.json`.
- Check for broken links: Run `mint broken-links`

### Resources
- [Alter website](https://alterhq.com)
- [Mintlify documentation](https://mintlify.com/docs)
- [Contributing guidelines](ALTER.md)
