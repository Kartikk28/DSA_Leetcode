# DSA_Leetcode
### Hi there 


Updated on <!-- daily_update_placeholder -->
![LeetCode Stats](https://leetcard.jacoblin.cool/kartiksharma___?ext=heatmap&theme=dark)
name: Daily README refresh

on:
  schedule:
    - cron: '15 0 * * *'          # 00:15 UTC daily
  workflow_dispatch:              # Manual “Run workflow” button

jobs:
  update-readme:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Replace timestamp
        run: |
          dt=$(date -u "+%Y-%m-%d %H:%M UTC")
          sed -i "s/<!-- daily_update_placeholder -->.*/${dt} <!-- daily_update_placeholder -->/" README.md

      - name: Commit and push
        uses: stefanzweifel/git-auto-commit-action@v5
        with:
          commit_message: "chore: daily README refresh"
