# Vortex — HvH client for Minecraft 1.21.11 (Fabric)

## Управление
- **Right Shift** — ClickGUI. ЛКМ вкл/выкл, ПКМ или `...` — настройки, СКМ — бинд (Backspace снимает).
- **Чат-команды** (префикс по умолчанию `.`, меняется в Client -> Prefix):
  - `.bind add "KillAura" "R"` — назначить бинд (кавычки необязательны)
  - `.bind remove "KillAura"` · `.bind list` · `.bind clear`
  - `.toggle KillAura` (или `.t`) · `.modules`
  - `.settings TargetStrafe` — показать настройки · `.set TargetStrafe Radius 3`
  - `.friend add Ник` (или наведись на игрока и `.friend add`) · `.friend remove|list|clear` — друзей не бьют
  - `.theme list` · `.theme Sunset` · `.config save|load` · `.help`

## Как получить .jar
### Вариант 1: GitHub Actions (без установки чего-либо)
1. Создай репозиторий на github.com (New repository).
2. Загрузи ВСЁ содержимое папки `vortex` в корень репозитория вместе со скрытой папкой `.github`
   (проще всего через git: `git init && git add . && git commit -m init && git branch -M main && git remote add origin <url> && git push -u origin main`).
3. Вкладка **Actions** -> `build` -> дождись зелёной галочки (3-6 минут).
4. Открой запуск -> внизу **Artifacts** -> `Vortex-jar` -> скачай zip -> внутри `vortex-1.0.0.jar`.

### Вариант 2: на своём ПК
Нужны JDK 21 и Gradle 9: `gradle clean build verifyModJar` -> `build/libs/vortex-1.0.0.jar`. The verification task checks that the final JAR contains the Fabric metadata, main class, and mixin config; it fails if the JAR is suspiciously small..

### Установка
Fabric Loader 0.18.2+ и Fabric API 0.141.3+1.21.11, jar в папку `mods`.
(Файл `vortex-1.0.0-sources.jar`, если появится рядом, ставить не нужно.)

## Шрифт и лицензия
HUD использует шрифт Inter (SIL OFL 1.1), лицензия лежит в `assets/vortex/font/INTER-LICENSE.txt`.
Выключить: Client -> CustomFont.
