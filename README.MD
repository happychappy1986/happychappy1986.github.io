James Champan Counselling

Built with [Jekyll](https://jekyllrb.com)

## Running Locally

To run this site locally, you'll need Ruby and Bundler installed.

1.  **Install dependencies:**

    ```bash
    bundle install
    ```

2.  **Run the server:**

    ```bash
    bundle exec jekyll serve
    ```

3.  **View the site:**

    Open your browser and go to `http://localhost:4000`.


DELETE WHEN DONE

# Netlify OAuth Setup for Decap CMS

Follow these steps to enable authentication for your CMS at https://happychappy1986.github.io/admin

## Step 1: Create Netlify Account

1. Go to https://netlify.com
2. Click "Sign up" and create a free account (you can sign up with GitHub)

## Step 2: Add Your Site to Netlify

1. Once logged in, click "Add new site" → "Import an existing project"
2. Choose "Deploy with GitHub"
3. Authorize Netlify to access your GitHub account
4. Select the repository: `happychappy1986/happychappy1986.github.io`
5. **Important**: Before clicking "Deploy", go to "Site settings"
6. Under "Build settings", you can leave everything as default (we won't actually use Netlify for hosting)
7. Click "Deploy site"

Note: Netlify will build and deploy your site, but you'll continue using GitHub Pages for the actual site. We're only using Netlify for the OAuth service.

## Step 3: Enable GitHub OAuth Provider

1. In your Netlify site dashboard, go to "Site settings"
2. Navigate to "Access control" → "OAuth" (in the sidebar)
3. Under "Authentication providers", click "Install provider"
4. Select "GitHub"
5. Follow the prompts to create a GitHub OAuth application:
   - GitHub will ask you to authorize Netlify
   - Netlify will automatically configure the OAuth app for you

That's it! The OAuth is now configured.

## Step 4: Push Changes and Test

1. Commit and push the updated `admin/config.yml` to GitHub:
   ```bash
   git add admin/config.yml
   git commit -m "Configure Netlify OAuth for CMS"
   git push origin main
   ```

2. Wait for GitHub Pages to rebuild (usually 1-2 minutes)

3. Visit https://happychappy1986.github.io/admin

4. Click "Login with GitHub"

5. You should be authenticated and able to edit your site!

## Step 5: Give Your Friend Access

To allow your friend to edit the site:

1. Go to your GitHub repository settings
2. Navigate to "Collaborators"
3. Add your friend's GitHub account as a collaborator
4. They'll need to accept the invitation
5. Once accepted, they can visit https://happychappy1986.github.io/admin and log in with their GitHub account

## Troubleshooting

**"Error: Failed to load config"**
- Make sure the changes are pushed to GitHub and Pages has rebuilt

**"Authentication error"**
- Verify OAuth is enabled in Netlify site settings
- Make sure your friend is a collaborator on the GitHub repo

**Still using local backend?**
- Check that `local_backend: true` is commented out in `admin/config.yml`

## Notes

- Your site will still be hosted on GitHub Pages at https://happychappy1986.github.io
- Netlify is only providing the OAuth authentication service
- All content changes are committed directly to your GitHub repository
- GitHub Pages automatically rebuilds when changes are made
