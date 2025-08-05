# 📚 Project: Book Reading Tracker CLI

## 🔧 Core Commands

| Command        | Description |
|----------------|-------------|
| `add`          | Add a new book (title, author, start date) |
| `list`         | List all books, showing title, author, and status |
| `update`       | Update reading progress or status (e.g. "completed") |
| `delete`       | Remove a book from the tracker |
| `search`       | Search by title or author |

---

## 📦 Book Fields

Each book record might include:

- `Title` (string, required)
- `Author` (string, required)
- `Pages` (int, optional)
- `PagesRead` (int, optional)
- `Status` (enum/string: "not started", "reading", "completed")
- `StartDate` (optional, string or time.Time)
- `CompletedDate` (optional)
- `Notes` (optional string)

Recommended storage format: **JSON**

---

## 🧱 Suggested CLI Usage

```bash
$ go run main.go add "The Hobbit" --author="J.R.R. Tolkien" --pages=310

$ go run main.go list
1. [reading] The Hobbit by J.R.R. Tolkien (Pg: 100/310)
2. [not started] The Pragmatic Programmer by Andy Hunt

$ go run main.go update 1 --pagesRead=150 --status=reading

$ go run main.go delete 2

$ go run main.go search --author="Tolkien"
```

---

## ✨ Stretch Features (Optional)

- Sort books by progress, date started, or status
- Export list to CSV or Markdown
- Track total pages read this month/year
- Show reading streaks
- Sync with a cloud service or REST API (long term idea)

---

## 🧰 Constraints

Use only standard Go libraries for:

- CLI parsing (`os.Args`, `flag`)
- File I/O (`os`, `encoding/json`)
- Dates (`time`)
- Data handling (slices, maps)
