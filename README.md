# DyNote website

The landing page and privacy policy for the DyNote browser extension. This is a separate repository, included in the extension repository as the `website` Git submodule.

## Structure

- `dist/index.html`: landing page.
- `dist/privacy/index.html`: privacy policy, available at `/privacy/`.
- `dist/assets/`: local styles and product assets.
- `.openai/hosting.json`: Sites project identity and static output configuration.

The authored `dist` files are tracked source. There is no framework build, package installation, backend, analytics, form submission, or website storage.

## Local preview

```sh
python3 -m http.server 4187 --bind 127.0.0.1 --directory dist
```

Open `http://127.0.0.1:4187/` and `http://127.0.0.1:4187/privacy/`.

## Update the submodule

From the extension repository, initialize a fresh checkout with `git submodule update --init --recursive`. Make and commit website changes inside `website`, push that repository, then commit the updated `website` pointer in the extension repository.

The GitHub source repository is private. Cloning it requires access to `0xdavid7/dynote-site`. Source visibility is independent of whether the website is publicly accessible.

## Chrome Web Store release

Before using this site in a public listing:

1. Confirm the publisher name and a public support contact in the privacy page.
2. Publish the website with public access and verify that `/privacy/` is available without signing in.
3. Enter the homepage and privacy-policy URLs in the Chrome Web Store Developer Dashboard. Review its privacy disclosures against the policy and the extension's actual behavior.
4. Replace the clearly marked coming-soon store status with the real Chrome Web Store listing URL after that listing is available.

The website does not submit, publish, or guarantee approval of the extension. Keep its privacy policy current when the extension's data practices change.

Official references: [Chrome user data FAQ](https://developer.chrome.com/docs/webstore/program-policies/user-data-faq), [Privacy dashboard](https://developer.chrome.com/docs/webstore/cws-dashboard-privacy/).
