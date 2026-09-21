# Changelog

## 1.1.0 — Special tier (26.3 only)
- **Special tier:** a new purple tier for large collections (All Terracotta, All Wool, All Stone…). It has an ornate border with gem corners and filigree, and a stacked-blocks seal. It works exactly like the other tiers and is available in the Issue form and as `tier:"special"`.
- **Existing permits:** unaffected, since tiers are pack-owned data.
- **26.2 build:** stays at 1.0.0 without the Special tier. When a 26.2 server upgrades, install the 26.3 v1.1.0 packs.

## 1.0.0 — Production release
- **26.2 build:** a separate build for Minecraft 26.2 (data 107.1, resources 88.0) with item modifiers using the pre-26.3 `function` field. Otherwise identical.
- **Permit models:** permits are 3D cards in hand, on the ground and in item frames, with a crest watermark back and a raised wax seal. The inventory icon keeps the flat artwork.
- **Category emblems:** eight emblems (food, building, redstone, transport, weapons, armor, resources, decoration), chosen by `custom_model_data` and layered with a composite model. Other categories show no emblem.
- **Audit log:** a pack-wide log of the last 500 events, with an Audit Log admin screen. Subject, officer, reset and revoke-all actions are recorded alongside permit events.
- **Migration:** registry schema 2, migrated automatically with the audit log backfilled from permit histories. Pre-1.0 physical permits are rebuilt in place when their holder's inventory changes.
- **Tests:** the suite now covers reissue superseding a copy, and the audit log. Added `test/give_all_emblems`.
- **Admin help:** `admin/help` lists every function.
- **Free-form subjects:** subjects are free text chosen when issuing, so a permit can cover a single item or a collection (All Wood, All Wool). `admin/create` takes a `category` for the emblem. The pre-filled subject catalog, the Subjects screen and `admin/subject/*` are removed; example subjects exist only in the tests. Stored catalogs are cleaned up automatically.
- **Issue form:** now opens straight from the admin screen, with no chat line.
- **Resource pack update:** item frames and dropped permits use a thicker card with a clearly raised seal, so the 3D shape reads face-on. Held permits are unchanged.

## 0.7.x — Interface
- **Screens:** every screen is built by functions, so no dialog files are shipped and `/reload` always applies changes.
- **Access:** permits are the only player entry point, and menu buttons require holding one. Officers get an Administration button.
- **Admin UI:** Issue, Registry, Look Up, Transfer, Reissue, Revoke, Subjects and Danger Zone (revoke all, reset). Added `admin/uninstall`.
- **Icons and chat:** UI icons use atlas sprites, and trigger feedback text is blanked.
- **Permit wording:** "{Subject} Permit", "{Tier} Permit", and a "Trading Standards" footer.

## 0.6.0 — Player interaction
- Right-click verification, My Permits, Present to nearby players, and the verification report.

## 0.5.x — Core engine
- Generic permit schema, persistent registry, PERMIT-0001 IDs, macro-based creation, dynamic item generation.
- Validation (not_permit, corrupted, unknown, revoked, expired, wrong_holder, outdated), transfer, reissue and revocation with history.
- Adapted to 26.3 formats: item modifier `type` field, `/item modify` for name lookup, and unquoted text output.

## 0.1.0 — Visual proof of concept
- Diamond Permit item, model and texture.
