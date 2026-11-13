# claude-skills

Sammel-Repo für eigene Claude Skills. Alle Skills stecken im Plugin `meine-skills`.

## Enthaltene Skills

| Skill | Wofür |
|---|---|
| `wochenbericht` | Macht aus Stichpunkten einen einseitigen Wochenbericht |

## Neuen Skill anlegen

1. Lege einen Ordner `skills/<name>/` mit einer Datei `SKILL.md` an. Sie beginnt so:

   ```markdown
   ---
   name: <name>
   description: Was der Skill tut. Use when <wann Claude ihn nutzen soll>.
   ---

   # Titel

   Anweisungen für Claude.
   ```

2. Trage den Ordner in `.claude-plugin/marketplace.json` unter `skills` ein, zum Beispiel `"./skills/<name>"`. Ohne diesen Eintrag wird der Skill nicht geladen.
3. Ergänze die Tabelle oben.
4. Committe und pushe.

## Installieren

Einmalig in Claude Code:

```
/plugin marketplace add opuCo/claude-skills
```

```
/plugin install meine-skills@meine-skills
```

Danach gelten die Skills in jedem Repo auf deinem Rechner. Claude wählt sie anhand der `description` aus, du kannst sie auch mit `/<name>` aufrufen.

## Aktualisieren

Nach neuen Skills im Repo:

```
/plugin marketplace update meine-skills
```

## Überall nutzen (Browser und Handy-App)

Die Installation mit `/plugin` gilt nur lokal. Browser und Handy-App starten Claude Code in einer Cloud-Sitzung, die deine lokale Installation nicht sieht. Dort stehen Plugins aus der Plugin-Bibliothek der Organisation in claude.ai bereit.

Dieses Repo ist die Quelle, die Veröffentlichung ist der Weg dorthin:

1. Öffne die Claude-App oder ein Terminal auf deinem Rechner. Aus einer Cloud-Sitzung geht das Veröffentlichen nicht.
2. Hole den aktuellen Stand dieses Repos und bitte Claude, das Plugin an die Organisation zu veröffentlichen. Den Ordner mit `.claude-plugin/plugin.json` nimmt Claude als Plugin-Ordner.
3. Bestätige die Rückfrage. Je nach Einstellung der Organisation prüft ein Administrator das Plugin zuerst.
4. Nach jeder Änderung wiederholst du die Veröffentlichung. Erhöhe vorher die `version` in `.claude-plugin/plugin.json`.

Wer in der Organisation ist, sieht die veröffentlichten Skills ebenfalls. Lege hier nichts Persönliches oder Vertrauliches ab.

Ersatzweg für ein einzelnes Repo: Trage den Marketplace und das Plugin in dessen `.claude/settings.json` ein (`extraKnownMarketplaces` und `enabledPlugins`). Das wirkt nur in Sitzungen zu diesem Repo.
