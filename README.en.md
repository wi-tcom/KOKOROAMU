# AMU Studio v0.1.0-beta.4 (beta)

This is a translation. The Japanese version ([README.md](README.md)) prevails.

AMU Studio is a Windows app that gives Characters made in SAKU a job and memory and runs them with an external AI.

- One Character acts as the point of contact, takes requests and answers them.
- For requests that need judgment, Seats 2–7 inside the Character exchange views before it answers (1+7).
- Anything that needs the agreement of a person (Seat 8) is not answered until that agreement is given.

This repository is **for distribution only**. It does not contain the app's source code.

## About this beta

- This version is a beta (Pre-release). A new version of "AMU Seat8 Console" (demo version), which Seat 8 (a person) uses, is also included.
- **As in beta.3.1, the Seat 8 part is a demo.** The screen shows DEMO. It is not connected to the production Seat 8 certification.
- The installer carries a **code signature** (signer: wi-t.com Inc.). Even with a signature, Windows SmartScreen may show a warning until a reputation has built up.
- Before running it, check that the installer's SHA-256 matches the value below.
- **AI answers are drafts.** They do not constitute sign-off, a decision or a production record.
- The settings screen of AMU Studio still shows old text from before the signature was added (such as 「β は未署名・未公開」, "the beta is unsigned and unpublished"). This will be fixed in the next version.

## Install and use

1. Download `AMU Studio_0.1.0-beta.4_x64-ai-live-setup.exe` from the [Releases](https://github.com/wi-tcom/KOKOROAMU/releases) of this repository.
2. Check that its SHA-256 matches `7eb8161d8c0b0801013cdace7734a39fd38e6f02bccec827721787c64e570b04` (26,327,552 bytes).
   `Get-FileHash ".\AMU Studio_0.1.0-beta.4_x64-ai-live-setup.exe" -Algorithm SHA256`
3. Install and start it. It installs per user; administrator rights are not required. If SmartScreen shows a warning, press 「詳細情報」 then 「実行」 ("More info" then "Run anyway" on English Windows).
4. Use your own API key for the AI provider (Anthropic or OpenAI). The key is stored in Credential Manager on this PC.

**AI usage fees are billed by the AI provider to the owner of the API key.** The app shows estimates based on the prices published by the provider.

### First launch

- The first time you start the app, it may show "Not Responding" for a while. If this happens, please wait without closing the app.
- With beta.3.1, the whole PC once stopped responding for about two minutes the first time AMU Seat8 Console was started. This did not happen in our beta.4 tests; AMU Seat8 Console started in about 4 seconds.
- From the second time on, it starts quickly.

## AMU Seat8 Console (demo version)

- A separate app from AMU Studio, for Seat 8 (a person) to answer requests. It does not connect to an external AI.
- Install `AMU Seat8 Console_0.1.0-beta.4_x64-setup.exe` (26,304,624 bytes, SHA-256 `93b5967e3f8b1b795e8d48335b4d7b8170f94609ccedadd7c9b93c60b22009a0`) from the [Releases](https://github.com/wi-tcom/KOKOROAMU/releases), separately from AMU Studio.
- AMU Studio and AMU Seat8 Console exchange items through the same shared folder, each pointing to it by path. A synced folder of Google Drive for desktop can also be used (AMU does not communicate with Google directly). The text of Seat 8's answers is placed in the folder sealed.
- **This is a demo version.** The issuer and the Seat 8 certification are not the production ones, and the screen shows DEMO.
- It can answer sign-off, advice, inquiry and contact requests. In the demo version, however, sign-off and advice cannot be satisfied (confirmation, inquiry and contact can be used).
- The round trip between two PCs has not been checked yet.

## Changes in this release

- **A "Runtime から戻った候補" (Candidates returned from the Runtime) section on the editing screen.** You load candidates (`.amureturn`) written by a Runtime, decide for each whether to accept it, and save a signed receipt. Accepting a candidate does not change the original Character automatically. A Runtime is not included in this release.
- **Before a conversation that a Seat 8 person joins, the requester is asked to declare their country/region.** If it is outside Japan, or nothing is declared, no Seat 8 person joins.
- **More kinds of requests to Seat 8 (a person)** (sign-off, advice, inquiry and contact). In the demo version, sign-off and advice cannot be satisfied.
- **You can choose the answer language.**
- Characters you made yourself can be run in a request card (team) with your own signature.
- A fix for transmissions to the AI failing on PCs where antivirus software inspects HTTPS traffic.
- Other corrections (seat names, council text, where consent records are kept, and so on) and the changes to AMU Seat8 Console are described in the release notes.
- v0.1.0-beta.3 and v0.1.0-beta.3.1 stay published as they are.

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
