# Public repository audit and revised M0–M4 plan

Snapshot: **9 October 2026 (Europe/Istanbul)**. Scope: only public repositories owned by Zaryob and 9base. **77 repositories: Zaryob 23 (3 archived), 9base 54 (50 archived); 53 archived, 24 open.** Counts are a snapshot, not a permanent profile claim. No private repository was inspected.

This audit read GitHub repository metadata, README/root files and published release metadata for all 77. For open repositories it also inspected tree/build/test/workflow markers and the five latest workflow runs. Selected repositories received the local checks below. Archived repositories were not unarchived, rebuilt or given speculative maintenance commitments.

A GitHub fork flag identifies a relationship in GitHub; its absence does not prove original authorship. A license-detector value of `NOASSERTION` or missing data does not establish that licensing is absent. Repository topics and README declarations are maintenance context; open state, recent documentation commits and passing tests alone do not prove sustained maintenance. Build/test marker presence is not execution evidence.

[Machine-readable inventory](public-repositories.json) | [CSV](public-repositories.csv) | [Public Portfolio Quality project](https://github.com/users/Zaryob/projects/9)

## Plan revisions and acceptance

| Stage | Current action | Acceptance / remaining gate |
| --- | --- | --- |
| M0: facts and safe setup | Publish the 77-repository inventory, retain 9base taxonomy, audit fork deltas; replace the destructive dotfiles installer; document historical LinkLayerModel input/output | Local installer checks pass; numerical model validity remains open; archive flags/history unchanged |
| M1: presentation | Curated profile project map, existing website catalogue extended, 9base evidence index | Reviewable PRs; bio/pin changes still pending because current credentials cannot update bio and the browser session is unauthenticated |
| M2: evidence | C backend/sanitizer record, Rust bounded fuzz/Miri/benchmark scope, imshark current sanitizer record, Performer synthetic pair, Sift test wiring, Pena synthetic test record | Local outcomes recorded, including failures; no invented CI badges, speeds, screenshots, binaries or device results |
| M3: distribution | Gate releases on TLS identity checks, platform packaging, live profiling and physical/signed app validation | Open issues carry concrete acceptance criteria; no new tag or release until those checks are complete |
| M4: maintenance | Review unresolved fork/provenance/license questions, XML compatibility and equivalent-work benchmarks | No blanket removal/archival policy; ongoing commitments require evidence and owner decisions |

The earlier roadmap is revised around the current evidence: 9base already has detailed curation and only four open repositories; `build-dependencies` is already archived. Work here extends that curation. The detailed current backlog is authoritative for acceptance criteria.

## Selected local results

The local host used macOS 27.0 arm64, Apple M4/16 GiB and Xcode 27.0. Linux collector checks used a clean source archive in a local Python 3.12 container. No paid CI service was required.

| Repository | Actual observation |
| --- | --- |
| [Zaryob/iksemel](https://github.com/Zaryob/iksemel) | 7/7 plain + ASan/UBSan; 9/9 per TLS backend; transport unverified |
| [Zaryob/iksemel-rs](https://github.com/Zaryob/iksemel-rs) | stable suites + 8 Miri tests passed; 314921 short fuzz executions; benchmarks scoped |
| [Zaryob/imshark](https://github.com/Zaryob/imshark) | Debug ASan/UBSan serial: 1267 pass, 28 skip, 0 fail; parallel fixture collisions recorded; release failures remain |
| [Zaryob/Performer](https://github.com/Zaryob/Performer) | Synthetic bundles valid; viewer 117 pass/1 skip; Linux collector 2 errors/1 skip |
| [Zaryob/Sift](https://github.com/Zaryob/Sift) | Unsigned build; serial XCTest 49 tests, 4 assertion failures in 3 cases; host shutdown interrupted |
| [Zaryob/Pena](https://github.com/Zaryob/Pena) | 39 definitions / 93 parameterized executions passed; physical audio unverified |
| [Zaryob/dotfiles](https://github.com/Zaryob/dotfiles) | Isolated installer regression tests passed |
| [Zaryob/LinkLayerModel](https://github.com/Zaryob/LinkLayerModel) | Build + example exit succeeded; output contains 40 NaN entries |
| [Zaryob/CaffeVigil](https://github.com/Zaryob/CaffeVigil) | Source/documentation review only; Windows runtime unverified |
| [Zaryob/zaryob.github.io](https://github.com/Zaryob/zaryob.github.io) | Jekyll build + 92-page local link check passed |

These are bounded checks, not a full security audit. C TLS builds do not test peer identity or modern transport safety. Rust short fuzz/Miri runs do not certify conformance. Synthetic profiler/tuner data does not establish live overhead, microphone accuracy or device behavior. imshark has no published release at this snapshot; recent packaging failures are tracked before any binary publication.

## Fork evidence

Comparisons below concern the default branches at this snapshot, not every branch. “Ahead” can be documentation only. Preserve upstream names/licenses and use retained commits when describing local engineering work.

| Fork | Parent | Ahead / behind | Interpretation |
| --- | --- | --- | --- |
| [Zaryob/coherent-rtlsdr](https://github.com/Zaryob/coherent-rtlsdr) | mlaaks/coherent-rtlsdr | 0 / 0 | identical |
| [Zaryob/gitbook-pdf](https://github.com/Zaryob/gitbook-pdf) | vs0uz4/gitbook-pdf | 7 / 0 | ahead |
| [Zaryob/GPU_SDR](https://github.com/Zaryob/GPU_SDR) | nasa/GPU_SDR | 1 / 0 | ahead |
| [Zaryob/gr-pdw](https://github.com/Zaryob/gr-pdw) | gtri/gr-pdw | 0 / 0 | identical |
| [Zaryob/iksemel](https://github.com/Zaryob/iksemel) | meduketto/iksemel | 128 / 1 | diverged |
| [Zaryob/SDRPlusPlus](https://github.com/Zaryob/SDRPlusPlus) | AlexandreRouma/SDRPlusPlus | 24 / 66 | diverged |
| [Zaryob/volk](https://github.com/Zaryob/volk) | gnuradio/volk | 0 / 200 | behind |
| [9base/gdb-dashboard](https://github.com/9base/gdb-dashboard) | cyrus-and/gdb-dashboard | 1 / 0 | ahead |
| [9base/jsbsim](https://github.com/9base/jsbsim) | JSBSim-Team/jsbsim | 3 / 210 | diverged |
| [9base/qFlipper](https://github.com/9base/qFlipper) | flipperdevices/qFlipper | 3 / 0 | ahead |

Additional source review: gdb-dashboard's observed single local commit changes its README; qFlipper retains a compatibility patch; jsbsim's local C130 adjustment is historical. The `gr-doa` default-branch comparison had no common ancestor; no mirror/equivalence claim follows. See individual READMEs for attribution and full historical context.

## Repository decisions

Retain archived state for all archived repositories. For open forks, establish local use/deltas before changing maintenance labels or synchronizing. For public original tools, present their real source/build paths and current limitations; release availability must come from actual published assets. No automatic transfer, deletion, license replacement, history rewrite or mass upstream README edit is part of this change.

| Repository | GitHub origin relation | State / maintenance evidence | README / release count | Local check |
| --- | --- | --- | --- | --- |
| [Zaryob/CaffeVigil](https://github.com/Zaryob/CaffeVigil) | not marked as a fork; see attribution | open; open; maintenance not established by metadata | README.md / 0 | Source/documentation review only; Windows runtime unverified |
| [Zaryob/coherent-rtlsdr](https://github.com/Zaryob/coherent-rtlsdr) | fork of mlaaks/coherent-rtlsdr | open; fork; maintenance unverified | README.md / 0 | Not compiled/tested in this audit |
| [Zaryob/donut](https://github.com/Zaryob/donut) | not marked as a fork; see attribution | archived; archived historical | README.md / 0 | Not compiled/tested in this audit |
| [Zaryob/dotfiles](https://github.com/Zaryob/dotfiles) | not marked as a fork; see attribution | open; open; maintenance not established by metadata | README.md / 0 | Isolated installer regression tests passed |
| [Zaryob/gitbook-pdf](https://github.com/Zaryob/gitbook-pdf) | fork of vs0uz4/gitbook-pdf | open; fork; maintenance unverified | README.md / 0 | Not compiled/tested in this audit |
| [Zaryob/GPU_SDR](https://github.com/Zaryob/GPU_SDR) | fork of nasa/GPU_SDR | open; fork; maintenance unverified | README.md / 0 | Not compiled/tested in this audit |
| [Zaryob/gr-doa](https://github.com/Zaryob/gr-doa) | fork of EttusResearch/gr-doa | open; fork; maintenance unverified | README.md / 0 | Not compiled/tested in this audit |
| [Zaryob/gr-pdw](https://github.com/Zaryob/gr-pdw) | fork of gtri/gr-pdw | open; fork; maintenance unverified | README.md / 0 | Not compiled/tested in this audit |
| [Zaryob/iksemel](https://github.com/Zaryob/iksemel) | fork of meduketto/iksemel | open; fork; maintenance unverified | README.md / 4 | 7/7 plain + ASan/UBSan; 9/9 per TLS backend; transport unverified |
| [Zaryob/iksemel-rs](https://github.com/Zaryob/iksemel-rs) | not marked as a fork; see attribution | open; open; maintenance not established by metadata | README.md / 3 | stable suites + 8 Miri tests passed; 314921 short fuzz executions; benchmarks scoped |
| [Zaryob/imshark](https://github.com/Zaryob/imshark) | not marked as a fork; see attribution | open; open; maintenance not established by metadata | README.md / 0 | Debug ASan/UBSan serial: 1267 pass, 28 skip, 0 fail; parallel fixture collisions recorded; release failures remain |
| [Zaryob/inary](https://github.com/Zaryob/inary) | not marked as a fork; see attribution | archived; archived historical | README / 2 | Not compiled/tested in this audit |
| [Zaryob/kilavuzlar](https://github.com/Zaryob/kilavuzlar) | not marked as a fork; see attribution | open; open; maintenance not established by metadata | README.md / 0 | Not compiled/tested in this audit |
| [Zaryob/LinkLayerModel](https://github.com/Zaryob/LinkLayerModel) | not marked as a fork; see attribution | open; open; maintenance not established by metadata | Readme.md / 0 | Build + example exit succeeded; output contains 40 NaN entries |
| [Zaryob/Pena](https://github.com/Zaryob/Pena) | not marked as a fork; see attribution | open; open; maintenance not established by metadata | README.md / 0 | 39 definitions / 93 parameterized executions passed; physical audio unverified |
| [Zaryob/Performer](https://github.com/Zaryob/Performer) | not marked as a fork; see attribution | open; open; maintenance not established by metadata | README.md / 0 | Synthetic bundles valid; viewer 117 pass/1 skip; Linux collector 2 errors/1 skip |
| [Zaryob/raspipboy](https://github.com/Zaryob/raspipboy) | not marked as a fork; see attribution | archived; archived historical | README.md / 0 | Not compiled/tested in this audit |
| [Zaryob/SDRPlusPlus](https://github.com/Zaryob/SDRPlusPlus) | fork of AlexandreRouma/SDRPlusPlus | open; fork; maintenance unverified | readme.md / 0 | Not compiled/tested in this audit |
| [Zaryob/Sift](https://github.com/Zaryob/Sift) | not marked as a fork; see attribution | open; open; maintenance not established by metadata | README.md / 0 | Unsigned build; serial XCTest 49 tests, 4 assertion failures in 3 cases; host shutdown interrupted |
| [Zaryob/volk](https://github.com/Zaryob/volk) | fork of gnuradio/volk | open; fork; maintenance unverified | README.md / 0 | Not compiled/tested in this audit |
| [Zaryob/zaryob](https://github.com/Zaryob/zaryob) | not marked as a fork; see attribution | open; open; maintenance not established by metadata | README.md / 0 | Not compiled/tested in this audit |
| [Zaryob/zaryob.github.io](https://github.com/Zaryob/zaryob.github.io) | not marked as a fork; see attribution | open; open; maintenance not established by metadata | README.md / 1 | Jekyll build + 92-page local link check passed |
| [Zaryob/zfs_kitabi](https://github.com/Zaryob/zfs_kitabi) | not marked as a fork; see attribution | open; open; maintenance not established by metadata | README.md / 1 | Not compiled/tested in this audit |
| [9base/.github](https://github.com/9base/.github) | not marked as a fork; see attribution | open; maintained | profile/README.md / 0 | Not compiled/tested in this audit |
| [9base/80sgifgenerator](https://github.com/9base/80sgifgenerator) | fork of antoineMoPa/80sgifgenerator | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/AndroGarbage](https://github.com/9base/AndroGarbage) | not marked as a fork; see attribution | archived; educational | README.md / 1 | Not compiled/tested in this audit |
| [9base/archtrace](https://github.com/9base/archtrace) | fork of gems-uff/archtrace | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/bismon](https://github.com/9base/bismon) | fork of bstarynk/bismon | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/build-dependencies](https://github.com/9base/build-dependencies) | fork of open-license-manager/build-dependencies | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/chm2pdf](https://github.com/9base/chm2pdf) | fork of Arnoques/chm2pdf | archived; historical-downstream | README.md / 1 | Not compiled/tested in this audit |
| [9base/ClothSimulation](https://github.com/9base/ClothSimulation) | fork of johnBuffer/ClothSimulation | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/ConvartDataGenerate](https://github.com/9base/ConvartDataGenerate) | not marked as a fork; see attribution | archived; historical | README.md / 0 | Not compiled/tested in this audit |
| [9base/ConVarT_pipeline](https://github.com/9base/ConVarT_pipeline) | fork of thekaplanlab/ConVarT_pipeline | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/ConVarT_Web](https://github.com/9base/ConVarT_Web) | fork of thekaplanlab/ConVarT_Web | archived; historical-downstream | README.md / 0 | Not compiled/tested in this audit |
| [9base/examples](https://github.com/9base/examples) | fork of open-license-manager/examples | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/flowgen](https://github.com/9base/flowgen) | not marked as a fork; see attribution | archived; historical-downstream | README.md / 0 | Not compiled/tested in this audit |
| [9base/FlutterGarbage](https://github.com/9base/FlutterGarbage) | not marked as a fork; see attribution | archived; educational | README.md / 0 | Not compiled/tested in this audit |
| [9base/gdb-dashboard](https://github.com/9base/gdb-dashboard) | fork of cyrus-and/gdb-dashboard | open; working-copy | README.md / 0 | Not compiled/tested in this audit |
| [9base/gitolite](https://github.com/9base/gitolite) | fork of sitaramc/gitolite | archived; preserved | README.markdown / 0 | Not compiled/tested in this audit |
| [9base/jhalfs](https://github.com/9base/jhalfs) | fork of automate-lfs/jhalfs | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/jira_clone](https://github.com/9base/jira_clone) | fork of oldboyxx/jira_clone | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/jsbsim](https://github.com/9base/jsbsim) | fork of JSBSim-Team/jsbsim | open; working-copy | README.md / 0 | Not compiled/tested in this audit |
| [9base/kmon](https://github.com/9base/kmon) | not marked as a fork; see attribution | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/lcc-license-generator](https://github.com/9base/lcc-license-generator) | fork of open-license-manager/lcc-license-generator | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/libomxil-bellagio](https://github.com/9base/libomxil-bellagio) | not marked as a fork; see attribution | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/librsvg](https://github.com/9base/librsvg) | not marked as a fork; see attribution | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/licensecc](https://github.com/9base/licensecc) | fork of open-license-manager/licensecc | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/linux](https://github.com/9base/linux) | fork of torvalds/linux | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/lp2gh](https://github.com/9base/lp2gh) | fork of termie/lp2gh | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/moviepad](https://github.com/9base/moviepad) | not marked as a fork; see attribution | archived; educational | README.md / 0 | Not compiled/tested in this audit |
| [9base/MS-DOS](https://github.com/9base/MS-DOS) | fork of microsoft/MS-DOS | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/mxu11x0](https://github.com/9base/mxu11x0) | fork of Moxa-Linux/mxu11x0 | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/mysqlogin](https://github.com/9base/mysqlogin) | not marked as a fork; see attribution | archived; educational | README.md / 0 | Not compiled/tested in this audit |
| [9base/nvidia_stuff](https://github.com/9base/nvidia_stuff) | not marked as a fork; see attribution | archived; historical | README.md / 0 | Not compiled/tested in this audit |
| [9base/openrocket](https://github.com/9base/openrocket) | fork of openrocket/openrocket | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/PhotoGIMP](https://github.com/9base/PhotoGIMP) | fork of Diolinux/PhotoGIMP | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/qFlipper](https://github.com/9base/qFlipper) | fork of flipperdevices/qFlipper | open; maintained-downstream | README.md / 0 | Not compiled/tested in this audit |
| [9base/Rayban](https://github.com/9base/Rayban) | not marked as a fork; see attribution | archived; historical | README.md / 0 | Not compiled/tested in this audit |
| [9base/re3](https://github.com/9base/re3) | fork of VideogameSources/gta3-decomp-alt | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/rolling_cat](https://github.com/9base/rolling_cat) | not marked as a fork; see attribution | archived; educational | README.md / 0 | Not compiled/tested in this audit |
| [9base/SpaceCadetPinball](https://github.com/9base/SpaceCadetPinball) | fork of alula/SpaceCadetPinball | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/Tinkerboard2-buildroot](https://github.com/9base/Tinkerboard2-buildroot) | fork of TinkerBoard2/buildroot | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/Tinkerboard2-debian](https://github.com/9base/Tinkerboard2-debian) | fork of TinkerBoard2/debian | archived; preserved | readme.md / 0 | Not compiled/tested in this audit |
| [9base/Tinkerboard2-kernel](https://github.com/9base/Tinkerboard2-kernel) | fork of TinkerBoard2/kernel | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/Tinkerboard2-manifest](https://github.com/9base/Tinkerboard2-manifest) | fork of TinkerBoard2/manifest | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/Tinkerboard2-rkbin](https://github.com/9base/Tinkerboard2-rkbin) | fork of TinkerBoard2/rkbin | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/Tinkerboard2-uboot](https://github.com/9base/Tinkerboard2-uboot) | fork of TinkerBoard2/u-boot | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/Tinkerboard2Android-manifest](https://github.com/9base/Tinkerboard2Android-manifest) | fork of TinkerBoard2-Android/manifest | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/TLP](https://github.com/9base/TLP) | fork of linrunner/TLP | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/torshammer](https://github.com/9base/torshammer) | not marked as a fork; see attribution | archived; historical-downstream | README.md / 0 | Not compiled/tested in this audit |
| [9base/Veil](https://github.com/9base/Veil) | fork of Veil-Framework/Veil | archived; historical-downstream | README.md / 0 | Not compiled/tested in this audit |
| [9base/vlmcsd](https://github.com/9base/vlmcsd) | fork of Wind4/vlmcsd | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/VsftpdWeb](https://github.com/9base/VsftpdWeb) | fork of Tvel/VsftpdWeb | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/Web-GUI-for-stockfish-chess](https://github.com/9base/Web-GUI-for-stockfish-chess) | fork of antiproton/Web-GUI-for-stockfish-chess | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/wubi](https://github.com/9base/wubi) | not marked as a fork; see attribution | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/xdgpp](https://github.com/9base/xdgpp) | fork of WerWolv/xdgpp | archived; preserved | README.md / 0 | Not compiled/tested in this audit |
| [9base/yocto-poky](https://github.com/9base/yocto-poky) | fork of TinkerBoard2/yocto-poky | archived; preserved | README.md / 0 | Not compiled/tested in this audit |

## Backlog and review state

Twenty issues were opened in their relevant repositories and added to the public project with M0–M4 and priority fields. `Todo` means no accepted implementation yet; `In Progress` means work or a reviewable PR exists; `Done` requires the acceptance criteria to be met. Opening a PR is not completion or a claim of a merge.

- M0 / P0: [Publish the public repository inventory and evidence-based M0–M4 plan](https://github.com/Zaryob/zaryob/issues/4) — In Progress
- M1 / P0: [Replace the profile banner with a public project map](https://github.com/Zaryob/zaryob/issues/5) — In Progress
- M0 / P1: [Add an auditable index while preserving the existing 9base curation](https://github.com/9base/.github/issues/1) — In Progress
- M2 / P0: [Document security boundaries and verify the Meson backend build matrix](https://github.com/Zaryob/iksemel/issues/15) — In Progress
- M3 / P0: [Gate network use on TLS identity and downgrade rejection tests](https://github.com/Zaryob/iksemel/issues/16) — Todo
- M2 / P0: [Make parser safety and benchmark claims reproducible and bounded](https://github.com/Zaryob/iksemel-rs/issues/2) — In Progress
- M4 / P1: [Establish XML compatibility and equivalent-work performance coverage](https://github.com/Zaryob/iksemel-rs/issues/3) — Todo
- M2 / P0: [Record current parser and sanitizer evidence and correct download claims](https://github.com/Zaryob/imshark/issues/1) — In Progress
- M3 / P0: [Resolve verified release failures before publishing platform packages](https://github.com/Zaryob/imshark/issues/2) — Todo
- M2 / P0: [Publish a locally verified synthetic bundle pair and reproduction record](https://github.com/Zaryob/Performer/issues/7) — In Progress
- M3 / P1: [Measure live profiler accuracy and overhead on a suitable Linux host](https://github.com/Zaryob/Performer/issues/8) — Todo
- M2 / P0: [Wire the checked-in tests and entitlements into clean checkouts](https://github.com/Zaryob/Sift/issues/1) — In Progress
- M3 / P1: [Verify signed installation, widget sharing and AI fallback on devices](https://github.com/Zaryob/Sift/issues/2) — Todo
- M2 / P1: [Record synthetic tuner results and correct simulator test instructions](https://github.com/Zaryob/Pena/issues/1) — In Progress
- M3 / P1: [Gate a beta on real microphone and interruption validation](https://github.com/Zaryob/Pena/issues/2) — Todo
- M3 / P1: [Correct process-watching documentation and verify Windows timer behavior](https://github.com/Zaryob/CaffeVigil/issues/1) — In Progress
- M0 / P1: [Replace destructive remote installation with reviewed local dry runs and backups](https://github.com/Zaryob/dotfiles/issues/2) — In Progress
- M1 / P1: [Extend the existing project catalogue with current public tools](https://github.com/Zaryob/zaryob.github.io/issues/4) — In Progress
- M0 / P2: [Clarify historical model scope and runnable source instructions](https://github.com/Zaryob/LinkLayerModel/issues/2) — In Progress
- M4 / P2: [Review fork provenance, license gaps and maintenance commitments without churn](https://github.com/Zaryob/zaryob/issues/6) — Todo

## Pull requests

- [Zaryob/dotfiles: Make installation opt-in with dry runs and recoverable backups](https://github.com/Zaryob/dotfiles/pull/3) — open for review
- [Zaryob/iksemel: Fix GnuTLS dependency linking and document verified backend checks](https://github.com/Zaryob/iksemel/pull/17) — open for review
- [Zaryob/iksemel-rs: Bound parser and benchmark claims with local validation evidence](https://github.com/Zaryob/iksemel-rs/pull/4) — open for review
- [Zaryob/Performer: Add verified synthetic bundles and record actual local validation](https://github.com/Zaryob/Performer/pull/9) — open for review
- [Zaryob/Pena: Record synthetic tuner results and usable simulator test instructions](https://github.com/Zaryob/Pena/pull/3) — open for review
- [Zaryob/CaffeVigil: Describe actual timer behavior and source-build limitations](https://github.com/Zaryob/CaffeVigil/pull/2) — open for review
- [Zaryob/LinkLayerModel: Clarify historical model inputs and failed numerical smoke evidence](https://github.com/Zaryob/LinkLayerModel/pull/3) — open for review
- [Zaryob/zaryob.github.io: Extend the existing catalogue with current public projects](https://github.com/Zaryob/zaryob.github.io/pull/5) — open for review
- [Zaryob/Sift: Wire existing tests and App Group inputs with honest failure evidence](https://github.com/Zaryob/Sift/pull/3) — draft; exposed test/host failures remain
- [Zaryob/imshark: Record current sanitizer results and verified release limitations](https://github.com/Zaryob/imshark/pull/3) — open for review
- [Zaryob/zaryob: Replace the profile banner with an evidence-based public project map](https://github.com/Zaryob/zaryob/pull/7) — open for review
- [9base/.github: Add a public evidence index while preserving 9base curation](https://github.com/9base/.github/pull/2) — open for review
