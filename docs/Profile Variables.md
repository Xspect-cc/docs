---
title: Profile Variables
summary: "*Last updated: August 2025*"
sidebar_title: Profile Variables
new: false
order: 0
external_links:
  "Xspect Main site": https://xspect.cc/
---

## Enhance your profile bio with dynamic variables. These variables will be automatically replaced with their values whenever someone views your profile.

### How to Use Variables

To use a variable in your bio, type the variable name surrounded by double curly braces:
```jinga2
{{ variable_name }}
```

### Using Line Breaks

You can add line breaks to your bio by using the pipe symbol (|) between text:
```js
First line | Second line | Third line
```

You can also use the newline variable:
```jinga
First line {{ newline }} Second line
```

### Examples

```jinga
Current time: {{ current_time }}
```

```jinga
I joined on {{ join_date }} | That's {{ days_since_join }} days ago!
```

### Available Variables

| Variable | Description | Premium Required |
|----------|-------------|------------------|
| `{{ current_time }}` | Current Time | No |
| `{{ join_date }}` | Join Date | No |
| `{{ random_quote }}` | Random Quote | Yes |
| `{{ current_date }}` | Current Date | No |
| `{{ days_since_join }}` | Days Since Join | No |
| `{{ random_number }}` | Random Number | No |
| `{{ current_year }}` | Current Year | No |
| `{{ newline }}` | New Line | No |
| `{{ quote_of_day }}` | Quote of the Day | No |

