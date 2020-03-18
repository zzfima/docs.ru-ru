---
ms.openlocfilehash: 85f50b221e7ecb1ebd6fa539894ab7aabed8d362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "67540121"
---
### <a name="install-the-global-tool"></a>Установка глобального средства

Ресурсы пакета следует установить в защищенном расположении с помощью параметра `--tool-path`. Это позволяет изолировать среду пользователя с ограниченным доступом от среды с повышенными правами.

```bash
sudo dotnet tool install PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

`/usr/local/share/dotnet-tools` создается с разрешением `drwxr-xr-x`. Если каталог уже существует, используйте команду `ls -l`, чтобы убедиться в том, что у пользователя с ограниченным доступом нет разрешения на изменение каталога. Если такое разрешение есть, запретите доступ с помощью команды `sudo chmod o-w -R /usr/share/dotnet-tools`.

### <a name="run-the-global-tool"></a>Запуск глобального средства

**Способ 1**. Используйте полный путь с sudo:

```bash
sudo /usr/local/share/dotnet-tools/TOOLCOMMAND
```

**Способ 2**. Добавьте символьную ссылку на средство (одна на средство):

```bash
sudo ln -s /usr/local/share/dotnet-tools/TOOLCOMMAND /usr/local/bin/TOOLCOMMAND
```

Запустите средство с помощью команды:

```bash
sudo TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a>Удаление глобального средства

```bash
sudo dotnet tool uninstall PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

Если вы добавили символьную ссылку, ее также нужно удалить:

```bash
sudo rm /usr/local/bin/TOOLCOMMAND
```
