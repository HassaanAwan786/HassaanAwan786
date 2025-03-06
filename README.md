
## Most Used Languages

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=HassaanAwan786&layout=compact&theme=radical&hide_border=true)

# 
## Languages Used

![Dart](https://img.shields.io/badge/Dart-79.75%25-blue)
![Java](https://img.shields.io/badge/Java-9.27%25-orange)
![C++](https://img.shields.io/badge/C++-5.71%25-red)
![CMake](https://img.shields.io/badge/CMake-2.73%25-green)
![HTML](https://img.shields.io/badge/HTML-1.28%25-yellow)
![C#](https://img.shields.io/badge/C%23-1.26%25-purple)

name: Update README

on:
  schedule:
    - cron: '0 0 * * *' # Runs daily at midnight
  push:
    branches:
      - main

jobs:
  update-readme:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v2

      - name: Generate language stats
        uses: anuraghazra/github-readme-stats@main
        with:
          username: ${{ github.repository_owner }}
          layout: compact
          theme: radical
          hide_border: true

      - name: Commit and push changes
        run: |
          git config --global user.name "GitHub Actions"
          git config --global user.email "actions@github.com"
          git add README.md
          git commit -m "Update README with latest language stats"
          git push
