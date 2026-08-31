name: 🐍 Cyber Contribution Snake

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:

permissions:
  contents: write

jobs:
  generate:
    runs-on: ubuntu-latest

    steps:
      - name: 🐍 Generate Cyber Snake
        uses: Platane/snk@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
                      dist/cyber-snake-dark.svg?color_snake=%2300ff9c&color_dots=%2300110b,%23003322,%23006644,%2300aa77,%2300ff9c
                      dist/cyber-snake-light.svg?color_snake=%237c3aed&color_dots=%23f5f3ff,%23ddd6fe,%23a78bfa,%237c3aed,%234c1d95
      - name: 🚀 Deploy generated files
        uses: crazy-max/ghaction-github-pages@v5
        with:
          build_dir: dist
          target_branch: output
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
