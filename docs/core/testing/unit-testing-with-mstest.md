---
title: Модульное тестирование кода C# с использованием MSTest и .NET Core
description: Сведения о концепциях модульного тестирования в C# и .NET Core в рамках пошаговой процедуры по созданию примера решения с помощью команды dotnet test и MSTest.
author: ncarandini
ms.author: wiwagn
ms.date: 09/08/2017
ms.openlocfilehash: bd7891243d84277a7578089f8b4629ff5bada577
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240913"
---
# <a name="unit-testing-c-with-mstest-and-net-core"></a><span data-ttu-id="051cd-103">Модульное тестирование кода C# с использованием MSTest и .NET Core</span><span class="sxs-lookup"><span data-stu-id="051cd-103">Unit testing C# with MSTest and .NET Core</span></span>

<span data-ttu-id="051cd-104">Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="051cd-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="051cd-105">Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/) перед началом работы.</span><span class="sxs-lookup"><span data-stu-id="051cd-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="051cd-106">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="051cd-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="create-the-source-project"></a><span data-ttu-id="051cd-107">Создание исходного проекта</span><span class="sxs-lookup"><span data-stu-id="051cd-107">Create the source project</span></span>

<span data-ttu-id="051cd-108">Откройте окно оболочки.</span><span class="sxs-lookup"><span data-stu-id="051cd-108">Open a shell window.</span></span> <span data-ttu-id="051cd-109">Создайте каталог с именем *unit-testing-using-mstest* для хранения решения.</span><span class="sxs-lookup"><span data-stu-id="051cd-109">Create a directory called *unit-testing-using-mstest* to hold the solution.</span></span> <span data-ttu-id="051cd-110">В этом каталоге выполните команду [`dotnet new sln`](../tools/dotnet-new.md), чтобы создать файл решения для библиотеки классов и тестового проекта.</span><span class="sxs-lookup"><span data-stu-id="051cd-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="051cd-111">Затем создайте каталог *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="051cd-111">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="051cd-112">Ниже приведена актуальная структура каталогов и файлов:</span><span class="sxs-lookup"><span data-stu-id="051cd-112">The following outline shows the directory and file structure thus far:</span></span>

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="051cd-113">Перейдите в каталог *PrimeService* и выполните команду [`dotnet new classlib`](../tools/dotnet-new.md), чтобы создать исходный проект.</span><span class="sxs-lookup"><span data-stu-id="051cd-113">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="051cd-114">Переименуйте *Class1.cs* в *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="051cd-114">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="051cd-115">Создайте сбойную реализацию класса `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="051cd-115">You create a failing implementation of the `PrimeService` class:</span></span>

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            throw new NotImplementedException("Please create a test first.");
        }
    }
}
```

<span data-ttu-id="051cd-116">Вернитесь в каталог *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="051cd-116">Change the directory back to the *unit-testing-using-mstest* directory.</span></span> <span data-ttu-id="051cd-117">Чтобы добавить проект библиотеки классов в решение, выполните команду [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md).</span><span class="sxs-lookup"><span data-stu-id="051cd-117">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="create-the-test-project"></a><span data-ttu-id="051cd-118">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="051cd-118">Create the test project</span></span>

<span data-ttu-id="051cd-119">Затем создайте каталог *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="051cd-119">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="051cd-120">Ниже представлена структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="051cd-120">The following outline shows the directory structure:</span></span>

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="051cd-121">Перейдите в каталог *PrimeService.Tests* и создайте проект с помощью [`dotnet new mstest`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="051cd-121">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="051cd-122">Команда dotnet new создает тестовый проект, который использует MSTest в качестве библиотеки тестов.</span><span class="sxs-lookup"><span data-stu-id="051cd-122">The dotnet new command creates a test project that uses MSTest as the test library.</span></span> <span data-ttu-id="051cd-123">Созданный шаблон настраивает средство запуска тестов в файле *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="051cd-123">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="051cd-124">Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда</span><span class="sxs-lookup"><span data-stu-id="051cd-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="051cd-125">Команда `dotnet new` в предыдущем шаге добавила пакет SDK MSTest, платформу тестирования MSTest и средство запуска MSTest.</span><span class="sxs-lookup"><span data-stu-id="051cd-125">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="051cd-126">Теперь добавьте в проект библиотеку классов `PrimeService` в качестве еще одной зависимости.</span><span class="sxs-lookup"><span data-stu-id="051cd-126">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="051cd-127">Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="051cd-127">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="051cd-128">Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="051cd-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="051cd-129">Ниже показан окончательный макет решения:</span><span class="sxs-lookup"><span data-stu-id="051cd-129">The following outline shows the final solution layout:</span></span>

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="051cd-130">Выполните команду [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) в каталоге *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="051cd-130">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-mstest* directory.</span></span>

## <a name="create-the-first-test"></a><span data-ttu-id="051cd-131">Создание первого теста</span><span class="sxs-lookup"><span data-stu-id="051cd-131">Create the first test</span></span>

<span data-ttu-id="051cd-132">Напишите один тест сбоя теста, запустите его, а затем повторите этот процесс.</span><span class="sxs-lookup"><span data-stu-id="051cd-132">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="051cd-133">Удалите *UnitTest1.cs* из каталога *PrimeService.Tests* и создайте файл C# *PrimeService_IsPrimeShould.cs* со следующим содержимым:</span><span class="sxs-lookup"><span data-stu-id="051cd-133">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestClass]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [TestMethod]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="051cd-134">[Атрибут TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) обозначает класс, содержащий модульные тесты.</span><span class="sxs-lookup"><span data-stu-id="051cd-134">The [TestClass attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) denotes a class that contains unit tests.</span></span> <span data-ttu-id="051cd-135">[Атрибут TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) указывает, что метод — это метода теста.</span><span class="sxs-lookup"><span data-stu-id="051cd-135">The [TestMethod attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) indicates a method is a test method.</span></span>

<span data-ttu-id="051cd-136">Сохраните этот файл и выполните [`dotnet test`](../tools/dotnet-test.md), чтобы создать тесты и библиотеку классов, а затем запустите тесты.</span><span class="sxs-lookup"><span data-stu-id="051cd-136">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="051cd-137">Средство запуска тестов MSTest содержит точку входа в программу для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="051cd-137">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="051cd-138">`dotnet test` запускает средство выполнения тестов с помощью проекта модульного теста, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="051cd-138">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="051cd-139">Тест не будет пройден.</span><span class="sxs-lookup"><span data-stu-id="051cd-139">Your test fails.</span></span> <span data-ttu-id="051cd-140">Вы еще не создали реализацию.</span><span class="sxs-lookup"><span data-stu-id="051cd-140">You haven't created the implementation yet.</span></span> <span data-ttu-id="051cd-141">Чтобы тест был пройден, напишите простейший код в классе `PrimeService`, который работает:</span><span class="sxs-lookup"><span data-stu-id="051cd-141">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first.");
}
```

<span data-ttu-id="051cd-142">Выполните команду *еще раз в каталоге*unit-testing-using-mstest`dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="051cd-142">In the *unit-testing-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="051cd-143">Команда `dotnet test` запускает сборку для проекта `PrimeService` и затем для проекта `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="051cd-143">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="051cd-144">После сборки обоих проектов она запускает этот отдельный тест.</span><span class="sxs-lookup"><span data-stu-id="051cd-144">After building both projects, it runs this single test.</span></span> <span data-ttu-id="051cd-145">Он выполняется.</span><span class="sxs-lookup"><span data-stu-id="051cd-145">It passes.</span></span>

## <a name="add-more-features"></a><span data-ttu-id="051cd-146">Добавление дополнительных возможностей</span><span class="sxs-lookup"><span data-stu-id="051cd-146">Add more features</span></span>

<span data-ttu-id="051cd-147">Теперь, когда тест проходит успешно, пора создать дополнительные тесты.</span><span class="sxs-lookup"><span data-stu-id="051cd-147">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="051cd-148">Есть еще ряд элементарных случаев с простыми числами: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="051cd-148">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="051cd-149">Можно добавлять новые тесты с помощью [атрибута TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute), но это скоро станет утомительным.</span><span class="sxs-lookup"><span data-stu-id="051cd-149">You could add new tests with the [TestMethod attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute), but that quickly becomes tedious.</span></span> <span data-ttu-id="051cd-150">Есть другие атрибуты MSTest, которые позволяют создавать наборы похожих тестов.</span><span class="sxs-lookup"><span data-stu-id="051cd-150">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="051cd-151">[Атрибут DataTestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataTestMethodAttribute) представляет набор тестов, которые выполняют один и тот же код, но имеют разные входные аргументы.</span><span class="sxs-lookup"><span data-stu-id="051cd-151">A [DataTestMethod attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataTestMethodAttribute) represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="051cd-152">С помощью [атрибута DataRow](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataRowAttribute) можно указать значения для этих входных аргументов.</span><span class="sxs-lookup"><span data-stu-id="051cd-152">You can use the [DataRow attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataRowAttribute) to specify values for those inputs.</span></span>

<span data-ttu-id="051cd-153">Вместо того чтобы создавать новые тесты, используйте эти два атрибута, чтобы создать единый управляемый данными тест,</span><span class="sxs-lookup"><span data-stu-id="051cd-153">Instead of creating new tests, apply these two attributes to create a single data driven test.</span></span> <span data-ttu-id="051cd-154">который проверяет несколько значений меньше 2, то есть наименьшего простого числа.</span><span class="sxs-lookup"><span data-stu-id="051cd-154">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/snippets/core/testing/unit-testing-using-mstest/csharp/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="051cd-155">Выполните команду `dotnet test`, и два из этих тестов завершаются ошибкой.</span><span class="sxs-lookup"><span data-stu-id="051cd-155">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="051cd-156">Для успешного выполнения всех тестов нужно изменить предложение `if` в начале метода:</span><span class="sxs-lookup"><span data-stu-id="051cd-156">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="051cd-157">Продолжайте итерации, добавляя тесты, алгоритмы и код в главной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="051cd-157">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="051cd-158">В результате вы получите [готовую версию тестов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) и [полную реализацию библиотеки](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="051cd-158">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="051cd-159">Вы создали небольшую библиотеку и набор модульных тестов для нее.</span><span class="sxs-lookup"><span data-stu-id="051cd-159">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="051cd-160">Вы структурировали решение, чтобы сделать добавление новых пакетов и тестов частью обычного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="051cd-160">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="051cd-161">и получить возможность сосредоточиться на задачах приложения.</span><span class="sxs-lookup"><span data-stu-id="051cd-161">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="051cd-162">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="051cd-162">See also</span></span>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting>
- [<span data-ttu-id="051cd-163">Использование платформы MSTest в модульных тестах</span><span class="sxs-lookup"><span data-stu-id="051cd-163">Use the MSTest framework in unit tests</span></span>](/visualstudio/test/using-microsoft-visualstudio-testtools-unittesting-members-in-unit-tests)
- [<span data-ttu-id="051cd-164">Документация по платформе тестирования MSTest V2</span><span class="sxs-lookup"><span data-stu-id="051cd-164">MSTest V2 test framework docs</span></span>](https://github.com/Microsoft/testfx-docs)
