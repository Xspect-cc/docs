---
title: Home
layout: home
---

# Creating Custom Profile Templates for Xspect

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

A basic template structure looks like this:
```html
<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>{{ username }}'s Profile</title>
      <style>
         /* Your CSS here */
         body {
         font-family: 'Arial', sans-serif;
         background-color: #121212;
         color: #ffffff;
         margin: 0;
         padding: 0;
         }
         .profile-container {
         max-width: 800px;
         margin: 30px auto;
         padding: 20px;
         border-radius: 10px;
         background-color: #1e1e1e;
         }
         .profile-header {
         display: flex;
         align-items: center;
         margin-bottom: 20px;
         }
         .profile-pic {
         width: 100px;
         height: 100px;
         border-radius: 50%;
         object-fit: cover;
         }
         .username {
         margin-left: 20px;
         font-size: 24px;
         font-weight: bold;
         }
         .bio {
         margin-bottom: 20px;
         line-height: 1.6;
         }
         .stats {
         display: flex;
         gap: 10px;
         margin-bottom: 20px;
         }
         .stat {
         background-color: #2a2a2a;
         padding: 8px 12px;
         border-radius: 5px;
         font-size: 14px;
         }
         .social-links {
         display: flex;
         gap: 15px;
         }
         .social-link {
         color: #ffffff;
         text-decoration: none;
         }
         .social-link:hover {
         text-decoration: underline;
         }
      </style>
   </head>
   <body>
      <div class="profile-container">
         <div class="profile-header">
            <img src="{{ pfpurl }}" alt="{{ username }}" class="profile-pic">
            <h1 class="username">{{ username }}</h1>
         </div>
         <div class="bio">
            {{ bio }}
         </div>
         <div class="stats">
            <div class="stat">Views: {{ total_views }}</div>
            <div class="stat">Today: {{ daily_views }}</div>
            {% if is_premium %}
            <div class="stat">Premium User</div>
            {% endif %}
         </div>
         <div class="social-links">
            {% if discord %}
            <a href="#" class="social-link">Discord: {{ discord }}</a
            {% endif %}
            {% if github %}
            <a href="{{ github_link }}" class="social-link" target="_blank">GitHub</a>
            {% endif %}
            {% if twitter %}
            <a href="{{ twitter_link }}" class="social-link" target="_blank">Twitter</a>
            {% endif %}
            {% if instagram %}
            <a href="{{ instagram_link }}" class="social-link" target="_blank">Instagram</a>
            {% endif %}
         </div>
      </div>
   </body>
</html>
```
