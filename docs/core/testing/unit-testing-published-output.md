---
title: Проверка опубликованных выходных данных с помощью dotnet vstest
description: Узнайте, как протестировать опубликованные библиотеки (вместо исходного кода) с помощью команды dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.custom: seodec18
ms.openlocfilehash: 93b2e1a433b5d5b9694257d4d12e47d9107f4cd7
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117021"
---
# <a name="test-published-output-with-dotnet-vstest"></a>Проверка опубликованных выходных данных с помощью dotnet vstest

Чтобы проверить опубликованные выходные данные, выполните команду `dotnet vstest`. Эту команду можно использовать в проверках xUnit, MSTest и NUnit. Найдите DLL-файл, который является частью опубликованных выходных данных, и выполните эту команду:

```dotnetcli
dotnet vstest <MyPublishedTests>.dll
```

`<MyPublishedTests>` — имя опубликованного тестового проекта.

## <a name="example"></a>Пример

Приведенные ниже команды демонстрируют выполнение тестов с опубликованным DLL-файлом.

```dotnetcli
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> Примечание. Если приложение не предназначено для платформы `netcoreapp`, вы все равно можете выполнить команду `dotnet vstest`, передав требуемую версию .NET Framework с помощью флага платформы. Например, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`. В обновлении 5 для Visual Studio 2017 нужная платформа определяется автоматически.

## <a name="see-also"></a>См. также

- [Модульное тестирование C# в .NET Core с использованием dotnet test и xUnit](unit-testing-with-dotnet-test.md)
- [Модульное тестирование с использованием dotnet test и xUnit](unit-testing-with-nunit.md)
- [Модульное тестирование кода C# с использованием MSTest и .NET Core](unit-testing-with-mstest.md)
