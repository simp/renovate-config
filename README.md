# Renovate Configuration

This repository contains common configuration for [Renovate](https://docs.renovatebot.com/).

## Presets

| Preset | Extends with | Purpose |
| --- | --- | --- |
| `default.json` | `github>simp/renovate-config` | Base configuration (recommended defaults, ignore paths) |
| `ruby.json` | `github>simp/renovate-config:ruby` | Gemfile / gemspec custom managers for Ruby projects |
| `puppet.json` | `github>simp/renovate-config:puppet` | `metadata.json` dependency ranges for Puppet modules (see caveat below) |

**Caveat for `puppet.json`:** correct range updates (keeping the lower bound while
raising the upper bound) require Renovate to honor `rangeStrategy` for custom
managers. Until that fix is released upstream, extending this preset will produce
range updates that drop the lower bound — don't extend it yet.
