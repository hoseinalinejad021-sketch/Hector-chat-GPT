# Build Hector APK privately

The source repository `hoseinalinejad021-sketch/Hector` stays private. This repository contains only a build workflow and setup notes; it does not contain the app source.

## One-time setup

1. In GitHub, open the private `Hector` repository → Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token.
2. Choose only the `Hector` repository and grant **Contents: Read-only**. Do not grant write/admin access.
3. Copy the token once. Never paste it into a file, issue, chat, or workflow YAML.
4. Open this public repository → Settings → Secrets and variables → Actions → New repository secret.
5. Name it exactly `HECTOR_SOURCE_TOKEN`; paste the token into the secret value and save it.

## Build

1. Open Actions → **Build Hector APK** → Run workflow.
2. Wait for the job to finish.
3. If it succeeds, open that run and download the `hector-debug-apk` artifact.
4. Extract the ZIP to obtain the APK.

## Important

- Do not change the private source repository visibility.
- Do not commit tokens, signing keys, passwords, or private source code here.
- The workflow creates a **debug APK**, not a release-signed APK.
- An APK is available only after a successful run. This setup does not guarantee a successful build until the secret is configured and the workflow completes.
