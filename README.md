## Hello 欢迎来到我的Github主页
![](https://komarev.com/ghpvc/?username=your-hz64-username&color=green)

我会的
<span > <img src="https://img.shields.io/badge/-HTML5-E34F26?style=flat-square&logo=html5&logoColor=white" /> <img src="https://img.shields.io/badge/-CSS3-1572B6?style=flat-square&logo=css3" /> <img src="https://img.shields.io/badge/-JavaScript-oringe?style=flat-square&logo=javascript" /> </span>

# Visit https://github.com/lowlighter/metrics#-documentation for full reference
name: Metrics
on:
  # Schedule updates (each hour)
  schedule: [{cron: "0 * * * *"}]
  # Lines below let you run workflow manually and on each commit
  workflow_dispatch:
  push: {branches: ["master", "main"]}
jobs:
  github-metrics:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - uses: lowlighter/metrics@latest
        with:
          # Your GitHub token
          # The following scopes are required:
          #  - repo
          #  - public_access (default scope)
          #  - public_repo
          #  - read:project
          # The following additional scopes may be required:
          #  - read:org      (for organization related metrics)
          #  - read:user     (for user related data)
          #  - read:packages (for some packages related data)
          #  - repo          (optional, if you want to include private repositories)
          token: ${{ secrets.METRICS_TOKEN }}

          # Options
          user: hz64
          template: terminal
          base: header, activity, community, repositories, metadata
          config_timezone: Asia/Singapore
          plugin_projects: yes
          plugin_projects_limit: 4
          plugin_traffic: yes
