<!-- NIUX REMOTE PROJECT SHOWCASE -->

# Happy Desktop — Remote Project Management

**Community contribution by [NiuX](https://github.com/neo19482)**

> Independent community fork of
> [Happy Desktop](https://github.com/slopus/happy-desktop).
> Not an official Happy release.

[View source code](https://github.com/neo19482/happy-desktop/tree/integration/remote-project-management) |
[Official Pull Request #82](https://github.com/slopus/happy-desktop/pull/82)

## Resumen ejecutivo

Esta contribución amplía Happy Desktop para administrar proyectos
alojados en una instancia remota de Happy Agent directamente desde
la interfaz de macOS.

### Funcionalidades incorporadas

- Crear proyectos y directorios remotos.
- Importar carpetas existentes.
- Acceder a la clonación de repositorios Git desde el menú Proyectos.
- Archivar proyectos y eliminar sus directorios físicos, previa confirmación.
- Admitir nombres con Unicode, mayúsculas, espacios y caracteres habituales.
- Conservar el acceso a los proyectos y conversaciones existentes.

### Arquitectura

**Happy Desktop → Happy Agent API → Sistema de archivos remoto**

La implementación utiliza tres componentes principales:

| Componente | Responsabilidad |
|---|---|
| `AppHappyAgentView.tsx` | Interfaz, menús y confirmaciones |
| `happyAgentClient.ts` | API, operaciones remotas y comprobaciones |
| `happyAgentWorkspaceStore.ts` | Estado y ciclo de vida de proyectos |

### Validaciones realizadas

- TypeScript: correcto en la versión original y en la rama oficial integrada.
- Creación de proyectos y directorios remotos: verificada.
- Archivado y eliminación física de un proyecto descartable: verificados.
- Sincronización de conversaciones macOS ↔ iPhone: verificada.
- Integración Git con la rama oficial: sin conflictos.

**Seguridad:** la eliminación utiliza comprobaciones restrictivas,
pero todavía requiere auditoría de seguridad y pruebas automatizadas.
Se recomienda una API dedicada de Happy Agent para operaciones
destructivas antes de su incorporación oficial.

## English summary

This community contribution extends Happy Desktop with remote
project lifecycle management through an existing Happy Agent.

Features include remote project creation, directory import,
access to Git cloning, project archival and confirmed physical
directory deletion, with support for flexible project names.

Functional tests were completed on macOS ARM64 with Happy Agent
0.4.110, including bidirectional conversation synchronization
with iOS.

The implementation has been integrated with the upstream main
branch and passes TypeScript validation.

**Status:** Proof of concept submitted as
[upstream PR #82](https://github.com/slopus/happy-desktop/pull/82).
Destructive operations require additional security review.

---

## Original Happy Desktop documentation

The following documentation belongs to the original Happy Desktop
project and is retained for attribution and reference.

---

<div align="center">

<h1>Any Model. Your Subscription.<br><em>Happy Harness.</em></h1>

<p>Orchestrate Claude, Codex, Grok, Gemini, and more in one app</p>

<p>Free and open source</p>

</div>

https://github.com/user-attachments/assets/b3580704-f9e0-441e-80be-3f83f6a08ab5

<p align="center">
<a href="https://happy.engineering/#download"><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/slopus/happy-desktop/main/.github/download-desktop-dark.svg"><img width="212" height="39" alt="Download Desktop for macOS, Windows, and Linux" src="https://raw.githubusercontent.com/slopus/happy-desktop/main/.github/download-desktop-light.svg" /></picture></a>
</p>

<p align="center">
<a href="https://apps.apple.com/us/app/happy-codex-claude-code-app/id6748571505"><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/slopus/happy-desktop/main/.github/app-store-rating-dark.svg"><img width="150" height="56" alt="Download on the App Store. Rated 4.9 stars from 1,000+ ratings" src="https://raw.githubusercontent.com/slopus/happy-desktop/main/.github/app-store-rating-light.svg" /></picture></a>&nbsp;&nbsp;&nbsp;<a href="https://play.google.com/store/apps/details?id=com.ex3ndr.happy"><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/slopus/happy-desktop/main/.github/google-play-rating-dark.svg"><img width="150" height="56" alt="Get it on Google Play. Rated 5.0 stars from 3.1k+ reviews" src="https://raw.githubusercontent.com/slopus/happy-desktop/main/.github/google-play-rating-light.svg" /></picture></a>
</p>

## What you get

1. **Any model: Claude, Codex, Grok, Gemini, and more.** Gemini runs through
   Antigravity, and OpenCode or any Agent Client Protocol agent plugs in as a
   harness. Give every task the model that fits, and delegate to subagents on
   any of them.
2. **Reuse your subscriptions.** Sign in with the Claude, Codex, and Grok
   subscriptions you already pay for; Antigravity, OpenCode, and ACP agents
   keep their own logins. Happy adds a harness, not another bill.
3. **Open source MIT.** It runs on your own hardware and your projects stay
   ordinary folders. Read the code, fork it, ship your own build.
4. **End-to-end encrypted mobile app.** Left your desk? The same sessions are
   already on your phone, and what moves between your devices is encrypted.
5. **Natively multiplayer.** Invite a colleague or a friend into the session.
   You both watch the same agent work, and either of you can steer it.

#### Resources

<p align="center">
<a href="https://happy.engineering/">Website</a> · <a href="https://happy.engineering/welcome/">Documentation</a> · <a href="https://discord.gg/fX9WBAhyfD">Discord</a> · <a href="https://github.com/slopus/happy-desktop/blob/main/DEVELOPMENT.md">Development guide</a> · <a href="https://github.com/slopus/happy-desktop/blob/main/LICENSE">MIT License</a>
</p>

## How Happy fits together

| Repository                                                                            | What it is                                                                 |
| ------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| [slopus/happy](https://github.com/slopus/happy)                                       | The mobile app (iOS, Android, web), the original CLI, and the relay server |
| **[slopus/happy-desktop](https://github.com/slopus/happy-desktop)** ← this repository | **The desktop app for macOS, Windows, and Linux**                          |
| [slopus/happy-agent](https://github.com/slopus/happy-agent)                           | Happy Agent, the open-source agent runtime the desktop app runs on         |
| [slopus/slopus.github.io](https://github.com/slopus/slopus.github.io)                 | The website and docs at happy.engineering                                  |

## Original Happy CLI

The original CLI wraps the Claude Code and Codex harnesses directly in your
terminal and lets you continue from your phone.

For multi-model sessions and teams, move to the desktop app and Happy Harness.

```sh
npm install -g happy

# Start Claude Code
happy claude

# Or start Codex
happy codex
```
