# AMU Studio v0.1.0-beta.5 (beta)

This is a translation. The Japanese version ([README.md](README.md)) prevails.

AMU Studio is a Windows app that gives Characters made in SAKU a job and memory and runs them with an external AI.

- One Character acts as the point of contact, takes requests and answers them.
- For requests that need judgment, Seats 2–7 inside the Character exchange views before it answers (1+7).
- Important points go ahead only after a person (Seat 8) has checked them.

This repository is **for distribution only**. It does not contain the app's source code.

## About this beta

- This version is a beta (Pre-release). "AMU Seat8 Console", which Seat 8 (a person) uses to answer, and the "AMU Runtime" zip, for embedding in a product's program, are included with the same version.
- The installer carries a **code signature** (signer: wi-t.com Inc.). Even with a signature, Windows SmartScreen may show a warning until a reputation has built up.
- Before running it, check that the installer's SHA-256 matches the value below.
- **AI answers are drafts.** They do not constitute sign-off, a decision or a production record.
- **Protection when the PC has been taken over is outside what this product covers.** If the PC is fully controlled with administrator rights, the protection of the transmission record and the keys may not work.

## Install and use

1. Download `AMU.Studio_0.1.0-beta.5_x64-ai-live-setup.exe` from the [Releases](https://github.com/wi-tcom/KOKOROAMU/releases) of this repository.
2. Check that its SHA-256 matches `782ad233be06ced8b9ed130b3d3e9d5e355ead28a1de03bf5d28c50a4865b7af` (94,702,896 bytes).
   `Get-FileHash ".\AMU.Studio_0.1.0-beta.5_x64-ai-live-setup.exe" -Algorithm SHA256`
3. Install and start it. It installs per user; administrator rights are not required. If SmartScreen shows a warning, press 「詳細情報」 then 「実行」 ("More info" then "Run anyway" on English Windows). You can install over v0.1.0-beta.4.1.
4. Use your own API key for the AI provider (Anthropic, OpenAI or Gemini). The key is stored in Credential Manager on this PC. You can also run it with Ollama on this PC.

**AI usage fees are billed by the AI provider to the owner of the API key.** The app shows estimates based on the prices published by the provider.

The file names here are the names GitHub downloads (spaces in the names become dots).

### First launch

- The first time you start the app, it may show "Not Responding" for a while. If this happens, please wait without closing the app.
- From the second time on, it starts quickly.

## AMU Seat8 Console

- A separate app from AMU Studio, for Seat 8 (a person) to answer requests. It can also be installed on the same PC as AMU Studio.
- Install `AMU.Seat8.Console_0.1.0-beta.5_x64-ai-live-setup.exe` (27,045,096 bytes, SHA-256 `06758bd12b6a3d7f79f82c76e1da21752ace71a61f06846c751446a7a3d19985`) from the [Releases](https://github.com/wi-tcom/KOKOROAMU/releases).
- AMU Studio and AMU Seat8 Console look at the same shared folder and exchange keys with a passphrase before they exchange requests and answers. The passphrase is not written to any file; you enter it each time you start. It stops after five passphrase attempts that do not succeed.
- The answers from AMU Seat8 Console (such as 「確認した（進めてよい）」, "Confirmed (you may proceed)") are returned signed with the console's key. **A signature-verification result indicates only technical consistency between the recorded answer and the signature verified using the public key.** It does not establish who actually answered, that person's intent, identity, qualifications or organizational authority, or when the answer was actually given. We do not verify the identity, qualifications or authority of the person who answers (Supplementary Terms for AI Products and Services, Section 07).
- What can be asked of Seat 8 is "confirmation". Sign-off and advice are not available in this version.
- **The AI draft is a feature under test.** The end-to-end run of a two-tier Seat 8 (two receiving consoles) has not been checked yet. If no draft appears, proceed by having the Seat 8 person answer (a person's answers, the key exchange and the conversation work without the draft).

## AMU Runtime zip (for embedding in a product's program)

- `AMU_RUNTIME_0.1.0-d38b051_win-x64.zip` (40,616,774 bytes, SHA-256 `552e7f861febf391e92187383e036508289a94a5217cab1fb1ab36195b8e670d`) in the [Releases](https://github.com/wi-tcom/KOKOROAMU/releases). It is also inside the AMU Studio installer.
- There is no installer. Before use, run the following command once as the Windows user that runs the Runtime (not as an administrator or SYSTEM):
  `amu-runtime-host.exe --init-ai-ledger --data-dir <the Runtime's data location>`
- The zip itself has no code signature (a zip file cannot carry one). The executables inside it, once extracted, carry a code signature.

## Changes in this release

- **Transmissions to an AI are now kept in a record that is not lost if the app or PC stops.** A transmission that was interrupted because the app or PC stopped, so that it is not known whether it arrived, is not sent again automatically, so that it is not sent twice. The next time you start, the number of such transmissions is shown at the top of the screen, and you can record what you found from the list (this only records the result; nothing is sent again). When the transmission record cannot be used, nothing is sent.
- **AMU Studio and AMU Seat8 Console are now connected through a shared folder and a passphrase.**
- **More exports.** The AMU Seat8 Console set (the .amupkg and the .amuseat8pkg together), the AMU Seat8 Console package and the memory bundle can be saved. Files are saved in the "Downloads" folder on this PC. The signature badges in the list now use the same words as SAKU Builder, and when a pack Character that has been edited is exported, you check that the original pack's terms of use still apply before it is exported.
- **A notice when Gemini is chosen.** Gemini cannot be chosen for Characters such as those from a Character Pack that prohibits use for training.
- **"Confirmation before sending" has been tidied up.** If "Do not send" is chosen, nothing is sent.
- v0.1.0-beta.3, v0.1.0-beta.3.1, v0.1.0-beta.4 and v0.1.0-beta.4.1 stay published as they are.

For details, see the release notes in [Releases](https://github.com/wi-tcom/KOKOROAMU/releases).

## Known limits

- The AI draft in AMU Seat8 Console is a feature under test (see "AMU Seat8 Console" above).
- Accepting a candidate returned from a Runtime does not create a new Runtime Package.
- You cannot choose where exports and backups are saved (they are saved in the "Downloads" folder on this PC).
- If you open AMU Studio twice, the second window is read-only and does not send (by design).
- Windows x64 only. The screens are in Japanese only (the answer language can be chosen).

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
- The bundled sample Characters (1.2.0) are governed by `LicenseRef-WIT-Sample-1.0` (not OSS).

## Contact and reports

- Reproducible bugs: GitHub Issues in this repository
- Questions: support desk https://www.wi-t.com/contact-8
- Vulnerabilities: do not post them in public issues; tell the support desk.
- Do not include API keys or passwords in your inquiries.

© wi-t.com Inc.
