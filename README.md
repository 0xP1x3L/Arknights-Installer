# Arknights Installer

A GitHub Actions workflow that downloads a selected Arknights Android client, extracts and merges APK splits when needed, aligns and signs the resulting APK, and publishes the files as a downloadable workflow artifact.

## Supported clients

- **Official**
- **YoStarEN**
- **YoStarJP**
- **YoStarKR**
- **txwy**

### Bilibili client

The Bilibili client is not available in this GitHub Actions workflow. To download it manually, visit the [Arknights listing on Bilibili Game Center](https://app.biligame.com/detail?id=101772) and download the APK from that page.

## How to run the workflow

1. Open the [Actions tab](../../actions) of this repository.
2. In the workflow list, select **Download Arknights APK**.
3. Click **Run workflow**.
4. Choose the client you want from the **client** dropdown.
5. Click **Run workflow** to start the job.
6. Open the running workflow, wait for it to finish successfully, and open the completed run.
7. In **Artifacts**, download the artifact named for the selected client (for example, `Arknights-Official`).

## What the workflow produces

- An APK named `Arknights-<Client>.apk`.
- Any OBB files found in the downloaded package, preserved under `Android/obb/<package-id>/`.

Artifacts are retained for **14 days**. Download them before they expire.

## Important notes

- The workflow downloads supported clients through APKPure using `apkeep`. Availability depends on the upstream source.
- The output APK is signed with the APKToolGUI test key, not an official publisher signing key. It is intended for testing and may not install as an update over an official installation. You may need to uninstall the existing app first; doing so can remove local app data.
- APK split merging and signing are performed automatically by the workflow.
- If a run fails, open the run in **Actions**, expand the failed step, and read its log. A failed download may mean the upstream package is unavailable or has changed.
- Only download and install APKs from sources you trust.

## Run history

All workflow runs are available from the repository's [Actions tab](../../actions).
