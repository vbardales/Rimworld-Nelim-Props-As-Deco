---
mod: Props as Deco
packageId: nelim.propsasdeco
repo: Rimworld-Nelim-Props-As-Deco
remote: https://github.com/vbardales/Rimworld-Nelim-Props-As-Deco.git
visibility: public             # public | private
detached: yes
workflow_stage: settings[1.0.0]
licence: original              # original | open | alive | forbidden | silent
licence_at: "2026-10-28: patch-only, nothing copied from any source (Chi_XiangLu now patched in place, not owned); the Chinese source 2877536640 forbids republication of its assets only, nothing here carries them"
upstream_mod_remotes: N/A      # source mods are Workshop-only, no git repository found yet
settings_audit: unchecked      # not_applicable | complete | partial | passed | unchecked
localization: unchecked
translation_en: unchecked
translation_fr: unchecked
dependencies: declared         # optional only: loadAfter + IfModActive, no modDependencies (see Dependencies 2026-10-28)
workshop: private item 3811383060 (PublishedFileId.txt)
published: no
tested_on: never
remaining:
  - "2026-10-28: unverified: 4.a packageId of Rabbie The Moonrabbit race (runnelatki.rabbieracemod, Workshop 1837246563) not verifiable: its folder is absent from the local Workshop content; the id is kept from the earlier audit"
  - "2026-10-28: unverified: 1.a duplicate check done with owner approval (Search-Workshop.sh, pattern SEX_Clutter|SEX_ClutterableSurface|Mlie.ColonistsDeco|DecoModExtension, *.xml, 9550 of 9552 folders, 843 lines): only the two engines, our own item 3811383060, our RimScent Extended (own defs) and Junkie Knick Knacks 3607387774 (bazoka81, adds its own clutter defs, not a patch of other mods' props) hold the tags. No equivalent mod found; one route only, not a proof of absence"
  - "2026-10-28: unverified: GitHub topics and settings of the private repo (privé: no social preview)"
  - "2026-10-28: unverified: the Chinese source declares v1.2 to v1.5 in LoadFolders.xml, no v1.6 block: confirm in game that RimWorld 1.6 falls back to v1.5 so Chi_XiangLu exists for the patch (TESTING.md scenario 1)"
  - "2026-10-28: unverified: six manual scenarios of TESTING.md never executed; no Pickle suite, no automated unit test project (no C#); Tests/Test-ChinesePatch.ps1 passes (64 static assertions)"
  - "2026-10-28: unverified: repository made public after delete and recreate with a fresh history (old commits with the Chinese texture no longer resolve on GitHub); topics set. Left: GitHub social preview upload of Mod/About/Preview.png and social_preview_sha256 (required from writeDocs); Workshop item 3811383060 (old name and description) set public by the owner by hand, description updated by CI or the Steam page"
  - "2026-10-28: unverified: settings audit not done (MOD_SETTINGS.md); no settings expected, absence of page and shortcut to confirm in sources"
social_preview_sha256: ba5bb37afd0ddd0eb683d1273bbdcbf14c938fa5ff6dfc26e35a524ebbbb48a9
protocols_read_sha: 7a1282c60cc188fb02a1bfaceec231e0f8d53669
updated: 2026-10-28
---

# Props as Deco: status

Current state only: the front matter above is the source of truth, run lines go to `docs/runs/`.

Patch-only integrations of other mods' props into Knick Knacks (surfaces, 330 objects, plus the Chinese incense burner Chi_XiangLu patched in place) and Colonists' Deco (walls, 18 objects). No C#, no def, no asset of anyone else. Source and selection notes: `Docs/CHINESE_INTEGRATION.md`, `Docs/CHINESE_MANIFEST.json`, `Docs/SOURCES.csv`. Manual scenarios and static test: `TESTING.md`.

## Audit 2026-10-28

Audited from `preTest` (retired) down to `setupRepo`: no push, local history unrelated to `origin/main`, 1.d status mentions and 1.g English docs missing, `STATUS.md` off template. Then fixed the same day: histories reconciled by rebase onto `origin/main` (local content kept on every conflict) and pushed; `About.xml` name, author and `PERSONAL USE ONLY` paragraph, README title and paragraph, English `CHANGELOG.md`, `LICENSE` aligned with `Mod/LICENSE`, 1.a duplicate check done. `Check-Status`, `Check-ModBasics` and `Tests/Test-ChinesePatch.ps1` pass. Moved to `makeSources` (1.k).

makeSources to code[1.0.0] (same day): `Art/ModIcon-source.png` delivered by the owner; `Mod/About/ModIcon.png` regenerated (128x128, 30 KB) and `ModIcon.ico` current. First `Preview-source.png` failed the palette rule (Vmean 0.254, vignette, grain, upright front-elevation furniture, a readable face); the owner replaced it from a new prompt: Measure-Palette now gives Vmean 0.359 (>= 0.30), 2 hue families, vivid 40.9 %, dominant 92 %; flat sprites, no readable face (settlers from behind), table with six props identifiable at 268 px by eye. Old source stays in git history. Art/ holds sources, outputs and the provisional echo-concept.png (echo is redone at mountPreview). Preview regenerated from the new source: its panel and echo overlap the left half of the table, to settle at mountPreview with the gallery. The owner validated this Preview on 2026-10-28 and it was uploaded as the GitHub social preview the same day (og:image on repository-images.githubusercontent.com, sha256 in the front matter).

On 2026-10-28 the owned copy of Chi_XiangLu and its texture (branch ChinesePrivate, licence forbidden, suffix prohibited) was replaced by a patch on the source mod's def, on the owner's go: the mod is patch-only again, licence original, name without suffix, no incompatibility with the source. Repository public since 2026-10-28. Seen below the current state: patch files under Mod/*/Patches/ carry French comments (English required in repo files, existing comments not rewritten).

## Dependencies 2026-10-28 (declareDependencies, revision after a567f19)

No hard dependency: no code, and every integration is a patch guarded by its own LoadFolders branch (IfModActive) or by PatchOperationFindMod (Colonists' Deco). Declared in About.xml as loadAfter only, 21 ids: Ludeon.RimWorld, the 15 surface sources, the 3 wall sources (ucp.walldecorations, unagi.funiture.build.window, runnelatki.rabbieracemod), the two engines Knick Knacks (VaguelySexual.ModPackageId.GoesHere, id as the mod itself ships it) and Mlie.ColonistsDeco, Dajian.ChiTeaditional.Expanded (Chi_XiangLu patched in place) and nelim.halloweenmonstermash (Halloween Monster Mash Renew). Ids read from each source About.xml in the local Workshop (all match, case aside), except Rabbie (see remaining) and the Halloween mod, read from its local repository. Defect fixed: LoadFolders named nelim.halloweenmonstermashrenew, which is not the packageId, so the Halloween batch never loaded; id corrected and added to loadAfter, ATTRIBUTION heading renamed. No incompatibleWith (the duplicate-def clash with the Chinese source went away with the owned def). No DLC branch, supportedVersions 1.6 only. No animal (ANIMALS.md n/a). Tests/Test-ChinesePatch.ps1 now asserts every IfModActive id is in loadAfter (64 assertions).
