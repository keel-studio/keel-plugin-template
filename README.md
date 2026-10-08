# keel plugin template

Start a new [keel](https://github.com/MiladNalbandi/keel-v2) plugin from this repo: press **Use this template** on GitHub.

> **Status: early.** The plugin SDK and the build come with keel 0.15–0.20 ([the plan](https://github.com/MiladNalbandi/keel-v2/tree/main/docs/plugins)). This repo shows the
> layout and the manifest now, so plugin repos look the same from the start.

A plugin can have up to five parts. All are optional; keep only what you need.

```
keel-plugin.yml   the manifest: name, version, what it needs, its parts, its permissions
engine/           Python package for keel's engine: actions, agent tools (MCP), hooks
api/              Kotlin, a thin Spring Boot jar: endpoints, Inbox cards, connections
web/              React pages and slots, built as one ES module (index.js)
content/          workflows, agents, skills, stacks, KeelBot commands
migrations/       V1__init.sql …: its own tables, with its own history
```

## Rules

- Every name starts with your plugin's id: actions `example:do`, events `example.done`, agent tools `example_read`,
  tables `example_items`.
- Use only keel's plugin SDK, never keel's internal code.
- No install scripts. keel unpacks the files and loads them when it starts.
- Ask only for the permissions you need. keel shows them before install.

## Release

A tag `v0.1.0` builds `example-0.1.0.kplug`, signs it, and makes a GitHub release (the workflow comes with the SDK).
Then add your plugin to [keel-marketplace](https://github.com/MiladNalbandi/keel-marketplace).

## License

MIT
