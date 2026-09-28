# AMU Studio v0.1.0-beta.3 (beta)

This is a translation. The Japanese version ([README.md](README.md)) prevails.

AMU Studio is a Windows app that gives Characters made in SAKU a job and memory and runs them with an external AI.

- One Character acts as the point of contact, takes requests and answers them.
- For requests that need judgment, Seats 2–7 inside the Character exchange views before it answers (1+7).
- Anything that needs the agreement of a person (Seat 8) is not answered until that agreement is given.

This repository is **for distribution only**. It does not contain the app's source code.

## About this beta

- This version is a beta (Pre-release).
- **It is not code-signed yet.** Windows SmartScreen or antivirus software may warn or stop it from running.
- Before running it, check that the installer's SHA-256 matches the value below.
- **AI answers are drafts.** They do not constitute sign-off, a decision or a production record.

## Install and use

1. Download `AMU Studio_0.1.0-beta.3_x64-ai-live-setup.exe` from the [Releases](https://github.com/wi-tcom/KOKOROAMU/releases) of this repository.
2. Check that its SHA-256 matches `77598d3d4a918d9f5c8067fa0613a31ccdb14f8eb14f0676a821ea911c32ddc6` (26,089,507 bytes).
   `Get-FileHash ".\AMU Studio_0.1.0-beta.3_x64-ai-live-setup.exe" -Algorithm SHA256`
3. Install and start it. It installs per user; administrator rights are not required. If SmartScreen shows a warning, press 「詳細情報」 then 「実行」 ("More info" then "Run anyway" on English Windows).
4. Use your own API key for the AI provider (Anthropic or OpenAI). The key is stored in Credential Manager on this PC.

**AI usage fees are billed by the AI provider to the owner of the API key.** The app shows estimates based on the prices published by the provider.

## Changes in this release

- **Fast council added.** Requests that need judgment are checked with fewer transmissions. The views of the six seats are gathered in one call, and only the seats that disagree, for example, are checked individually.
- **Choice of council method:** 「速い合議」 (fast council, the default) / 「6 席の合議・早く終える」 (six-seat council, finish early) / 「6 席の合議・3 巡回す」 (six-seat council, three rounds). The six-seat councils send more transmissions and cost more.
- **「アンバーとして合議にかける」 (send to the council as amber) button added.** When Seat 1's classification is lighter than amber, it is raised to amber and sent to the council; even if the council agrees, no answer is given until Seat 8 (a person) agrees.
- **The model is chosen from a list before you start.** Each model shows an estimated unit price based on the provider's price list.
- **「考える量」 (amount of thinking) can be chosen:** 「提供元に任せる」 (leave it to the provider, the default) / 「少なく」 (less) / 「考えない」 (no thinking). The effect of reducing the amount of thinking on the answers has not been checked yet.
- **Lower cost by reusing the Character's text (caching).**
- **Signatures of ERABAZU occupation templates are checked against the published key list.**
- **Self-made Character ZIPs from SAKU can be imported.** Because they carry no signature, they are marked 「自作・未確認」 (self-made, not checked). In this version, you can only import them and add them to the list; you cannot yet put a self-made Character in a team and run it.
- **Three sample-mode Characters bundled.** Choose them with 「サンプルを読み込む」 (Load samples) in Character selection (rights terms `LicenseRef-WIT-Sample-1.0`; not OSS).

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
