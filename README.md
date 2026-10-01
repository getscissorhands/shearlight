# Shearlight Theme

A multi-purpose ScissorHands.NET theme for sites and blogs, inspired by Astro Starlight. Shearlight uses Razor views, responsive styling, light/dark mode, and sample content. No UI framework or JavaScript build step is required.

See the **[theme documentation](https://getscissorhands.app/docs/themes/)** for setup, configuration, component APIs, navigation, and customization.

## Prerequisites

- [.NET 10+ SDK](https://dotnet.microsoft.com/download/dotnet/10.0)
- [Visual Studio 2026](https://visualstudio.microsoft.com/) or [VS Code](https://code.visualstudio.com/) with [C# Dev Kit](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csdevkit)

## Theme Layout

```text
src/
├── assets/
│   ├── css/
│   │   └── theme.css
│   ├── images/
│   │   └── icons/
│   │       ├── chevron-down.svg
│   │       ├── globe.svg
│   │       ├── github.svg
│   │       ├── moon.svg
│   │       └── sun.svg
│   └── js/
│       └── theme.js
├── favicon.ico
├── theme.json
├── shearlight.csproj
├── _Imports.razor
├── MainLayout.razor
├── IndexView.razor
├── PostView.razor
├── PageView.razor
├── NotFoundView.razor
├── TagListView.razor
├── TagView.razor
└── Components/
    ├── LanguageSwitcher.razor
    ├── LocalizationMetadata.razor
    ├── LocalizationFallbackBanner.razor
    ├── PublicationBadges.razor
    └── NavigationItems.razor
```

## Local Preview

The sample needs a symbolic link at `sample/themes/shearlight` pointing to `src`, with the relative target `../../src`. This repository tracks the link; recreate it if it is missing.

If the link is missing, run one of the following from the repository root. Replace `shearlight` with the `Site:Theme` value in `sample/appsettings.json` if you renamed the theme.

```bash
# zsh/bash
mkdir -p sample/themes
ln -s ../../src sample/themes/shearlight
```

```powershell
# PowerShell
New-Item -ItemType Directory -Path ./sample/themes -Force
New-Item -ItemType SymbolicLink -Path ./sample/themes/shearlight -Target ../../src
```

Then build and preview from the repository root:

```bash
dotnet restore && dotnet build
cd sample
dotnet run -- --preview
```

Open `http://localhost:5000/`. The sample includes English, Korean, missing translations, and preview-only publication statuses. Stop preview before rebuilding Razor components.
