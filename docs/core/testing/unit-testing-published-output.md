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
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="73ca2-103">Проверять выходные опубликованные данные с dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="73ca2-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="73ca2-104">Можно выполнять тесты на выходе, уже опубликованных с `dotnet vstest` команды.</span><span class="sxs-lookup"><span data-stu-id="73ca2-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="73ca2-105">Это будет работать в xUnit MSTest и NUnit тестов.</span><span class="sxs-lookup"><span data-stu-id="73ca2-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="73ca2-106">Просто DLL-файл, который был частью выходных опубликованных данных и выполните:</span><span class="sxs-lookup"><span data-stu-id="73ca2-106">Simply locate the DLL file that was part of your published output and run:</span></span>
```
dotnet vstest <MyPublishedTests>.dll
```
<span data-ttu-id="73ca2-107">где `<MyPublishedTests>` имя опубликованного тестового проекта.</span><span class="sxs-lookup"><span data-stu-id="73ca2-107">where `<MyPublishedTests>` is the name of your published test project.</span></span>

### <a name="example-of-running-tests-on-a-published-dll"></a><span data-ttu-id="73ca2-108">Пример выполнения тестов для опубликованных DLL</span><span class="sxs-lookup"><span data-stu-id="73ca2-108">Example of running tests on a published DLL</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE] <span data-ttu-id="73ca2-109">Примечание: Если приложение не предназначен для платформу `netcoreapp` можно выполнять с `dotnet vstest` команду путем передачи в целевой версии .NET framework с флагом framework.</span><span class="sxs-lookup"><span data-stu-id="73ca2-109">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="73ca2-110">Например, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="73ca2-110">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="73ca2-111">В Visual Studio 2017 г. обновления 5 нужную платформу определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="73ca2-111">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

### <a name="related-topics"></a><span data-ttu-id="73ca2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="73ca2-112">Related topics</span></span>
- [<span data-ttu-id="73ca2-113">Модульное тестирование с тестированием dotnet и xUnit</span><span class="sxs-lookup"><span data-stu-id="73ca2-113">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="73ca2-114">Модульное тестирование с тестированием dotnet и MSTest</span><span class="sxs-lookup"><span data-stu-id="73ca2-114">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
