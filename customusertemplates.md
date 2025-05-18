---
title: Custom UGC Templates [BETA]
layout: home
---

# Creating Custom Profile Templates for Xspect [BETA]

## Overview
This guide will help you create custom profile templates for Xspect. Custom templates allow you to personalize how your profile page looks when users visit `/u/<username>`.

## Getting Started

### Template Basics
Templates in Xspect use the Jinja2 templating engine with HTML, CSS and JavaScript. Your template will receive specific variables containing user information.

### Available Variables
Your template will have access to the following variables:

- `username`: The user's username
- `bio`: User biography text
- `pfpurl`: URL to the user's profile picture
- `bgurl`: URL to the user's background image
- `discord`: Discord username (if set)
- `email`: Email address (if set)
- `telegram`: Telegram handle (if set)
- `bio_music_link`: Music link in bio (if set)
- `theme`: Theme ID number
- `github`, `twitter`, `instagram`, `linkedin`: Social media usernames
- `github_link`, `twitter_link`, `instagram_link`, `linkedin_link`: Full social media URLs
- `is_premium`: Boolean indicating premium status
- `is_helper`, `is_bughunter`, `is_og`, `is_developer`: Badge status booleans
- `total_views`: Total profile view count
- `daily_views`: Profile views in the last 24 hours
- `profile_effect`, `mouse_effect`, `bg_effect`: Applied visual effects
- `custom_badge_name`, `custom_badge_icon`, `custom_badge_type`: Custom badge information

## Template Structure

A basic template structure can be found <a href="/basictemplate.html">here </a>
