# cct-project — издания

Тук се публикуват готовите версии на **cct-project**: команда и MCP сървър за Claude Code, които работят с проекти в Google Drive. Кодът е в частно репо; тук има само изданията и инсталаторите.

В това репо **няма** данни на организации, ключове или пароли. Организацията си идва от малък частен файл `cct-org-<домейн>.json`, който получаваш от IT.

## Инсталация

**macOS, ChromeOS (Linux терминал), Debian/Ubuntu**

```bash
curl -fsSL https://github.com/erida-ai/cct-project-releases/releases/latest/download/install.sh | bash
```

**Windows (PowerShell)**

```powershell
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
irm https://github.com/erida-ai/cct-project-releases/releases/latest/download/install.ps1 -OutFile $env:TEMP\cct-install.ps1
powershell -NoProfile -ExecutionPolicy Bypass -File $env:TEMP\cct-install.ps1
```

Инсталаторът не иска парола и администраторски права. Слага всичко в профила ти: Node.js 22+ (ако липсва), приложението, командата `cct-project`, Claude Code и MCP сървъра.

## Първо ползване: файл на организацията

След инсталацията отвори Claude Code и кажи „настрой cct-project“. Claude ще поиска файла на твоята организация от IT: **Drive линк** или път до вече изтеглен `cct-org-<домейн>.json`. Файлът не е публичен, затова се отваря браузърът: влез със служебния Google акаунт и файлът се сваля сам. След това влизаш в Google със служебния акаунт.

В терминал: `cct-project org add <Drive линк или път>`, после `cct-project init-auth --domain <домейн>`. На ChromeOS премести изтегления файл в *Linux files* и дай пътя му.

## Обновяване

`cct-project` проверява най-много веднъж на ден дали има нова версия и ти казва след някоя команда. Обновяваш с:

```bash
cct-project self-update
```

После рестартирай Claude Code. Проверката се изключва с променливата `CCT_NO_UPDATE_CHECK=1`.

## Какво има във всяко издание

| Файл | За какво е |
|---|---|
| `cct-project-vX.Y.Z.tar.gz` | приложението |
| `SHA256SUMS` | контролна сума; инсталаторът и `self-update` я проверяват преди да сложат нещо |
| `install.sh`, `install.ps1` | инсталаторите по-горе |

Списъкът с промените по версии е в бележките на всяко издание.

## Проблеми

Изпрати снимка на терминала на IT.
