<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/jennifer-language/jennifer/main/site/logo/jennifer-wordmark-dark.svg">
    <img src="https://raw.githubusercontent.com/jennifer-language/jennifer/main/site/logo/jennifer-wordmark.svg" alt="Jennifer" width="360">
  </picture>
</p>

# Jennifer - a batteries-included programming language

Jennifer is an interpreted language for real tools: 43 built-in libraries and
76 modules - SQL, JSON / YAML / TOML / XML, HTTP client and server, mail,
crypto, MQTT, S3, MCP and more - in **one self-contained static binary**, with
no runtime to install and no dependency tree to resolve. Its design is strict
and explicit: conditions must be `bool`, conversions are spelled out, names
never shadow, and an error says where it happened.

```jennifer
use io;
use strings;

def name as string init "world";
io.printf("hello, %s!\n", strings.upper($name));
```

**[jennifer-lang.dev](https://www.jennifer-lang.dev/)** - documentation,
examples and downloads. Linux is the supported platform; unsupported macOS and
Windows builds come with every
[release](https://github.com/jennifer-language/jennifer/releases).

## The project

| Repository | What it is |
|---|---|
| [`jennifer`](https://github.com/jennifer-language/jennifer) | The interpreter (Go, plus an embeddable TinyGo build), its built-in libraries and modules, and the docs |
| [`jvc`](https://github.com/jennifer-language/jvc) | The deck manager: resolves, pins and vendors decks into a project, and publishes them |
| [`registry`](https://github.com/jennifer-language/registry) | The deck registry: the index `jvc` resolves against, and its operator CLI |
| [`grimoire`](https://github.com/jennifer-language/grimoire) | A documentation site and a printable PDF from a directory of Markdown; builds every deck's manual. Plugins: [`grimoire-katex`](https://github.com/jennifer-language/grimoire-katex), [`grimoire-mermaid`](https://github.com/jennifer-language/grimoire-mermaid) |
| [`cantrip`](https://github.com/jennifer-language/cantrip) | Markdown slide decks: an HTML slideshow and a PDF from one file |
| [`website`](https://github.com/jennifer-language/website) | www.jennifer-lang.dev, served by a Jennifer program |
| [`deck-template`](https://github.com/jennifer-language/deck-template) | The starting point for a new deck, and the CI layer every deck shares |

## Official decks

Decks are Jennifer's packages. They are vendored into your project with
[jvc](https://jvc.jennifer-lang.dev/), never installed globally:

```sh
jvc add @jennifer/influxdb
```

```jennifer
import "@jennifer/influxdb/" as influxdb;
```

| Deck | What it does |
|---|---|
| [`@jennifer/discord`](https://github.com/jennifer-language/deck-discord) | Post messages to a Discord channel through a webhook |
| [`@jennifer/gotify`](https://github.com/jennifer-language/deck-gotify) | Push notifications to a Gotify server |
| [`@jennifer/influxdb`](https://github.com/jennifer-language/deck-influxdb) | InfluxDB 1.x, 2.x and 3.x: line-protocol writes, InfluxQL and Flux queries |
| [`@jennifer/oauthext`](https://github.com/jennifer-language/deck-oauthext) | Vendor OAuth2: Google and Microsoft presets, Google service accounts |
| [`@jennifer/prometheus`](https://github.com/jennifer-language/deck-prometheus) | Prometheus metrics in the text exposition format, and queries against its HTTP API |
| [`@jennifer/slack`](https://github.com/jennifer-language/deck-slack) | Post messages to Slack through an Incoming Webhook |
| [`@jennifer/statsd`](https://github.com/jennifer-language/deck-statsd) | StatsD over UDP: counters, gauges, timings and sets, with DogStatsD tags and batching |
| [`@jennifer/telegram`](https://github.com/jennifer-language/deck-telegram) | A Telegram Bot API client |

Every published deck, official or not, can be found in the official
[deck registry](https://registry.jennifer-lang.dev/browse), the index `jvc`
installs from. Community decks live at [Deckyard](https://github.com/deckyard):
API clients, file formats, science and more, each with a named maintainer.

## Demos

- [`demo-jsnake`](https://github.com/jennifer-language/demo-jsnake) - a
  multiplayer snake game for the Linux console, over UDP and TCP
- [`demo-micrograd`](https://github.com/jennifer-language/demo-micrograd) - a
  scalar reverse-mode autodiff engine

## Getting involved

Bug reports and pull requests are welcome in each repository. Report a
security problem privately to <security@jennifer-lang.dev>, not as a public
issue; the interpreter's
[SECURITY.md](https://github.com/jennifer-language/jennifer/blob/main/SECURITY.md)
says what a useful report holds.

Jennifer is licensed under LGPL-3.0-only.
