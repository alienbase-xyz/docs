# Contributing to Alien Base Documentation

Thank you for your interest in contributing to the Alien Base documentation! This guide will help you get started with contributing to our documentation repository.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Getting Started](#getting-started)
- [Documentation Standards](#documentation-standards)
- [Submission Guidelines](#submission-guidelines)
- [Review Process](#review-process)
- [Community](#community)

## Code of Conduct

This project adheres to the Contributor Covenant [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior to the team via Discord.

## How Can I Contribute?

### Reporting Issues

If you find errors, outdated information, or areas that need improvement:

1. Check if the issue already exists in [GitHub Issues](https://github.com/solidworkssa/docs/issues)
2. If not, create a new issue using the appropriate template
3. Provide as much detail as possible:
   - What page or section has the issue
   - What is incorrect or unclear
   - What you expected to see
   - Screenshots if applicable

### Suggesting Enhancements

We welcome suggestions for improving the documentation:

1. Open a new issue with the "Documentation Enhancement" template
2. Describe your suggestion clearly
3. Explain why this enhancement would be useful
4. Provide examples if possible

### Contributing Content

You can contribute by:

- Fixing typos and grammatical errors
- Updating outdated information
- Adding missing documentation
- Improving clarity and readability
- Adding code examples
- Creating tutorials
- Translating content

## Getting Started

### Prerequisites

- Git installed on your machine
- GitHub account
- Text editor (VS Code recommended)
- Basic knowledge of Markdown

### Local Setup

1. **Fork the repository**
   ```bash
   # Click the "Fork" button on GitHub
   ```

2. **Clone your fork**
   ```bash
   git clone https://github.com/YOUR_USERNAME/docs.git
   cd docs
   ```

3. **Add upstream remote**
   ```bash
   git remote add upstream https://github.com/solidworkssa/docs.git
   ```

4. **Create a branch**
   ```bash
   git checkout -b fix/update-contract-addresses
   # or
   git checkout -b docs/add-staking-guide
   ```

### Branch Naming Convention

Use descriptive branch names with prefixes:

- `fix/` - Bug fixes or corrections
- `docs/` - New documentation or major updates
- `update/` - Updates to existing content
- `refactor/` - Restructuring without content changes

Examples:
- `fix/broken-links-in-readme`
- `docs/add-api-reference`
- `update/token-emission-schedule`

## Documentation Standards

### Writing Style

**Tone and Voice:**
- Use clear, concise language
- Write in second person ("you") when addressing users
- Be friendly but professional
- Avoid jargon; explain technical terms
- Use active voice

**Formatting:**
- Use sentence case for headings
- Keep paragraphs short (3-4 sentences)
- Use bullet points for lists
- Include code examples where relevant
- Add visual aids (screenshots, diagrams) when helpful

### Markdown Guidelines

**Headings:**
```markdown
# H1 - Page Title (one per page)
## H2 - Main Sections
### H3 - Subsections
#### H4 - Minor Subsections
```

**Links:**
```markdown
[Link text](https://example.com) - External links
[Link text](../path/to/file.md) - Internal links
```

**Code Blocks:**
````markdown
```javascript
// Always specify the language
const example = "code";
```
````

**Images:**
```markdown
![Descriptive alt text](path/to/image.png)
```

**Tables:**
```markdown
| Column 1 | Column 2 |
|----------|----------|
| Data 1   | Data 2   |
```

### File Organization

**File Naming:**
- Use lowercase with hyphens: `token-generator.md`
- Be descriptive: `how-to-stake-alb.md`
- Avoid special characters

**Directory Structure:**
```
docs/
├── getting-started/
├── user-guides/
├── developer/
├── governance/
├── security/
└── reference/
```

### Content Requirements

**Every documentation page should include:**

1. **Frontmatter** (for GitBook)
   ```markdown
   ---
   description: Brief description of the page content
   ---
   ```

2. **Title** (H1)
   ```markdown
   # Page Title
   ```

3. **Introduction**
   - Brief overview of the topic
   - What the reader will learn

4. **Main Content**
   - Organized with clear headings
   - Step-by-step instructions where applicable
   - Code examples with explanations

5. **Related Links** (optional)
   - Links to related documentation
   - External resources

### Code Examples

**Best Practices:**
- Provide complete, working examples
- Include necessary imports and setup
- Add comments to explain complex parts
- Test all code examples before submitting
- Use realistic variable names

**Example:**
```javascript
// Import required libraries
const { ethers } = require('ethers');

// Connect to Base network
const provider = new ethers.providers.JsonRpcProvider('https://mainnet.base.org');

// Get ALB token contract
const albAddress = '0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4';
const albAbi = [...]; // ABI here
const albContract = new ethers.Contract(albAddress, albAbi, provider);

// Get token balance
async function getBalance(address) {
  const balance = await albContract.balanceOf(address);
  return ethers.utils.formatEther(balance);
}
```

### Screenshots and Images

**Guidelines:**
- Use PNG format for screenshots
- Optimize images (keep under 500KB)
- Use descriptive filenames: `staking-dashboard-overview.png`
- Store in `.gitbook/assets/` directory
- Always include alt text
- Highlight important areas with arrows or boxes
- Use consistent styling

**Alt Text Examples:**
```markdown
Good: ![Alien Base staking dashboard showing esALB balance and APR](../assets/staking-dashboard.png)
Bad: ![Screenshot](../assets/img1.png)
```

## Submission Guidelines

### Before Submitting

**Checklist:**
- [ ] Content is accurate and up-to-date
- [ ] All links work correctly
- [ ] Code examples are tested
- [ ] Images have descriptive alt text
- [ ] Spelling and grammar are correct
- [ ] Markdown is properly formatted
- [ ] Changes follow the style guide
- [ ] Commit messages are clear

### Making Changes

1. **Make your changes**
   - Edit files in your branch
   - Follow documentation standards
   - Test all examples and links

2. **Commit your changes**
   ```bash
   git add .
   git commit -m "docs: add staking tutorial for esALB"
   ```

   **Commit Message Format:**
   ```
   <type>: <subject>

   <body (optional)>
   ```

   **Types:**
   - `docs:` - Documentation changes
   - `fix:` - Bug fixes or corrections
   - `update:` - Updates to existing content
   - `refactor:` - Restructuring
   - `chore:` - Maintenance tasks

   **Examples:**
   ```
   docs: add API reference for swap functions
   fix: correct contract address for esALB
   update: refresh token emission schedule for 2026
   ```

3. **Push to your fork**
   ```bash
   git push origin your-branch-name
   ```

4. **Create a Pull Request**
   - Go to your fork on GitHub
   - Click "New Pull Request"
   - Fill out the PR template completely
   - Link any related issues

### Pull Request Guidelines

**PR Title Format:**
```
[Type] Brief description
```

Examples:
- `[Docs] Add developer integration guide`
- `[Fix] Update outdated contract addresses`
- `[Update] Refresh roadmap for 2026`

**PR Description Should Include:**
- Summary of changes
- Motivation for changes
- Any breaking changes
- Screenshots (for UI changes)
- Checklist completion

**PR Template:**
```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix (typo, broken link, incorrect info)
- [ ] New documentation
- [ ] Update to existing documentation
- [ ] Refactoring/reorganization

## Checklist
- [ ] I have read the CONTRIBUTING guidelines
- [ ] My changes follow the documentation standards
- [ ] I have tested all code examples
- [ ] I have checked all links
- [ ] I have added/updated images with alt text
- [ ] My commit messages are clear and descriptive

## Related Issues
Closes #123
```

## Review Process

### What to Expect

1. **Automated Checks**
   - Link validation
   - Markdown linting
   - Spell checking
   - These must pass before review

2. **Maintainer Review**
   - A maintainer will review within 48 hours
   - They may request changes
   - Be responsive to feedback

3. **Approval and Merge**
   - Once approved, your PR will be merged
   - Changes will be deployed to the documentation site
   - You'll be added to the contributors list

### Review Criteria

Reviewers will check:
- **Accuracy** - Is the information correct?
- **Clarity** - Is it easy to understand?
- **Completeness** - Does it cover the topic adequately?
- **Style** - Does it follow our guidelines?
- **Technical** - Do code examples work?

### Addressing Feedback

When reviewers request changes:

1. **Respond to comments**
   - Ask questions if unclear
   - Explain your reasoning if you disagree

2. **Make requested changes**
   ```bash
   # Make changes in your branch
   git add .
   git commit -m "address review feedback"
   git push origin your-branch-name
   ```

3. **Request re-review**
   - Comment on the PR when ready
   - Tag the reviewer if needed

## Style Guide Quick Reference

### Do's

[YES] Use clear, simple language  
[YES] Include code examples  
[YES] Add screenshots for UI features  
[YES] Link to related documentation  
[YES] Test all examples  
[YES] Use descriptive alt text  
[YES] Keep content up-to-date  
[YES] Be concise but complete  

### Don'ts

[NO] Use jargon without explanation  
[NO] Include untested code  
[NO] Leave broken links  
[NO] Use vague headings  
[NO] Include outdated information  
[NO] Forget alt text on images  
[NO] Make assumptions about user knowledge  
[NO] Use first person ("I", "we")  

## Community

### Getting Help

**Questions about contributing?**
- Open a [GitHub Discussion](https://github.com/solidworkssa/docs/discussions)
- Ask in the [Discord #documentation channel](https://discord.gg/alienbase)
- Tag `@docs-team` for documentation questions

**Need technical help?**
- Check existing documentation first
- Search GitHub Issues
- Ask in Discord #support channel

### Recognition

We value all contributions! Contributors will be:
- Listed in CONTRIBUTORS.md
- Mentioned in release notes
- Recognized in community channels
- Eligible for contributor rewards (if applicable)

### Documentation Office Hours

Join us for weekly documentation office hours:
- **When:** Every Wednesday, 3 PM UTC
- **Where:** Discord voice channel
- **What:** Ask questions, get help, discuss improvements

## Additional Resources

### Documentation Tools

**Recommended Tools:**
- [VS Code](https://code.visualstudio.com/) - Code editor
- [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one) - VS Code extension
- [Grammarly](https://www.grammarly.com/) - Grammar checking
- [Carbon](https://carbon.now.sh/) - Beautiful code screenshots

### Learning Resources

**Markdown:**
- [Markdown Guide](https://www.markdownguide.org/)
- [GitHub Markdown](https://guides.github.com/features/mastering-markdown/)

**Technical Writing:**
- [Google Developer Documentation Style Guide](https://developers.google.com/style)
- [Write the Docs](https://www.writethedocs.org/)

**DeFi Concepts:**
- [Ethereum.org Documentation](https://ethereum.org/en/developers/docs/)
- [DeFi Glossary](https://ethereum.org/en/defi/)

## Questions?

If you have questions not covered in this guide:
- Open a [GitHub Discussion](https://github.com/solidworkssa/docs/discussions)
- Ask in [Discord](https://discord.gg/alienbase)
- Email: docs@alienbase.xyz

---

Thank you for contributing to Alien Base documentation! Your efforts help make DeFi more accessible to everyone.
