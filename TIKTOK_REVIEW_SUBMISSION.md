# TIGO Social Manager — TikTok Production Review Submission Kit

Last updated: 2026-11-03

## 1. Public URLs

Use the deployed GitHub Pages URLs below unless a verified custom domain is configured before submission:

- Website: https://pqthanh10qt-alt.github.io/tigo-social-manager/
- Privacy Policy: https://pqthanh10qt-alt.github.io/privacy/
- Terms of Service: https://pqthanh10qt-alt.github.io/terms/
- Support: https://pqthanh10qt-alt.github.io/support/
- Data Deletion: https://pqthanh10qt-alt.github.io/data-deletion/

The website uses the same `/logo.png` file for the visible brand mark and browser favicon so that the website identity is consistent with the app icon submitted to TikTok.

## 2. Basic information

**App name**

Tigo Social Manager

**Category**

Social Networking

**Description**

TIGO Social Manager is a social media management application developed by TigoSoft. It helps businesses and content creators organize media, schedule content, manage social channels, and connect authorized TikTok accounts to publish content through TikTok's official APIs.

## 3. Recommended TikTok products and scopes for this revision

Keep the review surface minimal.

### Login Kit

- `user.info.basic`

Purpose: identify the TikTok account that the user has explicitly authorized and show the authorized account's display information inside TIGO Social Manager.

### Content Posting API

Choose only the mode(s) that are already implemented and can be demonstrated end-to-end in Sandbox.

- `video.upload` — upload selected content to the authorized user's TikTok account as a draft for completion in TikTok.
- `video.publish` — direct posting, only if TIGO's current build fully implements and visibly demonstrates the creator-info/privacy/post confirmation flow required by TikTok.

Do not request `video.list`, profile stats, or other unused scopes in this revision.

## 4. App Review explanation — Login Kit

TIGO Social Manager uses TikTok Login Kit to let businesses and content creators securely connect their own TikTok accounts. The user starts the connection from the Channels section of TIGO Social Manager and is redirected to TikTok's official authorization screen. TIGO Social Manager never asks the user to provide a TikTok password.

After the user grants permission, TikTok returns an authorization code through the configured redirect flow. TIGO Social Manager uses the approved authorization to identify the connected account and display the authorized account information so the user can confirm which TikTok account is connected.

The requested `user.info.basic` scope is used only to display basic information for the TikTok account that the user explicitly authorized.

## 5. App Review explanation — Content Posting API / video.upload

Users of TIGO Social Manager organize their own media and content inside the application. When a user chooses to send a video to TikTok, the user explicitly selects the media and the authorized TikTok destination account before confirming the action.

For the `video.upload` flow, TIGO Social Manager sends the selected content through TikTok's Content Posting API to the authorized user's TikTok account as a draft. The user then continues the editing and posting flow in the TikTok app. TIGO Social Manager does not silently publish content without the user's action.

## 6. App Review explanation — Direct Post / video.publish

Include this section only if Direct Post is fully implemented in the review build.

Before posting, TIGO Social Manager retrieves and displays the publishing options required by TikTok for the authorized creator. The user selects the destination account, content, caption and available privacy settings and explicitly confirms the publishing action. TIGO Social Manager then uses TikTok's Content Posting API to submit the content to the authorized account and displays the resulting publishing status.

The `video.publish` permission is used only for content that the authenticated user explicitly chooses to publish to their own authorized TikTok account.

## 7. Revision note after previous rejection

This revision addresses the previous review feedback:

1. The public website has been replaced with a complete product website for TIGO Social Manager rather than a private/internal-use landing page.
2. The public website now clearly explains the product, target users, supported workflows, TikTok integration, support contact, privacy practices, and data deletion process.
3. Privacy Policy and Terms of Service are directly accessible from the product website and footer.
4. The website brand mark and browser favicon use the same TIGO Social Manager logo asset, aligning the public website identity with the submitted app icon.
5. The app description now reflects a public software product for businesses and creators rather than an internal tool for one shop.
6. TikTok browser automation / Local Bridge is not part of the production TikTok integration. TikTok connectivity is designed around official TikTok authorization and approved APIs.

## 8. Demo video script

For first-time production review, record the integration in TikTok Sandbox.

### Part A — public website (10–20 seconds)

1. Open the public TIGO Social Manager product website.
2. Show the product name and matching logo.
3. Scroll enough to show TikTok Integration.
4. Show that Privacy Policy and Terms of Service are visible and accessible.

### Part B — open TIGO Social Manager

1. Launch the Windows app.
2. Show the app name and main interface.
3. Open Channels & Groups.
4. Select TikTok / Connect.

### Part C — Login Kit

1. Start TikTok authorization.
2. Show TikTok's own authorization page.
3. Show the permissions being requested.
4. Approve the connection with a Sandbox/test account.
5. Return to TIGO Social Manager.
6. Show the connected account identity.

### Part D — Content Posting API

For `video.upload`:
1. Select a test video.
2. Select the connected TikTok account.
3. Confirm the upload action.
4. Show the successful result in TIGO.
5. Show the corresponding TikTok draft/inbox flow.

For `video.publish` (only if requested):
1. Select content.
2. Show the available creator/post settings.
3. Select caption/privacy options.
4. Explicitly confirm post.
5. Show publish status and the resulting post.

### Rules for the recording

- Show every selected TikTok product and every requested scope.
- Use the Sandbox environment for first-time review.
- Do not reveal Client Secret, access tokens, refresh tokens, cookies or DevTools.
- Do not demo browser scraping or TikTok Local Bridge.
- Keep the app interface and website domain consistent with the submitted configuration.

## 9. URL property verification checklist

Before submission, verify ownership of:
- Website/Desktop URL
- Privacy Policy URL
- Terms of Service URL
- Any upload URL/domain used by Content Posting API

Existing TikTok verification files in the repository must not be removed unless TikTok issues new verification files.

## 10. Final pre-submit checklist

- [ ] Production revision is Draft.
- [ ] App icon matches website logo/favicon.
- [ ] App name is Tigo Social Manager.
- [ ] Description no longer says internal/private jewelry-shop tool.
- [ ] Website is publicly accessible without login.
- [ ] Privacy Policy works.
- [ ] Terms of Service works.
- [ ] Support works.
- [ ] Data Deletion page works.
- [ ] Required URL properties are Verified.
- [ ] Redirect URI matches the implemented OAuth flow exactly.
- [ ] Only necessary products/scopes are selected.
- [ ] Sandbox Login Kit works end-to-end.
- [ ] Sandbox posting flow works end-to-end.
- [ ] Demo video shows all selected products/scopes.
- [ ] No secrets are visible in the demo.
- [ ] App Review explanations match actual behavior.
- [ ] Submit only after all above items pass.

## 11. Phase 2 — Comments / Accounts API

Do not include browser scraping or Local Bridge in the production TikTok integration.

After the TikTok for Developers app is approved/live, apply separately for TikTok Accounts API access through TikTok for Business. The intended use case is management of the organic presence of accounts explicitly authorized by their owners, including comment moderation and replies.

The Accounts API application should describe:
- Owned/authorized account management
- Comment retrieval for owned videos
- Unified inbox display
- Reply/moderation by the account owner or authorized team
- No creator scraping, unauthorized analytics, engagement manipulation or media downloading
