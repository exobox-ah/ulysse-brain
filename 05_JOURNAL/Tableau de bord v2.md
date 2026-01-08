
```dataview
TABLE WITHOUT ID
	link(file.link, string(date)) as "Date",
	reveil as "⏰",
	coucher as "💤",
	deepworktime as "🎯",
	gamingtime as "🕹️",
	shallowworktime as "📝",
	choice(emom, "🟢","🔘") as "🏋️",
	choice(morningwalk, "🟢","🔘") as "🌅🚶‍➡️",
	choice(lunchwalk, "🟢","🔘") as "🕛🚶‍➡️",
	choice(magnesium, "🟢","🔘") as "Mg",
	choice(zinc, "🟢","🔘") as "Zn",
	choice(omega3, "🟢","🔘") as "Ω3"

FROM #journal
WHERE file.name != this.file.name AND file.folder = "05_JOURNAL/ENTRIES"
SORT date DESC
LIMIT 30
```

