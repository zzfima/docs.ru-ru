---
title: Проверка опубликованных выходных данных с помощью dotnet vstest
description: Узнайте, как протестировать опубликованные выходные данные с помощью команды dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 2f750a8bb0907069691c4a4491beeb4b1733df29
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="test-published-output-with-dotnet-vstest"></a>Проверка опубликованных выходных данных с помощью dotnet vstest

Чтобы проверить опубликованные выходные данные, выполните команду `dotnet vstest`. Эту команду можно использовать в проверках xUnit, MSTest и NUnit. Найдите DLL-файл, который является частью опубликованных выходных данных, и выполните эту команду:

```
dotnet vstest <MyPublishedTests>.dll
```

`<MyPublishedTests>` — это имя опубликованного тестового проекта.

## <a name="example-of-running-tests-on-a-published-dll"></a>Пример тестирования опубликованного DLL-файла

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> Примечание. Если приложение не предназначено для платформы `netcoreapp`, вы все равно можете выполнить команду `dotnet vstest`, передав требуемую версию .NET Framework с помощью флага платформы. Например, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`. В обновлении 5 для Visual Studio 2017 нужная платформа определяется автоматически.

## <a name="see-also"></a>См. также
 [Модульное тестирование C# в .NET Core с использованием dotnet test и xUnit](unit-testing-with-dotnet-test.md)  
 [Модульное тестирование кода C# с использованием MSTest и .NET Core](unit-testing-with-mstest.md)  
