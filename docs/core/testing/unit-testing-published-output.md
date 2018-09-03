---
title: Проверка опубликованных выходных данных с помощью dotnet vstest
description: Узнайте, как протестировать опубликованные выходные данные с помощью команды dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.openlocfilehash: e99000996f5dfa9f9d4f9b823e36ecbe325da835
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43404719"
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="3a155-103">Проверка опубликованных выходных данных с помощью dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="3a155-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="3a155-104">Чтобы проверить опубликованные выходные данные, выполните команду `dotnet vstest`.</span><span class="sxs-lookup"><span data-stu-id="3a155-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="3a155-105">Эту команду можно использовать в проверках xUnit, MSTest и NUnit.</span><span class="sxs-lookup"><span data-stu-id="3a155-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="3a155-106">Найдите DLL-файл, который является частью опубликованных выходных данных, и выполните эту команду:</span><span class="sxs-lookup"><span data-stu-id="3a155-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="3a155-107">`<MyPublishedTests>` — это имя опубликованного тестового проекта.</span><span class="sxs-lookup"><span data-stu-id="3a155-107">where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example-of-running-tests-on-a-published-dll"></a><span data-ttu-id="3a155-108">Пример тестирования опубликованного DLL-файла</span><span class="sxs-lookup"><span data-stu-id="3a155-108">Example of running tests on a published DLL</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="3a155-109">Примечание. Если приложение не предназначено для платформы `netcoreapp`, вы все равно можете выполнить команду `dotnet vstest`, передав требуемую версию .NET Framework с помощью флага платформы.</span><span class="sxs-lookup"><span data-stu-id="3a155-109">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="3a155-110">Например, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="3a155-110">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="3a155-111">В обновлении 5 для Visual Studio 2017 нужная платформа определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="3a155-111">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a155-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3a155-112">See also</span></span>
- [<span data-ttu-id="3a155-113">Модульное тестирование C# в .NET Core с использованием dotnet test и xUnit</span><span class="sxs-lookup"><span data-stu-id="3a155-113">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="3a155-114">Модульное тестирование с использованием dotnet test и xUnit</span><span class="sxs-lookup"><span data-stu-id="3a155-114">Unit Testing with dotnet test and NUnit</span></span>](unit-testing-with-nunit.md)
- [<span data-ttu-id="3a155-115">Модульное тестирование кода C# с использованием MSTest и .NET Core</span><span class="sxs-lookup"><span data-stu-id="3a155-115">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
