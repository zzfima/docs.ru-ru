---
ms.openlocfilehash: dece035f443ff827a250ca1c1233b7651df7d108
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424709"
---
### <a name="install-the-global-tool"></a><span data-ttu-id="9b083-101">Установка глобального средства</span><span class="sxs-lookup"><span data-stu-id="9b083-101">Install the global tool</span></span>

<span data-ttu-id="9b083-102">Ресурсы пакета следует установить в защищенном расположении с помощью параметра `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="9b083-102">Package assets should be installed in a protected location using the `--tool-path` option.</span></span> <span data-ttu-id="9b083-103">Это позволяет изолировать среду пользователя с ограниченным доступом от среды с повышенными правами.</span><span class="sxs-lookup"><span data-stu-id="9b083-103">This separation avoids sharing a restricted user environment with an elevated environment.</span></span>

```bash
sudo dotnet tool install PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

<span data-ttu-id="9b083-104">`/usr/local/share/dotnet-tools` создается с разрешением `drwxr-xr-x`.</span><span class="sxs-lookup"><span data-stu-id="9b083-104">`/usr/local/share/dotnet-tools` will be created with permission `drwxr-xr-x`.</span></span> <span data-ttu-id="9b083-105">Если каталог уже существует, используйте команду `ls -l`, чтобы убедиться в том, что у пользователя с ограниченным доступом нет разрешения на изменение каталога.</span><span class="sxs-lookup"><span data-stu-id="9b083-105">If the directory already exists, use the `ls -l` command to verify the restricted user doesn't have permission to edit the directory.</span></span> <span data-ttu-id="9b083-106">Если такое разрешение есть, запретите доступ с помощью команды `sudo chmod o-w -R /usr/share/dotnet-tools`.</span><span class="sxs-lookup"><span data-stu-id="9b083-106">If so, use the `sudo chmod o-w -R /usr/share/dotnet-tools` command to remove the access.</span></span>

### <a name="run-the-global-tool"></a><span data-ttu-id="9b083-107">Запуск глобального средства</span><span class="sxs-lookup"><span data-stu-id="9b083-107">Run the global tool</span></span>

<span data-ttu-id="9b083-108">**Способ 1**. Используйте полный путь с sudo:</span><span class="sxs-lookup"><span data-stu-id="9b083-108">**Option 1** Use the full path with sudo:</span></span>

```bash
sudo /usr/local/share/dotnet-tools/TOOLCOMMAND
```

<span data-ttu-id="9b083-109">**Способ 2**. Добавьте символьную ссылку на средство (одна на средство):</span><span class="sxs-lookup"><span data-stu-id="9b083-109">**Option 2** Add the symbol link of the tool, once per tool:</span></span>

```bash
sudo ln -s /usr/local/share/dotnet-tools/TOOLCOMMAND /usr/local/bin/TOOLCOMMAND
```

<span data-ttu-id="9b083-110">Запустите средство с помощью команды:</span><span class="sxs-lookup"><span data-stu-id="9b083-110">And run with:</span></span>

```bash
sudo TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a><span data-ttu-id="9b083-111">Удаление глобального средства</span><span class="sxs-lookup"><span data-stu-id="9b083-111">Uninstall the global tool</span></span>

```bash
sudo dotnet tool uninstall PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

<span data-ttu-id="9b083-112">Если вы добавили символьную ссылку, ее также нужно удалить:</span><span class="sxs-lookup"><span data-stu-id="9b083-112">If you made a symbol link, you also need to remove it:</span></span>

```bash
sudo rm /usr/local/bin/TOOLCOMMAND
```