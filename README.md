# Intelli-Core

Intelli-Core is an app for capturing tax knowledge and turning it into logic. You write down what a memo, a decision table, a set of rules, a diagram, a timeline or a spreadsheet says. Intelli-Core translates every statement as you go into formal logic: first-order logic, IDP-Z3, LEAN 4, Prolog, OWL, SMT-LIB and Drools. Everything comes together in one knowledge base. That knowledge base shows where sources contradict each other, keeps tests, and tracks changes in branches.

Together with [IDP Studio](#4-connect-idp-studio-optional), Intelli-Core can also do the following:
- read documents and propose what they say;
- check the knowledge base with the IDP-Z3 reasoner;
- export it as an Open Knowledge File bundle.

It works on **Mac**, **Windows** and **Linux**.

**[⬇ Download the latest version](https://github.com/BartJanCoppens/Intelli-Core/releases/latest)**

---

## 1. Download

Open the [latest release](https://github.com/BartJanCoppens/Intelli-Core/releases/latest), scroll down to **Assets** and click the file for your computer:

| Your computer | File to download |
|---|---|
| Mac with an Apple chip (M1, M2, M3, M4…) | `Intelli-Core-<version>-arm64.dmg` |
| Mac with an Intel processor | `Intelli-Core-<version>-x64.dmg` |
| Windows 10 or 11 | `Intelli-Core-Setup-<version>-x64.exe` |
| Linux (most distributions) | `Intelli-Core-<version>-x86_64.AppImage` |
| Linux (Ubuntu, Debian and similar, as a package) | `Intelli-Core-<version>-amd64.deb` |

Not sure which Mac you have? Click the Apple menu  › **About This Mac**. If it says **Chip: Apple M…**, take the Apple chip file; if it says **Processor: Intel**, take the Intel file.

You can ignore the other files (`.zip`, `.blockmap`, `.yml`): the app uses them for its updates.

## 2. Install

### Mac

1. Open the `.dmg` file you downloaded.
2. Drag **Intelli-Core** onto the **Applications** folder in the window that appears.
3. Open **Intelli-Core** from your Applications folder (or with Spotlight). The first time, macOS asks whether you want to open an app downloaded from the internet: click **Open**.

<details>
<summary>macOS says it can't check Intelli-Core for malicious software</summary>

This happens with a version that isn't signed by its developer. Click **Done** (or **OK**), then open **System Settings** › **Privacy & Security**. Scroll down to the message about Intelli-Core and click **Open Anyway**. Confirm with your password or Touch ID, then click **Open Anyway** once more. From then on Intelli-Core opens normally.
</details>

### Windows and Linux

Intelli-Core isn't registered with Microsoft, so Windows warns you the first time you open it. That's expected; the steps below show how to get past the warning once.

#### Windows

1. Double-click `Intelli-Core-Setup-<version>-x64.exe`.
2. If Windows shows **Windows protected your PC**, click **More info**, then **Run anyway**.
3. Intelli-Core installs by itself (no administrator rights needed) and opens. You'll find it in the Start menu afterwards.

Needs Windows 10 or 11, 64-bit.

#### Linux

**AppImage** (works on most distributions):

```sh
chmod +x Intelli-Core-*-x86_64.AppImage
./Intelli-Core-*-x86_64.AppImage
```

Or right-click the file › **Properties** › **Permissions**, tick **Allow executing file as program**, then double-click it. On Ubuntu 22.04 or later, if it doesn't start, install FUSE first: `sudo apt install libfuse2` (on Ubuntu 24.04: `sudo apt install libfuse2t64`).

**Debian package:**

```sh
sudo apt install ./Intelli-Core-*-amd64.deb
```

Intelli-Core then appears in your applications menu.

## 3. Start working

Intelli-Core opens on the Belgian Tax KB example. Edit any canvas and the formalisation dock on the right translates it immediately. Each knowledge domain is a workspace, saved as an `.intellicore` file: use **File › New Workspace**, **Open…**, **Save** and **Save As…**. A dot next to the workspace name means there are unsaved changes, and Intelli-Core asks before closing them. Double-click an `.intellicore` file to open it; the app reopens your last workspace when it starts. Click any clause to go to its source: the canvas it was written in, or the highlighted passages of the document it was extracted from. **KB › Branches** lets you try changes on a branch and merge them back after review.

## 4. Start a domain with Claude (optional)

**File › New with AI…** lets Claude help you set up a new knowledge domain: it asks about the domain, searches the web for sources, and proposes rules, parameters, concepts and tests. You accept or skip each one.

It needs your own Claude API key from the [Claude Console](https://platform.claude.com). Paste it in **Settings › Claude**. Intelli-Core keeps it in your system keychain, and use is billed to your Anthropic account.

## 5. Connect IDP Studio (optional)

These features need IDP Studio (ask Bart Jan for access) running on the same computer:
- the **Documents** canvas;
- **Run in IDP-Z3** under **KB › Tests**;
- the assistant's **Detect gaps** and **Generate tests**;
- the **Open Knowledge File** export;
- **Visualisation**.

1. Install and open IDP Studio. It listens on `http://127.0.0.1:8765`.
2. In Intelli-Core, open **Workspace › Documents**. It shows **Connected to IDP Studio**.

If IDP Studio runs on another port, start Intelli-Core with `IDP_STUDIO_URL` set, for example `IDP_STUDIO_URL=http://127.0.0.1:9000`.

**Visualisation** turns the knowledge base into an interactive app. In **Design**, place the knowledge base's values on a dashboard. Settle the ones you leave off: give a default, or leave them free. Add buttons that find solutions, the best value, or an explanation. Then click **View**: the dashboard opens on its own page. Change any value there and IDP-Z3 shows what follows, with a **Why?** for each derived value.

## Updates

- **Mac**, **Windows** and **Linux AppImage**: Intelli-Core tells you when a new version is ready. Click **Download and install**; it installs the next time you restart Intelli-Core.
- **Linux .deb** (and a Mac version not signed by its developer): Intelli-Core tells you when a new version is ready, with a **Download** button. Install it the same way as the first time.

You can also check by hand: **Intelli-Core › Check for Updates…** on a Mac, **Help › Check for Updates…** elsewhere.

## Uninstall

- **Mac**: drag **Intelli-Core** from Applications to the Bin.
- **Windows**: **Settings › Apps › Installed apps**, find Intelli-Core › **Uninstall**.
- **Linux**: delete the AppImage, or run `sudo apt remove intelli-core`.

## Questions or problems

Contact Bart Jan directly, or [open an issue](https://github.com/BartJanCoppens/Intelli-Core/issues) here.
