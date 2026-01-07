
```dataview
TABLE WITHOUT ID
	link(file.link, string(date)) as "Date",
	sommeil_global as "Dodo 🌙",
	lever as "Réveil",
	choice(magnesium, "✅", "❌") as "Mg",
	choice(zinc_cuivre, "✅", "❌") as "Zn",
	choice(omega3, "✅", "❌") as "Ω3",
	energie as "Énergie ⚡",
	focus as "Focus 🎯",
	humeur as "Humeur 🙂"
FROM #journal
WHERE file.name != this.file.name AND file.folder = "05_JOURNAL/ENTRIES"
SORT date DESC
LIMIT 30
```

