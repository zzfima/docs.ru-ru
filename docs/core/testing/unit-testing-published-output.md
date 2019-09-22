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
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="4613f-103">Проверка опубликованных выходных данных с помощью dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="4613f-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="4613f-104">Чтобы проверить опубликованные выходные данные, выполните команду `dotnet vstest`.</span><span class="sxs-lookup"><span data-stu-id="4613f-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="4613f-105">Эту команду можно использовать в проверках xUnit, MSTest и NUnit.</span><span class="sxs-lookup"><span data-stu-id="4613f-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="4613f-106">Найдите DLL-файл, который является частью опубликованных выходных данных, и выполните эту команду:</span><span class="sxs-lookup"><span data-stu-id="4613f-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```dotnetcli
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="4613f-107">`<MyPublishedTests>` — имя опубликованного тестового проекта.</span><span class="sxs-lookup"><span data-stu-id="4613f-107">Where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example"></a><span data-ttu-id="4613f-108">Пример</span><span class="sxs-lookup"><span data-stu-id="4613f-108">Example</span></span>

<span data-ttu-id="4613f-109">Приведенные ниже команды демонстрируют выполнение тестов с опубликованным DLL-файлом.</span><span class="sxs-lookup"><span data-stu-id="4613f-109">The commands below demonstrate running tests on a published DLL.</span></span>

```dotnetcli
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="4613f-110">Примечание. Если приложение не предназначено для платформы `netcoreapp`, вы все равно можете выполнить команду `dotnet vstest`, передав требуемую версию .NET Framework с помощью флага платформы.</span><span class="sxs-lookup"><span data-stu-id="4613f-110">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="4613f-111">Например, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="4613f-111">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="4613f-112">В обновлении 5 для Visual Studio 2017 нужная платформа определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="4613f-112">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="4613f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4613f-113">See also</span></span>

- [<span data-ttu-id="4613f-114">Модульное тестирование C# в .NET Core с использованием dotnet test и xUnit</span><span class="sxs-lookup"><span data-stu-id="4613f-114">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="4613f-115">Модульное тестирование с использованием dotnet test и xUnit</span><span class="sxs-lookup"><span data-stu-id="4613f-115">Unit Testing with dotnet test and NUnit</span></span>](unit-testing-with-nunit.md)
- [<span data-ttu-id="4613f-116">Модульное тестирование кода C# с использованием MSTest и .NET Core</span><span class="sxs-lookup"><span data-stu-id="4613f-116">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
