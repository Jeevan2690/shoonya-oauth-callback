# Shoonya OAuth Callback Page

This folder is ready to publish on GitHub Pages as a simple Shoonya OAuth callback site.

## What it does

- Receives the browser redirect from Shoonya OAuth
- Reads the `code` query parameter from the redirect URL
- Shows the full redirect URL and all query parameters
- Lets you copy the code into the tester or bot

## Recommended GitHub repository name

Use a repository name like:

`shoonya-oauth-callback`

## Recommended GitHub Pages URL

If your GitHub username is `YOUR_GITHUB_USERNAME` and your repo is `shoonya-oauth-callback`,
the page URL will normally be:

`https://YOUR_GITHUB_USERNAME.github.io/shoonya-oauth-callback/`

That full URL is the value you should try in the Shoonya API Key `URL` field.

## Publish Steps

1. Create a new public GitHub repository.
2. Upload the files from this folder into the repository root:
   - `index.html`
   - `.nojekyll`
   - `README.md`
3. In GitHub, open:
   - `Settings`
   - `Pages`
4. Under `Build and deployment`:
   - `Source` = `Deploy from a branch`
   - `Branch` = `main`
   - `Folder` = `/ (root)`
5. Save.
6. Wait for GitHub Pages to publish.
7. Open the GitHub Pages URL and confirm the page loads.
8. Put that exact GitHub Pages URL into Shoonya API Key `URL`.

## After Shoonya redirects here

When Shoonya redirects successfully, this page should show a `code`.

Then run:

```powershell
python shoonya_oauth_connectivity_tester.py --code YOUR_CODE
```

## Important

- GitHub Pages URL is public HTTPS, which is why it is more likely to pass Shoonya URL validation than localhost.
- Do not use someone else’s callback URL.
- Keep using your own `Client Id` and `Secret Code`.
