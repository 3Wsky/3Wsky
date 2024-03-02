### Hi there 👋
<h1 align="center"> <a href="https://onetu.cn/"> <img src="https://readme-typing-svg.herokuapp.com/?lines=console.log(%22Hello%2C%20World!%22);三万天祝你天天愉快!&center=true&size=27"> </a> </h1>
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
          #  - public_access (default scope)
          # The following additional scopes may be required:
          #  - read:org      (for organization related metrics)
          #  - read:user     (for user related data)
          #  - read:packages (for some packages related data)
          #  - repo          (optional, if you want to include private repositories)
          token: ${{ secrets.METRICS_TOKEN }}

          # Options
          user: 3Wsky
          template: classic
          base: header, activity, community, repositories, metadata
          config_timezone: Asia/Shanghai
          plugin_followup: yes
          plugin_followup_archived: yes
          plugin_followup_sections: repositories
          plugin_isocalendar: yes
          plugin_isocalendar_duration: half-year
          plugin_pagespeed: yes
          plugin_pagespeed_url: 3Wsky.github.io
          plugin_people: yes
          plugin_people_limit: 24
          plugin_people_size: 28
          plugin_people_types: followers, following
          plugin_reactions: yes
          plugin_reactions_display: absolute
          plugin_reactions_limit: 200
          plugin_reactions_limit_discussions: 100
          plugin_reactions_limit_discussions_comments: 100
          plugin_reactions_limit_issues: 100
          plugin_people_types: followers, following
          plugin_stargazers: yes
          plugin_stargazers_charts: yes
          plugin_stargazers_charts_type: classic
          plugin_stargazers_days: 14
          plugin_tweets: yes
          plugin_tweets_limit: 2
          plugin_tweets_user: .user.twitter
