---
title: Проверка опубликованных выходных данных с помощью dotnet vstest
description: Узнайте, как протестировать опубликованные библиотеки (вместо исходного кода) с помощью команды dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.openlocfilehash: 7618d37782de3a16f1963380bbb56945fb73e8eb
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714258"
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="c97ae-103">Проверка опубликованных выходных данных с помощью dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="c97ae-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="c97ae-104">Чтобы проверить опубликованные выходные данные, выполните команду `dotnet vstest`.</span><span class="sxs-lookup"><span data-stu-id="c97ae-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="c97ae-105">Эту команду можно использовать в проверках xUnit, MSTest и NUnit.</span><span class="sxs-lookup"><span data-stu-id="c97ae-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="c97ae-106">Найдите DLL-файл, который является частью опубликованных выходных данных, и выполните эту команду:</span><span class="sxs-lookup"><span data-stu-id="c97ae-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```dotnetcli
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="c97ae-107">`<MyPublishedTests>` — имя опубликованного тестового проекта.</span><span class="sxs-lookup"><span data-stu-id="c97ae-107">Where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example"></a><span data-ttu-id="c97ae-108">Пример</span><span class="sxs-lookup"><span data-stu-id="c97ae-108">Example</span></span>

<span data-ttu-id="c97ae-109">Приведенные ниже команды демонстрируют выполнение тестов с опубликованным DLL-файлом.</span><span class="sxs-lookup"><span data-stu-id="c97ae-109">The commands below demonstrate running tests on a published DLL.</span></span>

```dotnetcli
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="c97ae-110">Примечание. Если приложение не предназначено для платформы `netcoreapp`, вы все равно можете выполнить команду `dotnet vstest`, передав требуемую версию .NET Framework с помощью флага платформы.</span><span class="sxs-lookup"><span data-stu-id="c97ae-110">Note: If your app targets a framework other than `netcoreapp`, you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="c97ae-111">Например, `dotnet vstest <MyPublishedTests>.dll --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="c97ae-111">For example, `dotnet vstest <MyPublishedTests>.dll --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="c97ae-112">В обновлении 5 для Visual Studio 2017 и более поздних версий нужная платформа определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="c97ae-112">In Visual Studio 2017 Update 5 and later, the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="c97ae-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c97ae-113">See also</span></span>

- [<span data-ttu-id="c97ae-114">Модульное тестирование C# в .NET Core с использованием dotnet test и xUnit</span><span class="sxs-lookup"><span data-stu-id="c97ae-114">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="c97ae-115">Модульное тестирование с использованием dotnet test и xUnit</span><span class="sxs-lookup"><span data-stu-id="c97ae-115">Unit Testing with dotnet test and NUnit</span></span>](unit-testing-with-nunit.md)
- [<span data-ttu-id="c97ae-116">Модульное тестирование кода C# с использованием MSTest и .NET Core</span><span class="sxs-lookup"><span data-stu-id="c97ae-116">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
