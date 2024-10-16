# kivy-build

Usage

```yml
name: CI - Android

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    permissions:
      contents: write
      pull-requests: write
      repository-projects: write 
    env:
      GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
    steps:
      - name : Test Build
        uses: QiubyZ/kivy-build@v1
        with:
          buildozer_cmd: |
            echo 'yes' | buildozer -v android debug
        
```
