# 🏥 Repo Health Action

[![GitHub Marketplace](https://img.shields.io/badge/GitHub-Action-blue?logo=github)](https://github.com/RahilAlam929/repo-health-action)
[![Release](https://img.shields.io/github/v/release/RahilAlam929/repo-health-action)](https://github.com/RahilAlam929/repo-health-action/releases)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

A lightweight, reusable GitHub Action that checks the basic health of a repository and generates a **health score + grade**.

## ✨ What it checks

| Check | Points |
|---|---:|
| 📄 README | 25 |
| ⚖️ LICENSE | 25 |
| ⚙️ GitHub Actions | 25 |
| 📁 Minimum files | 25 |
| **Total** | **100** |

## 🚀 Usage

Add this to your workflow:

```yaml
name: Repo Health

on:
  push:
  pull_request:

permissions:
  contents: read
  pull-requests: write

jobs:
  health:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Repo Health Check
        id: health
        uses: RahilAlam929/repo-health-action@v1

      - name: Show Result
        run: |
          echo "Health Score: ${{ steps.health.outputs.health-score }}/100"
          echo "Grade: ${{ steps.health.outputs.grade }}"
