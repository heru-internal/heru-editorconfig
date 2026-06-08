# heru-editorconfig

A shared [EditorConfig](https://editorconfig.org/) configuration for Heru projects.
It keeps formatting — indentation, line endings, charset, and .NET/C# coding
conventions — consistent across editors, IDEs, and contributors.

## What it covers

| Scope                                     | Settings                                                                                         |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **All files** (`*`)                       | 2-space indent, LF line endings, UTF-8, trailing whitespace trimmed, final newline inserted      |
| **Shell scripts** (`*.sh`)                | 4-space indent                                                                                   |
| **Batch & PowerShell** (`*.bat`, `*.ps1`) | 4-space indent, CRLF line endings                                                                |
| **Markdown** (`*.md`)                     | Trailing whitespace preserved (for hard line breaks)                                             |
| **C#** (`*.cs`, `*.vb`)                   | 4-space indent, CRLF, plus a full set of .NET/C# coding conventions and naming rules (see below) |

The C# section encodes the team's Roslyn analyzer preferences: `this.`
qualification, `var` usage, expression-bodied members, pattern matching,
brace requirements (`csharp_prefer_braces = true:error`), modifier ordering,
PascalCase types/members, `I`-prefixed interfaces, and more.

## Usage

EditorConfig is supported natively by most editors and IDEs (Visual Studio,
Rider, VS Code with the EditorConfig extension, JetBrains IDEs, Vim, etc.).

Drop the `.editorconfig` file at the **root** of your repository (it is marked
`root = true`, so no parent configs are merged in):

```sh
curl -o .editorconfig https://raw.githubusercontent.com/heru-internal/heru-editorconfig/refs/heads/main/.editorconfig
```

Or copy it in manually and commit it. Once present, your editor applies these
rules automatically to matching files.

## Customizing

Project-specific overrides can live in a more deeply nested `.editorconfig`
within the same repo — EditorConfig applies the closest matching rule. Prefer
changing this shared file for org-wide conventions, and reserve local overrides
for genuinely project-specific needs.

## Reference

- [EditorConfig specification](https://spec.editorconfig.net/)
- [.NET code-style rules](https://learn.microsoft.com/dotnet/fundamentals/code-analysis/code-style-rule-options)
