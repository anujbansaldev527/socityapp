# Community OS v0.3 — Source starter / Pehla source build
M01 foundation and M02 identity/onboarding are implemented in source; M01 acceptance remains open for physical Android interaction, and M02 web UI awaits interactive browser QA. M03 finance design is documented and test-only implementation has started. / M01 foundation aur M02 source mein hain; Android device aur M02 browser QA baaki hain. M03 finance design documented hai aur test-only development shuru hua hai. Not a production release.

## Start locally (Windows PowerShell) / Local setup
Install Node 22.13+ (22.x), Git, and pnpm 10.11.0. Docker is optional when using MongoDB Atlas Free; Android Studio, JDK and ADB are needed only for native Android builds. Expo Go for Android supports SDK 57, but install a compatible SDK 57 build. No paid service is required. / Docker optional hai; native Android build ke liye Android Studio/JDK/ADB chahiye. Expo Go ka SDK 57-compatible Android build use karein.

```powershell
npm install -g pnpm@10.11.0
pnpm install --frozen-lockfile
Copy-Item apps/web/.env.example apps/web/.env.local
Copy-Item apps/mobile/.env.example apps/mobile/.env
node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
```
Set the generated value as READINESS_TOKEN in apps/web/.env.local; never commit it. The committed pnpm-lock.yaml supports frozen installs. If Corepack cannot bootstrap pnpm, install the exact version directly with `npm install --global pnpm@10.11.0` (or run it temporarily with `npm exec --yes --package=pnpm@10.11.0 -- pnpm <command>`). Run `pnpm --filter @community/mobile exec expo install --check`; the checked SDK 57 dependency set passes.

### MongoDB choice / MongoDB chunav

Use either local MongoDB 7 with a replica set (Docker Compose below) or an already available, eligible MongoDB Atlas Free test cluster. Docker is optional. For Atlas, use synthetic data only, create a least-privilege user limited to `community_os_demo`, restrict the network allowlist, and put the URI in the ignored `apps/web/.env.local`; never paste or commit it. Do not upgrade to a paid cluster. / Atlas par sirf dummy data, restricted user aur private allowlist use karein. URI secret hai.

```dotenv
APP_ENV=local
MONGODB_URI=mongodb+srv://<restricted-user>:<url-encoded-password>@<cluster-host>/?retryWrites=true&w=majority
MONGODB_DB_NAME=community_os_demo
```

```powershell
docker compose -f infra/compose.yaml up -d --wait
docker compose -f infra/compose.yaml exec mongo mongosh --quiet --eval 'try { rs.status() } catch(e) { rs.initiate({_id:"rs0",members:[{_id:0,host:"localhost:27017"}]}) }'
```
Wait until `docker compose -f infra/compose.yaml exec mongo mongosh --quiet --eval 'db.hello().isWritablePrimary'` returns true. Docker database is unauthenticated and binds host loopback only; local synthetic data only. Alternatively configure Atlas in apps/web/.env.local using an eligible free test cluster, a restricted database user and network allowlist; never use real data.

```powershell
pnpm seed
pnpm seed
pnpm db:test
pnpm dev
```
Open http://localhost:3000 and click Check / retry. In another terminal:

```powershell
pnpm smoke
pnpm test
pnpm typecheck
pnpm lint
pnpm build
```
Set `$env:READINESS_TOKEN` locally to the same secret before `pnpm smoke` to test authenticated readiness; unset it afterward. Stop Mongo and verify public health remains 200, authenticated readiness 503. Do not expose readiness token to mobile.

## Android / Mobile setup
For Android emulator keep `http://10.0.2.2:3000/api/v1`. For physical device change apps/mobile/.env to `http://YOUR_PC_LAN_IP:3000/api/v1`, use same Wi-Fi and restrict firewall access to the private network. SDK 57 has an Android Expo Go build; use the SDK-matched build from [expo.dev/go](https://expo.dev/go). `pnpm mobile` starts Metro; scan the QR with Expo Go. `pnpm android` opens an emulator and requires Android tooling. Native APK builds require Android SDK/JDK and prebuild/run:android. / Phone se PC ka IP use karein; SDK 57 wala Expo Go install karein.

## What is implemented / Kya bana hai
Responsive Next.js landing and workspace, versioned REST API, tenant-scoped auth/onboarding, shared contracts, protected DB readiness, Mongo connection reuse, synthetic seed and DB acceptance scripts, Expo Android app, CI definition. No billing or production data.

## Continue with AI / Agla step
Read AGENTS.md, rules.md, tracker.md, progress.md, last log, and milestones/M01-foundation.md. M02 identity/onboarding source already exists; verify it rather than recreating it. Keep M01 acceptance open until Android device checks pass. Do not recreate existing source. Historical docs retained under docs/. See docs/evidence/ for executed tests. No paid infrastructure or release without approval.

## Verification environment note (2026-11-24) / Local verification note
Verified in this environment: Node v22.23.1, pnpm 10.11.0 via npm exec, pnpm lockfile generation and initial dependency install; frozen install passed in a fresh manifest workspace with strict peer checks; the repository-root frozen relink still hits a Windows EPERM issue. In the current session, isolated web lint, all six workspace typechecks, 12 unit tests, Next.js production build and HTTP health/readiness checks passed; earlier Expo SDK compatibility and Android JavaScript bundle export passed. Later Antigravity verification supersedes the earlier standalone Mongo result: local MongoDB 8.2 replica set `rs0` passed idempotent seed twice and transaction checks. Production build, typecheck, unit tests and two-tenant security suite passed per the latest log. Android device/Expo Go interaction remains untested because no device is connected; the isolated web lint rerun passed. The latest audit reported one moderate advisory and no high/critical findings. See [M01 verification evidence](docs/evidence/M01-verification-2026-11-24.md). / Web, API, synthetic Mongo seed aur transaction verify hue. Physical Android device aur lint recheck baaki hain.
