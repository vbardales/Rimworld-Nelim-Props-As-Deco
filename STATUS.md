---
mod: Props as Deco
packageId: nelim.propsasdeco
repo: Rimworld-Nelim-Props-As-Deco
remote: https://github.com/vbardales/Rimworld-Nelim-Props-As-Deco.git
visibility: private            # public | private
detached: yes
workflow_stage: makeSources
licence: original              # original | open | alive | forbidden | silent
licence_at: "2026-10-28: patch-only, nothing copied from any source (Chi_XiangLu now patched in place, not owned); the Chinese source 2877536640 forbids republication of its assets only, nothing here carries them"
upstream_mod_remotes: N/A      # source mods are Workshop-only, no git repository found yet
settings_audit: unchecked      # not_applicable | complete | partial | passed | unchecked
localization: unchecked
translation_en: unchecked
translation_fr: unchecked
dependencies: unchecked
workshop: private item 3811383060 (PublishedFileId.txt)
published: no
tested_on: never
remaining:
  - "2026-10-28: unverified: 1.a duplicate check done with owner approval (Search-Workshop.sh, pattern SEX_Clutter|SEX_ClutterableSurface|Mlie.ColonistsDeco|DecoModExtension, *.xml, 9550 of 9552 folders, 843 lines): only the two engines, our own item 3811383060, our RimScent Extended (own defs) and Junkie Knick Knacks 3607387774 (bazoka81, adds its own clutter defs, not a patch of other mods' props) hold the tags. No equivalent mod found; one route only, not a proof of absence"
  - "2026-10-28: unverified: GitHub topics and settings of the private repo (privé: no social preview)"
  - "2026-10-28: unverified: the Chinese source declares v1.2 to v1.5 in LoadFolders.xml, no v1.6 block: confirm in game that RimWorld 1.6 falls back to v1.5 so Chi_XiangLu exists for the patch (TESTING.md scenario 1)"
  - "2026-10-28: unverified: six manual scenarios of TESTING.md never executed; no Pickle suite, no automated unit test project (no C#); Tests/Test-ChinesePatch.ps1 passes (44 static assertions)"
  - "2026-10-28: unverified: repository stays private until GitHub Support has purged the old commits (the forbidden Chinese texture and def sat in history until the fresh-history force push 585a660; unreachable objects may stay fetchable by SHA). Then: gh repo edit visibility public, topics rimworld, rimworld-mod, mod, social preview upload and social_preview_sha256. Workshop item 3811383060 (old name and description) is set public by the owner by hand"
  - "2026-10-28: unverified: settings audit not done (MOD_SETTINGS.md); no settings expected, absence of page and shortcut to confirm in sources"
protocols_read_sha: 43dd90d4b7873c500347fba1be01275a48d5795b
updated: 2026-10-28
---

# Props as Deco: status

Current state only: the front matter above is the source of truth, run lines go to `docs/runs/`.

Patch-only integrations of other mods' props into Knick Knacks (surfaces, 330 objects, plus the Chinese incense burner Chi_XiangLu patched in place) and Colonists' Deco (walls, 18 objects). No C#, no def, no asset of anyone else. Source and selection notes: `Docs/CHINESE_INTEGRATION.md`, `Docs/CHINESE_MANIFEST.json`, `Docs/SOURCES.csv`. Manual scenarios and static test: `TESTING.md`.

## Audit 2026-10-28

Audited from `preTest` (retired) down to `setupRepo`: no push, local history unrelated to `origin/main`, 1.d status mentions and 1.g English docs missing, `STATUS.md` off template. Then fixed the same day: histories reconciled by rebase onto `origin/main` (local content kept on every conflict) and pushed; `About.xml` name, author and `PERSONAL USE ONLY` paragraph, README title and paragraph, English `CHANGELOG.md`, `LICENSE` aligned with `Mod/LICENSE`, 1.a duplicate check done. `Check-Status`, `Check-ModBasics` and `Tests/Test-ChinesePatch.ps1` pass. Moved to `makeSources` (1.k).

On 2026-10-28 the owned copy of Chi_XiangLu and its texture (branch ChinesePrivate, licence forbidden, suffix prohibited) was replaced by a patch on the source mod's def, on the owner's go: the mod is patch-only again, licence original, name without suffix, no incompatibility with the source. Visibility unchanged (private). Seen below the current state: patch files under Mod/*/Patches/ carry French comments (English required in repo files, existing comments not rewritten).
