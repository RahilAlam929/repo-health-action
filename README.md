# 🏥 Repo Health Check

A simple reusable GitHub Action that checks the basic health of a repository.

## ✨ Checks

- ✅ README.md
- ✅ LICENSE
- ✅ GitHub Actions workflow
- ✅ Minimum number of files
- 📊 Health score out of 100

## 🚀 Usage

```yaml
name: Repository Health

on:
  push:
  pull_request:

jobs:
  health:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Repo Health Check
        uses: RahilAlam929/repo-health-action@v1
