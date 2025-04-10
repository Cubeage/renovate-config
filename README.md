# Shared Renovate Configuration

This repository contains a unified Renovate configuration that can handle multiple technology stacks, including:
- Docker
- Android
- iOS
- Dart/Flutter
- React/React Native
- Vue
- PNPM
- Bun
- PHP
- Python

## Usage

Create a `.github/renovate.json` or `renovate.json` file in your project with the following content:

```json
{
  "extends": ["github>YOUR_USERNAME/renovate-config"]
}
```

> **Note:** Replace `YOUR_USERNAME` with your actual GitHub username or organization name.

## Key Features

- **Automatic Project Type Detection** - Configuration automatically detects your project type and applies appropriate rules
- **Weekend Updates** - Updates are scheduled for weekends to minimize weekday disruptions
- **Automatic Merging** - Minor and patch updates are automatically merged, saving time
- **Dependency Dashboard** - Provides a clear dashboard to manage all dependencies
- **Smart Grouping** - Related dependencies are grouped in the same PR
- **Specific Labels** - Each update type has specific labels for easy identification

## Configuration Details

### General Settings
- Timezone set to Europe/London
- Dependency updates scheduled for weekends
- Maximum of 2 PRs per hour, with a concurrent limit of 5 PRs
- Automatic merging of minor and patch version updates
- Major version updates are labeled as "breaking"

### Technology-Specific Settings

The configuration includes specific rules for various technologies:

#### Docker
- Uses digest pinning for enhanced security
- Automatically merges minor updates

#### Android/Gradle
- Groups Android-related dependencies
- Special handling for androidx and Google components

#### iOS
- Supports Swift and CocoaPods updates
- Properly groups iOS dependencies

#### Flutter/Dart
- Enables pub dependency management
- Ignores iOS and Android platform-specific directories

#### JavaScript/TypeScript
- Supports React, Vue, PNPM, and Bun
- Special handling for TypeScript type definitions
- Appropriate grouping of frontend framework dependencies

#### PHP
- Supports Composer package updates
- Special handling for Laravel and Symfony frameworks

#### Python
- Supports pip, pipenv, poetry, and other Python package managers
- Groups Django, Flask, and testing packages

## Customization

If you need to override certain settings for a specific project, you can add additional configuration in your project's `renovate.json`:

```json
{
  "extends": ["github>YOUR_USERNAME/renovate-config"],
  "schedule": ["every weekend"],
  "labels": ["dependencies", "custom-label"]
}
```

## Troubleshooting

If you encounter any issues, please check the Renovate logs or open an issue in this repository.