---
title: Проверка опубликованных выходных данных с помощью dotnet vstest
description: Узнайте, как протестировать опубликованные библиотеки (вместо исходного кода) с помощью команды dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.custom: seodec18
ms.openlocfilehash: 660b966c6d02353b855e5728094083042a561558
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126091"
---
# <a name="test-published-output-with-dotnet-vstest"></a>Проверка опубликованных выходных данных с помощью dotnet vstest

Чтобы проверить опубликованные выходные данные, выполните команду `dotnet vstest`. Эту команду можно использовать в проверках xUnit, MSTest и NUnit. Найдите DLL-файл, который является частью опубликованных выходных данных, и выполните эту команду:

```
dotnet vstest <MyPublishedTests>.dll
```

`<MyPublishedTests>` — имя опубликованного тестового проекта.

## <a name="example"></a>Пример

Приведенные ниже команды демонстрируют выполнение тестов с опубликованным DLL-файлом.

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> Примечание. Если приложение не предназначено для платформы `netcoreapp`, вы все равно можете выполнить команду `dotnet vstest`, передав требуемую версию .NET Framework с помощью флага платформы. Например, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`. В обновлении 5 для Visual Studio 2017 нужная платформа определяется автоматически.

## <a name="see-also"></a>См. также

- [Модульное тестирование с использованием dotnet test и xUnit](unit-testing-with-dotnet-test.md)
- [Модульное тестирование с использованием dotnet test и NUnit](unit-testing-with-nunit.md)
- [Модульное тестирование с использованием dotnet test и MSTest](unit-testing-with-mstest.md)
