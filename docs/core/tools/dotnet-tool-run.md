---
title: Команда dotnet tool run
description: Команда dotnet tool run вызывает локальное средство.
ms.date: 02/14/2020
ms.openlocfilehash: a088cd0b7f4bba014234a8189a42a63aa6d88f4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847850"
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
- [Учебник. Установка и использование локального средства .NET Core с помощью интерфейса командной строки .NET Core](local-tools-how-to-use.md)
