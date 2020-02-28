---
title: Учебник. Установка и использование глобального средства .NET Core
description: Узнайте, как устанавливать и использовать средство .NET в качестве глобального.
ms.date: 02/12/2020
ms.openlocfilehash: 65047af9d8a7f2fd4c1a07f65af3a6ddbf870c5d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543824"
---
# <a name="tutorial-install-and-use-a-net-core-global-tool-using-the-net-core-cli"></a>Учебник. Установка и использование глобального средства .NET Core с помощью интерфейса командной строки .NET Core

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий

В этом учебнике вы узнаете, как установить и использовать глобальное средство. Вы используете инструмент, созданный в [первом учебнике этой серии](global-tools-how-to-create.md).

## <a name="prerequisites"></a>Предварительные требования

* Выполните действия из [первого руководства этой серии](global-tools-how-to-create.md).

## <a name="use-the-tool-as-a-global-tool"></a>Использование средства в качестве глобального

1. Установите средство из пакета, выполнив команду [dotnet tool install](dotnet-tool-install.md) в папке проекта *botsay-\<name>* :

   ```dotnetcli
   dotnet tool install --global --add-source ./nupkg botsay-<name>
   ```

   Параметр `--global` настраивает в .NET Core CLI установку двоичных файлов средства в расположении по умолчанию, которое автоматически добавляется в переменную среды PATH.

   Параметр `--add-source` настраивает временное использование каталога *./nupkg* в качестве дополнительного источника пакетов NuGet. Вы присвоили пакету уникальное имя, которое будет найдено только в каталоге *./nupkg*, а не на сайте Nuget.org. 

   В выходных данных отображается команда, используемая для вызова средства и установленной версии:

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'botsay-<name>' (version '1.0.0') was successfully installed.
   ```

1. Вызовите средство:

   ```console
   botsay hello from the bot
   ```

   > [!NOTE]
   > Если эта команда не сработает, для обновления PATH может потребоваться открыть новый терминал.

1. Удалите средство, выполнив команду [dotnet tool uninstall](dotnet-tool-uninstall.md):

   ```dotnetcli
   dotnet tool uninstall -g botsay-<name>
   ```

## <a name="use-the-tool-as-a-global-tool-installed-in-a-custom-location"></a>Использование средства в качестве глобального средства, установленного в настраиваемом расположении

1. Установите средство из пакета.

   Windows:

   ```dotnetcli
   dotnet tool install --tool-path c:\dotnet-tools --add-source ./nupkg botsay-<name>
   ```

   В Linux или macOS.

   ```dotnetcli
   dotnet tool install --tool-path ~/bin --add-source ./nupkg botsay-<name>
   ```

   Параметр `--tool-path` настраивает в .NET Core CLI установку двоичных файлов средства в указанном расположении. Создать каталог, если он не существует. Этот каталог не добавляется автоматически в переменную среды PATH.

   В выходных данных отображается команда, используемая для вызова средства и установленной версии:

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'botsay-<name>' (version '1.0.0') was successfully installed.
   ```

1. Вызовите средство:

   Windows:

   ```console
   c:\dotnet-tools\botsay hello from the bot
   ```

   В Linux или macOS.

   ```console
   ~/bin/botsay hello from the bot
   ```

1. Удалите средство, выполнив команду [dotnet tool uninstall](dotnet-tool-uninstall.md):

   Windows:

   ```dotnetcli
   dotnet tool uninstall --tool-path c:\dotnet-tools botsay --add-source ./nupkg botsay-<name>
   ```

   В Linux или macOS.

   ```dotnetcli
   dotnet tool uninstall --tool-path ~/bin botsay-<name>
   ```

## <a name="troubleshoot"></a>Устранение неполадок

Если при выполнении учебника появляется сообщение об ошибке, см. статью [Устранение неполадок при использовании средства .NET Core](troubleshoot-usage-issues.md).

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы установили и использовали средство в качестве глобального. Чтобы установить и использовать то же средство в качестве локального перейдите к следующему руководству.

> [!div class="nextstepaction"]
> [Tutorial: Install and use a .NET Core local tool using the .NET Core CLI](local-tools-how-to-use.md) (Учебник. Установка и использование локального средства .NET Core с помощью NET Core CLI.)
