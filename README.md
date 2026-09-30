# cct-project — издания

Тук се публикуват готовите версии на **cct-project**: команда и MCP сървър за Claude Code, които работят с проекти в Google Drive. Кодът е в частно репо; тук има само изданията и инсталаторите.

В това репо **няма** данни на организации, ключове или пароли. Организацията си идва от малък частен файл `cct-org-<домейн>.json`, който получаваш от IT.

## Инсталация

Трябва ти файлът на твоята организация (`cct-org-<домейн>.json`) от IT. Без него се инсталира само приложението.

**macOS, ChromeOS (Linux терминал), Debian/Ubuntu**

```bash
curl -fsSL https://github.com/erida-ai/cct-project-releases/releases/latest/download/install.sh | bash -s -- --org ~/Downloads/cct-org-<домейн>.json
```

**Windows (PowerShell)**

```powershell
irm https://github.com/erida-ai/cct-project-releases/releases/latest/download/install.ps1 -OutFile $env:TEMP\cct-install.ps1
powershell -NoProfile -ExecutionPolicy Bypass -File $env:TEMP\cct-install.ps1 -Org $HOME\Downloads\cct-org-<домейн>.json
```

Инсталаторът не иска парола и администраторски права. Слага всичко в профила ти: Node.js 22+ (ако липсва), приложението, командата `cct-project`, Claude Code, MCP сървъра и Google вход със служебния ти акаунт. Пускането му наново е безопасно. За втора организация го пусни с нейния файл.

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
