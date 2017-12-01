---
title: "Проверять выходные опубликованные данные с dotnet vstest"
description: "Узнайте, как для выполнения тестов на выходе, опубликованных с помощью команды dotnet vstest."
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 3965e4ca-75b8-4969-b3af-ca993c397a15
ms.openlocfilehash: 217787d41a9da6000941ded6caaa4f44d124644b
ms.sourcegitcommit: 8a4f8e6a7f1341764abcd188a332cc28d1e2d8ec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="test-published-output-with-dotnet-vstest"></a>Проверять выходные опубликованные данные с dotnet vstest

Можно выполнять тесты на выходе, уже опубликованных с `dotnet vstest` команды. Это будет работать в xUnit MSTest и NUnit тестов. Просто DLL-файл, который был частью выходных опубликованных данных и выполните:
```
dotnet vstest <MyPublishedTests>.dll
```
где `<MyPublishedTests>` имя опубликованного тестового проекта.

### <a name="example-of-running-tests-on-a-published-dll"></a>Пример выполнения тестов для опубликованных DLL

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE] Примечание: Если приложение не предназначен для платформу `netcoreapp` можно выполнять с `dotnet vstest` команду путем передачи в целевой версии .NET framework с флагом framework. Например, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`. В Visual Studio 2017 г. обновления 5 нужную платформу определяется автоматически.

### <a name="related-topics"></a>См. также
- [Модульное тестирование с тестированием dotnet и xUnit](unit-testing-with-dotnet-test.md)
- [Модульное тестирование с тестированием dotnet и MSTest](unit-testing-with-mstest.md)
