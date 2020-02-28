---
title: Команда dotnet tool run
description: Команда dotnet tool run вызывает локальное средство.
ms.date: 02/14/2020
ms.openlocfilehash: 05b21c0f5ea86f4b99b220f556c61bf83f464114
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543830"
---
# <a name="dotnet-tool-run"></a>dotnet tool run

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 3.0 и более поздних версий

## <a name="name"></a>name

`dotnet tool run` — вызов локального средства.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet tool run <COMMAND NAME> 
dotnet tool run <-h|--help>
```

## <a name="description"></a>Описание

Команда `dotnet tool run` позволяет выполнить поиск по файлам манифеста средства, которые входят в область текущего каталога. При нахождении ссылки на указанное средство оно запускается. См. дополнительные сведения о [запуске локального средства](global-tools.md#invoke-a-local-tool).

## <a name="arguments"></a>Аргументы

- **`COMMAND_NAME`**

  Имя выполняемой команды в средстве.

## <a name="options"></a>Параметры

- **`-h|--help`**

  Выводит краткую справку по команде.

## <a name="example"></a>Пример

- **`dotnet tool run dotnetsay`**

  Запуск локального средства `dotnetsay`.

## <a name="see-also"></a>См. также

- [Средства .NET Core](global-tools.md)
