# AMU Studio v0.1.0-beta.3.1 (beta)

This is a translation. The Japanese version ([README.md](README.md)) prevails.

AMU Studio is a Windows app that gives Characters made in SAKU a job and memory and runs them with an external AI.

- One Character acts as the point of contact, takes requests and answers them.
- For requests that need judgment, Seats 2–7 inside the Character exchange views before it answers (1+7).
- Anything that needs the agreement of a person (Seat 8) is not answered until that agreement is given.

This repository is **for distribution only**. It does not contain the app's source code.

## About this beta

- This version is a beta (Pre-release). The contents of AMU Studio are the same as v0.1.0-beta.3; it has been code-signed and published again. "AMU Seat8 Console" (demo version), which Seat 8 (a person) uses, is also included.
- The installer carries a **code signature** (signer: wi-t.com Inc.). Even with a signature, Windows SmartScreen may show a warning until a reputation has built up.
- Before running it, check that the installer's SHA-256 matches the value below.
- **AI answers are drafts.** They do not constitute sign-off, a decision or a production record.
- The settings screen of AMU Studio still shows old text from before the signature was added (such as 「β は未署名・未公開」, "the beta is unsigned and unpublished"). This will be fixed in the next version.

## Install and use

1. Download `AMU Studio_0.1.0-beta.3.1_x64-ai-live-setup.exe` from the [Releases](https://github.com/wi-tcom/KOKOROAMU/releases) of this repository.
2. Check that its SHA-256 matches `14e208afbce92821dc05cab0ce8dde73c9c77dbaa9455054db2ecc733a06fea4` (26,253,720 bytes).
   `Get-FileHash ".\AMU Studio_0.1.0-beta.3.1_x64-ai-live-setup.exe" -Algorithm SHA256`
3. Install and start it. It installs per user; administrator rights are not required. If SmartScreen shows a warning, press 「詳細情報」 then 「実行」 ("More info" then "Run anyway" on English Windows).
4. Use your own API key for the AI provider (Anthropic or OpenAI). The key is stored in Credential Manager on this PC.

**AI usage fees are billed by the AI provider to the owner of the API key.** The app shows estimates based on the prices published by the provider.

### First launch

- The first time you start the app, it may show "Not Responding" for a few minutes. With AMU Seat8 Console, the whole PC once stopped responding for about two minutes on the first start.
- If this happens, please wait without closing the app.
- From the second time on, it starts quickly (in our tests, AMU Studio started in about 11 seconds the second time).

## AMU Seat8 Console (demo version)

- A separate app from AMU Studio, for Seat 8 (a person) to confirm or reject. It does not connect to an external AI.
- Install `AMU Seat8 Console_0.1.0-beta.3.1_x64-setup.exe` (26,230,632 bytes, SHA-256 `6f8717953f3e3d828c2714db14b3a897d3bb77a10986243c297d453b980147ef`) from the [Releases](https://github.com/wi-tcom/KOKOROAMU/releases), separately from AMU Studio.
- AMU Studio and AMU Seat8 Console exchange items through the same shared folder, each pointing to it by path. A synced folder of Google Drive for desktop can also be used (AMU does not communicate with Google directly). The text of Seat 8's answers is placed in the folder sealed.
- **This is a demo version.** The issuer and RA are not the production ones, and the screen shows DEMO.
- There are no screens for creating sign-offs, advice, inquiries or contacts (confirming and rejecting only). The round trip on one PC has been checked. The round trip between two PCs has not been checked yet.

## Changes in this release

- **The installer and the executables inside it have been code-signed.** The signature shows only that the files were made by wi-t.com Inc. and that they have not changed since they were signed. It does not show that the contents are correct or that they are safe.
- **AMU Seat8 Console (demo version) added.**
- The features, screens and text of AMU Studio are the same as in v0.1.0-beta.3. v0.1.0-beta.3 (unsigned) stays published as it is.

For details, see the release notes in [Releases](https://github.com/wi-tcom/KOKOROAMU/releases).

## Services in preparation

The following services are **in preparation**. Registration and applications are not open yet.

- SAKU Repair Desk
- AMU Evaluation Center
- ERABAZU.WORKS

You can read about SAKU Repair Desk and AMU Evaluation Center on the overview page (https://support.kokoroamu.jp/, in Japanese). The start of registration will be announced on kokoroamu.jp.

## Terms

- Use is governed by the Terms of Use and the Supplementary Terms for AI Products and Services of wi-t.com Inc. (the Japanese versions prevail).
  - Terms of Use: https://www.wi-t.com/japanese-terms-conditions (English reference translation: https://www.wi-t.com/en-terms)
  - Supplementary Terms for AI Products and Services: https://www.wi-t.com/aiproductterms (English reference translation: https://www.wi-t.com/en-ai-product-terms)
- No open-source license applies to the contents of this repository or to the app. Copyright belongs to wi-t.com Inc. (`LICENSE.md`).
- Licenses of bundled third-party software follow what is shown in the app.
- The bundled sample Characters (1.1.0) are governed by `LicenseRef-WIT-Sample-1.0` (not OSS).

## Contact and reports

- Reproducible bugs: GitHub Issues in this repository
- Questions: support desk https://www.wi-t.com/contact-8
- Vulnerabilities: do not post them in public issues; tell the support desk.
- Do not include API keys or passwords in your inquiries.

© wi-t.com Inc.
