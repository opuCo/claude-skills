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

## Im Browser nutzen

Die Installation mit `/plugin` gilt nur lokal. Für Sitzungen im Browser trägst du den Marketplace und das Plugin in der `.claude/settings.json` des Repos ein, in dem du programmierst (`extraKnownMarketplaces` und `enabledPlugins`).
