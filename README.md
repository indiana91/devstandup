# 🚀 DevStandup

[![Go Version](https://img.shields.io/badge/Go-1.21+-00ADD8?style=flat&logo=go)](https://go.dev/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Hacktoberfest](https://img.shields.io/badge/Hacktoberfest-2025-orange.svg)](https://hacktoberfest.com/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

> A beautiful CLI tool that generates intelligent standup reports from your Git activity, powered by Google Gemini AI.

DevStandup analyzes your Git commits and generates human-readable standup reports, perfect for daily standups, weekly reviews, or tracking your development progress. With AI-powered insights and a gorgeous terminal UI built with Charm libraries.


## ✨ Features

- 📊 **Smart Commit Analysis** - Automatically analyzes your Git commits across repositories
- 🤖 **AI-Powered Summaries** - Uses Google Gemini to generate intelligent, context-aware standup reports
- 🎨 **Beautiful TUI** - Stunning terminal interface built with Bubble Tea and Lipgloss
- 📅 **Flexible Time Ranges** - Generate reports for today, yesterday, this week, or custom date ranges
- 🔍 **Multi-Repo Support** - Scan multiple repositories at once
- 💾 **Export Options** - Save reports as Markdown, JSON, or plain text
- ⚙️ **Configurable** - Customize AI prompts, output formats, and more
- 🌈 **Syntax Highlighting** - Beautiful code diffs with Glamour rendering

## 🎯 Use Cases

- **Daily Standups** - Generate quick summaries for your team meetings
- **Weekly Reviews** - Create comprehensive activity reports for retrospectives
- **Progress Tracking** - Monitor your development velocity and patterns
- **Open Source Contributions** - Track contributions across multiple projects
- **Portfolio Building** - Document your coding journey

## 📦 Installation

### Using Go Install

```bash
go install github.com/indiana91/devstandup@latest
```

### Using Homebrew (macOS/Linux)

```bash
brew tap indiana91/devstandup
brew install devstandup
```

### From Source

```bash
git clone https://github.com/indiana91/devstandup.git
cd devstandup
go build -o devstandup ./cmd/devstandup
sudo mv devstandup /usr/local/bin/
```

### Download Binary

Download pre-built binaries from the [Releases](https://github.com/indiana91/devstandup/releases) page.

## 🚀 Quick Start

### 1. Set up your Gemini API Key

```bash
export GEMINI_API_KEY="your-api-key-here"
```

Or add it to your shell profile (~/.bashrc, ~/.zshrc):

```bash
echo 'export GEMINI_API_KEY="your-api-key-here"' >> ~/.zshrc
```

Get your free API key at [Google AI Studio](https://makersuite.google.com/app/apikey).

### 2. Generate your first standup

```bash
# Standup for today
devstandup

# Standup for yesterday
devstandup --since yesterday

# Standup for the last week
devstandup --since "7 days ago"

# Interactive mode with TUI
devstandup --interactive
```

## 📖 Usage

### Basic Commands

```bash
# Show today's standup
devstandup

# Specify a custom repository path
devstandup --repo /path/to/repo

# Scan multiple repositories
devstandup --repos ~/projects/repo1,~/projects/repo2

# Custom date range
devstandup --since "2025-10-01" --until "2025-10-07"

# Export to file
devstandup --output standup.md

# JSON output for automation
devstandup --format json > standup.json
```

### Advanced Options

```bash
# Custom AI prompt template
devstandup --prompt "Summarize as a haiku"

# Include only specific authors
devstandup --author "John Doe"

# Exclude merge commits
devstandup --no-merges

# Verbose output for debugging
devstandup --verbose

# Configuration file
devstandup --config ~/.devstandup.yaml
```

### Interactive Mode

Launch the beautiful TUI for an enhanced experience:

```bash
devstandup --interactive
```

Features in interactive mode:
- Navigate through commits with arrow keys
- Preview individual commit changes
- Filter commits by keyword or file
- Copy standup to clipboard
- Real-time AI summary generation

## ⚙️ Configuration

Create a config file at `~/.devstandup.yaml`:

```yaml
# Default configuration
gemini_api_key: "your-api-key"
default_since: "yesterday"
default_repo: "."
include_merges: false
output_format: "markdown"

# AI Configuration
ai:
  model: "gemini-1.5-pro"
  temperature: 0.7
  max_tokens: 1000
  system_prompt: |
    You are an expert at summarizing software development work.
    Create concise, professional standup reports.

# Output styling
styling:
  theme: "dracula"
  show_stats: true
  show_files: true
  max_commits_display: 20

# Repository scanning
repos:
  - ~/projects/work
  - ~/projects/personal
  - ~/opensource
```

## 🎨 Output Examples

### Markdown Output

```markdown
# Standup Report - October 2, 2025

## Summary
Focused on implementing user authentication and fixing critical bugs in the payment system.

## What I Did
- ✅ Implemented JWT authentication with refresh tokens
- ✅ Fixed payment processing bug affecting 5% of transactions
- ✅ Added comprehensive unit tests for auth module
- ✅ Updated API documentation

## Statistics
- 📝 12 commits
- ➕ 847 lines added
- ➖ 234 lines removed
- 📁 18 files changed

## Repositories
- payment-service (8 commits)
- auth-api (4 commits)
```

### JSON Output

```json
{
  "date": "2025-10-02",
  "summary": "Focused on implementing user authentication...",
  "commits": 12,
  "stats": {
    "additions": 847,
    "deletions": 234,
    "files_changed": 18
  },
  "repositories": [
    {"name": "payment-service", "commits": 8},
    {"name": "auth-api", "commits": 4}
  ]
}
```

## 🏗️ Architecture

```
devstandup/
├── cmd/
│   └── devstandup/          # CLI entry point
│       └── main.go
├── internal/
│   ├── git/                 # Git operations
│   │   ├── analyzer.go
│   │   └── repository.go
│   ├── ai/                  # Gemini AI integration
│   │   ├── client.go
│   │   └── prompts.go
│   ├── ui/                  # Bubble Tea TUI
│   │   ├── model.go
│   │   ├── views.go
│   │   └── styles.go
│   ├── formatter/           # Output formatters
│   │   ├── markdown.go
│   │   ├── json.go
│   │   └── text.go
│   └── config/              # Configuration management
│       └── config.go
├── pkg/
│   └── standup/             # Core standup logic
│       └── generator.go
├── docs/                    # Documentation
├── examples/                # Example configs
├── .github/                 # GitHub workflows
│   └── workflows/
└── scripts/                 # Build & release scripts
```

## 🤝 Contributing

We love contributions! DevStandup is a Hacktoberfest 2025 project and we welcome developers of all skill levels.

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

### Good First Issues

Check out issues labeled `good first issue` for beginner-friendly tasks!

### Areas We Need Help

- 🎨 UI/UX improvements
- 🐛 Bug fixes and testing
- 📖 Documentation
- 🌍 Internationalization
- 🔌 New integrations (GitLab, Bitbucket, etc.)
- ✨ New AI models support (Anthropic Claude, OpenAI GPT)

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

Built with amazing open-source libraries:
- [Bubble Tea](https://github.com/charmbracelet/bubbletea) - TUI framework
- [Lipgloss](https://github.com/charmbracelet/lipgloss) - Style definitions
- [Glamour](https://github.com/charmbracelet/glamour) - Markdown rendering
- [Cobra](https://github.com/spf13/cobra) - CLI framework
- [go-git](https://github.com/go-git/go-git) - Git operations

## 🌟 Star History

If you find this project useful, please consider giving it a star! ⭐

## 📧 Contact

- Issues: [GitHub Issues](https://github.com/indiana91/devstandup/issues)
- Discussions: [GitHub Discussions](https://github.com/indiana91/devstandup/discussions)

---

Made with ❤️ for Hacktoberfest 2025
