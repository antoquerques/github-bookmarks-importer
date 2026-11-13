# GitHub Bookmarks Importer

A single page tool that reads Markdown files from a public GitHub repository 
and turns the links inside them into a bookmarks file that you can import into your browser.

It works with any browser that imports bookmarks from an HTML file (Chrome, Firefox,
Edge, Brave, Opera). No dependencies, no build step.

## Usage

1. Open `index.html` in your browser.
2. Paste the URL of a public repository, like `https://github.com/owner/repository`.
3. Click "Read repository" and wait for the summary.
4. Download the generated file and import it from your browser's bookmarks manager.

## How it works

The tool uses the default branch of the repository and reads every `.md` file in it.

- Folders and files become bookmark folders, and headings (`#`, `##`, ...) become subfolders.
- Both `[title](url)` links and plain `http(s)://` URLs are picked up.
- Images, badges, code blocks and inline code are ignored.
- Each URL is imported only once, even if it appears in several files.
- Files are downloaded from `raw.githubusercontent.com`, so an import only makes two requests to the GitHub API.

Everything runs in the browser, nothing is sent to any server other than GitHub.

## Limitations

- Public repositories only.
- Very large repositories can't be read, because GitHub truncates their file list.
- The tool creates a file. It doesn't change your bookmarks directly.

## License

MIT, see [LICENSE](LICENSE).
