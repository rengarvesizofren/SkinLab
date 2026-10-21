# SkinLab

A Windows workspace for organizing and managing League of Legends skin mods.

> This source snapshot is for League of Legends. It does not include CS2 skin functionality.

## What is included

A minimal entry point for the League mod workflow, build requirements, and project layout. The supplied documentation describes mod folders and profiles, search/filtering, batch operations, random selection, mod package import/export, BIN delta support, and a Topaz mod fixer. The project also contains a Windows WPF application, a C# helper, and a Rust game-data overlay helper.

## Project layout

- ModLoader/ — Windows WPF desktop application.
- cslol-go/ — C# helper project.
- game-data-overlay/ — Rust helper source, lockfile, and tests.
- 	ests/ModPkg.Tests/ — .NET test project.
- Tools/ — supporting executables and conversion data.
- docs/ — BIN delta and Topaz notes.
- README-upstream.md — original README preserved from the supplied archive.

## Requirements and build

Windows is required for the WPF application. ModLoader targets 
et10.0-windows7.0; cslol-go targets .NET 8. The Rust helper requires stable Rust and Cargo.

`powershell
dotnet restore ModLoader.sln
dotnet test tests/ModPkg.Tests/ModPkg.Tests.csproj --configuration Release
dotnet build ModLoader.sln --configuration Release
cargo test --locked --manifest-path game-data-overlay/Cargo.toml
`

The supplied workflow includes these checks. They were not run because .NET SDK and Cargo are unavailable in this environment.

## Installation and configuration

The archive includes a setup executable and supporting binaries. They are preserved unchanged, but were not run or independently verified. See README-upstream.md for the project’s documented release workflow. The application Settings view allows selection of the local League game path. No portable sample settings file is included; avoid committing machine-specific paths. See docs/bin-deltas.md for BIN delta guidance.

## Limitations and troubleshooting

League updates may change game data formats and mod compatibility. Live-game compatibility was not verified. If game data cannot be located, confirm the League installation path in Settings. If Rust builds fail, verify Rust stable/Cargo and dependency access. For package issues, review docs/bin-deltas.md. Review publisher game-integrity policies before using game modifications.

## License and bundled executables

Review LICENSE.txt before changing or redistributing the project; it contains project-specific terms and third-party notices. Bundled executables were not run or independently verified.

## Suggested GitHub topics

`league-of-legends`, `skin-mods`, `mod-manager`, `game-data

The 155 MB setup executable is kept in the separate publication package ZIP and omitted from this Git repository copy because it exceeds GitHub's 100 MB per-file limit. If redistribution is authorized, distribute it as a GitHub Release asset after validating it.

