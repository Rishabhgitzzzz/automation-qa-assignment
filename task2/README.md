# Task 2 — n8n API Integration Workflow

## Overview

This workflow fetches the top Node.js repositories from the GitHub API every 5 min using a Schedule Trigger.

The workflow:

1. Fetches the top repositories sorted by stars
2. Transforms and filters the top 5 repositories using a Code node
3. Uses an IF node to filter repositories with more than 1000 stars
4. Enriches repository data by fetching README information from the GitHub API
5. Sends formatted notifications to a Discord webhook

## APIs Used

- GitHub Search Repositories API
- GitHub Repository README API
- Discord Webhook API

## Error Handling

HTTP Request nodes were configured with "Continue On Fail" enabled to prevent silent workflow crashes.

## Technologies

- n8n
- GitHub REST API
- Discord Webhooks
- JavaScript (Code Node)

## Output

The workflow posts a digest of trending Node.js repositories to Discord including:

- Repository name
- Star count
- Description
- Repository URL
