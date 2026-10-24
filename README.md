# OpenXcom Extended — Nintendo Switch (Homebrew порт)

Это **homebrew-порт** открытой и бесплатной игры **OpenXcom Extended (OXCE) 8.7.1** на **Nintendo Switch**.

Порт сделан на основе полностью **открытого исходного кода** проекта [OpenXcom Extended](https://github.com/MeridianOXC/OpenXcom_OXCE) (лицензия **GPLv3**). Мы лишь адаптировали его под Switch (devkitPro/libnx/SDL2), добавили управление геймпадом/тачскрином и собрали в `.nro`.

> ⚠️ **В этом репозитории НЕТ файлов игр.** Оригинальные данные X-COM
> (UFO Defense / Terror from the Deep) добавляются отдельно — это ваши
> легально приобретённые копии игр. Репозиторий содержит только исходный код
> порта и готовый `.nro`.

---

## Что это

- **OpenXcom Extended 8.7.1** — расширенная версия классического X-COM.
- Поддерживает **UFO: Enemy Unknown / X-Com: UFO Defense** и **Terror from the Deep**.
- Запуск через Homebrew (Atmosphere/hekate), режим полной памяти.

## Возможности

- ✅ Полноценный OXCE 8.7.1 (геоскейп, бои, базы, исследования, производство).
- ✅ Управление геймпадом + тачскрином.
- ✅ Стандартные моды (с русскими описаниями) и свои моды через `user/mods`.
- ✅ Быстрые сохранения, экранная клавиатура.
- ✅ Собственная иконка порта.

---

## Управление

| Кнопка | Действие |
|---|---|
| Левый стик | курсор |
| Правый стик | прокрутка |
| **A** | подтверждение / левая кнопка мыши |
| **B** | правая кнопка мыши |
| **L / R** | предыдущий / следующий юнит |
| **ZL / ZR** | быстрое сохранение / загрузка |
| **X / Y** | `M` / `I` |
| **L3 / R3** | Ctrl / переключение яркости |
| Minus / Plus | Esc / Backspace |
| D-pad | PageUp/Down, Q/E |
| Тачскрин | тап = ЛКМ, 2 пальца = ПКМ |

---

## Установка

1. Скопируйте `openxcom.nro` в `sdmc:/switch/openxcom/`.
2. Добавьте свои данные игры:
   - `sdmc:/switch/openxcom/UFO/` — UFO Defense;
   - `sdmc:/switch/openxcom/TFTD/` — Terror from the Deep.
3. Папки `common/` и `standard/` возьмите из полного набора (или из этого репозитория).
4. Настройки: `sdmc:/config/openxcom/options.cfg` (создаются автоматически).
5. Запуск — через **Homebrew Menu** в режиме **полной памяти** (зажать `R`).
6. В игре `Options → Mods`: включите мастер-мод **xcom1** или **xcom2**.

---

## Скачать (Releases)

- **`openxcom.nro`** — только игра (для обновления).
- **`OpenXcomNX_8.7.1_NakedDeath_SD_v5.zip`** — полный набор: NRO + данные `common/standard` + структура папок (без игровых `UFO/TFTD`, их добавляете сами).

---

## Сборка из исходников

Требуется **devkitPro** (devkitA64 + libnx + switch-portlibs) и **MSYS2**.

```bash
source /etc/profile.d/devkit-env.sh
export PATH="$DEVKITPRO/devkitA64/bin:$DEVKITPRO/tools/bin:$PATH"
export PKG_CONFIG_LIBDIR="$DEVKITPRO/portlibs/switch/lib/pkgconfig"

# SD-вариант (данные на карте)
BUILD=build/oxce-sd NX_EMBED_ROMFS=OFF bash scripts/build_openxcom_switch.sh

# RomFS-вариант (данные внутри NRO)
BUILD=build/oxce-romfs NX_EMBED_ROMFS=ON bash scripts/build_openxcom_switch.sh
```

---

## Лицензия и авторство

- **OpenXcom Extended (OXCE)** — GPLv3 ([исходники](https://github.com/MeridianOXC/OpenXcom_OXCE)).
- **OpenXcom** — GPLv3 (<https://openxcom.org>).
- **SDL2 / libnx / devkitPro** — соответствующие лицензии.
- **Порт для Switch: NakedDeath.**

Это свободное программное обеспечение; вы можете распространять и изменять его в соответствии с GPLv3.
