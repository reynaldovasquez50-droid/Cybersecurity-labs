# Lab 05 — Security Dataset Filtering (Bash, PowerShell & jq)

## Overview
Applied command-line data filtering techniques across Bash and PowerShell to analyze a Kali Linux toolkit JSON dataset. Used grep, jq, and PowerShell's object-oriented pipeline to extract, count, and filter security tool data by category, name pattern, and description keywords.

## Tools Used
- Kali Linux terminal (Bash)
- PowerShell (via Kali Linux)
- grep — text search utility
- jq — command-line JSON processor
- head — file preview utility
- Dataset: kali_linux_toolkit_dataset.json

## What I Did

### Environment Setup
mkdir lab-05
cd lab-05
mv ~/Downloads/kali_linux_toolkit_dataset.json .
head kali_linux_toolkit_dataset.json

### Keyword Count with grep
Counted all entries containing "wireless" case-insensitive:
grep -ic "wireless" kali_linux_toolkit_dataset.json
Result: 99 matches

- -i flag: case-insensitive search
- -c flag: returns count instead of printing lines

### JSON Parsing with PowerShell
Extracted only the tool field from every entry:
Get-Content kali_linux_toolkit_dataset.json | ConvertFrom-Json | ForEach-Object { $_.tool }

- Get-Content: reads file as raw text
- ConvertFrom-Json: parses text into structured object
- ForEach-Object { $_.tool }: returns only the tool field per entry

Key insight: PowerShell treats data as objects while Bash treats data as text.

### Regex Filtering with jq
Listed all tools whose names begin with "air":
jq -r '.[] | select(.tool | test("^air"; "i")) | .tool' kali_linux_toolkit_dataset.json
Result: aircrack-ng, airmon-ng, airodump-ng, aireplay-ng

### Multi-Criteria Filter with jq
Searched for wireless tools related to password recovery:
jq -r '.[] | select(.category=="Wireless" and (.description | test("password"; "i"))) | .tool' kali_linux_toolkit_dataset.json
Result: Empty — no tools matched both criteria simultaneously.

An empty result is still a valid finding — it confirms absence of a condition, which matters in threat analysis.

### Dependency Troubleshooting
jq was not pre-installed. Resolved by:
sudo apt update
sudo apt install jq

## Key Takeaways
- grep -ic is the fastest way to count keyword occurrences across large text files
- PowerShell ConvertFrom-Json enables precise field-level extraction from JSON
- jq regex filtering enables surgical searches across structured security datasets
- An empty filter result is still valid — confirms absence of a condition
- Bash treats everything as text; PowerShell treats everything as objects=
