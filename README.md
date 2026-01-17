# berkyswrapper

A ChatGPT-style interface wrapper built with pure HTML, CSS, and JavaScript.

## Deployment to Cloudflare Pages

This project is configured to automatically deploy to Cloudflare Pages when changes are pushed to the `main` branch.

### Setup Instructions

1. **Create a Cloudflare Pages project:**
   - Log in to your [Cloudflare Dashboard](https://dash.cloudflare.com/)
   - Go to "Workers & Pages" > "Pages"
   - Click "Create a project"
   - Connect your GitHub repository
   - Use these build settings:
     - Build command: (leave empty)
     - Build output directory: `/`
     - Root directory: `/`

2. **Configure GitHub Secrets:**
   
   Add the following secrets to your GitHub repository (Settings > Secrets and variables > Actions):
   
   - `CLOUDFLARE_API_TOKEN`: Your Cloudflare API Token
     - Create one at: https://dash.cloudflare.com/profile/api-tokens
     - Use the "Edit Cloudflare Workers" template or create a custom token with "Cloudflare Pages:Edit" permissions
   
   - `CLOUDFLARE_ACCOUNT_ID`: Your Cloudflare Account ID
     - Find it in your Cloudflare Dashboard URL or in the Pages project settings

3. **Manual Deployment (Optional):**
   
   You can also use Wrangler CLI for manual deployments:
   
   ```bash
   # Install Wrangler
   npm install -g wrangler
   
   # Login to Cloudflare
   wrangler login
   
   # Deploy to Pages
   wrangler pages deploy . --project-name=berkyswrapper
   ```

### Automatic Deployment

The GitHub Actions workflow (`.github/workflows/deploy.yml`) will automatically deploy your site to Cloudflare Pages when:
- Changes are pushed to the `main` branch
- The workflow is manually triggered from the Actions tab

## Local Development

Simply open `index.html` in your browser to test the interface locally.

## Features

- ChatGPT-style UI with dark theme
- Sidebar with chat history
- Responsive design
- Message input with auto-resize
- Example prompts
