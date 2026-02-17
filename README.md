<p align="center">
  <img src="assets/banner.svg" alt="agent-skills" width="640" />
</p>

A collection of [Agent Skills](https://agentskills.io) that give AI coding agents superpowers beyond code — starting with macOS Calendar and Reminders management.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## About

Agent Skills extend AI coding agents with real-world capabilities. Instead of being limited to editing files and running commands, your agent can interact with native macOS apps, schedule events, and handle tasks you'd normally do by hand.

Works with [Claude Code](https://claude.ai/code), [Cursor](https://cursor.com), [Gemini CLI](https://geminicli.com), [GitHub Copilot](https://github.com/features/copilot), and [other compatible agents](https://agentskills.io).

## Available Skills

| Skill | Description | Platform | Version |
|---|---|---|---|
| [macos-calendar](skills/macos-calendar/) | Create, list, and manage Apple Calendar events using natural language | macOS | 1.2.0 |
| [macos-reminders](skills/macos-reminders/) | Create, list, and manage Apple Reminders using natural language | macOS | 1.0.0 |

## Installation

Install all skills from this collection:

```bash
npx skills add lucaperret/agent-skills
```

Then ask your agent something like:

> "Schedule a team meeting next Tuesday at 2pm with a 10-minute reminder"

The agent will use the appropriate skill automatically.

## Requirements

- **macOS** with Calendar.app and Reminders.app
- `osascript` (ships with macOS) and `python3` (included with [Xcode Command Line Tools](https://developer.apple.com/xcode/resources/)) available in PATH

## Usage Examples

Once installed, just talk to your agent naturally.

### macOS Calendar

| You say | What happens |
|---|---|
| "Remind me to call the dentist in 2 days" | Creates a calendar event with an alert |
| "Set up a recurring standup every weekday at 9am" | Creates a recurring event with RRULE |
| "Block July 15 as a vacation day" | Creates an all-day event |
| "What calendars do I have?" | Lists all available calendars |

### macOS Reminders

| You say | What happens |
|---|---|
| "Remind me to buy milk" | Creates a reminder in the default list |
| "Add eggs and bread to my shopping list" | Creates reminders in the Shopping list |
| "High priority: submit the report by Friday" | Creates a flagged, high-priority reminder with a due date |
| "Show my work to-dos" | Lists incomplete reminders from the Work list |

## License

MIT - see [LICENSE](LICENSE) for details.
