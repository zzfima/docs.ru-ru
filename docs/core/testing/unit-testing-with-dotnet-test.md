---
title: Модульное тестирование кода C# в .NET Core с использованием dotnet test и xUnit
description: Сведения о концепциях модульного тестирования в C# и .NET Core в рамках пошаговой процедуры по созданию примера решения с помощью команды dotnet test и xUnit.
author: ardalis
ms.author: wiwagn
ms.date: 11/29/2017
ms.topic: article
ms.prod: .net-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 382b5b5e8bafccbcaaa5ef247d894506c1b0b172
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2018
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="ef83c-103">Модульное тестирование C# в .NET Core с использованием dotnet test и xUnit</span><span class="sxs-lookup"><span data-stu-id="ef83c-103">Unit testing C# in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="ef83c-104">Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="ef83c-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="ef83c-105">Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/) перед началом работы.</span><span class="sxs-lookup"><span data-stu-id="ef83c-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/) before you begin.</span></span> <span data-ttu-id="ef83c-106">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="ef83c-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="ef83c-107">Создание исходного проекта</span><span class="sxs-lookup"><span data-stu-id="ef83c-107">Creating the source project</span></span>

<span data-ttu-id="ef83c-108">Откройте окно оболочки.</span><span class="sxs-lookup"><span data-stu-id="ef83c-108">Open a shell window.</span></span> <span data-ttu-id="ef83c-109">Создайте каталог с именем *unit-testing-using-dotnet-test* для хранения решения.</span><span class="sxs-lookup"><span data-stu-id="ef83c-109">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span>
<span data-ttu-id="ef83c-110">В этом каталоге выполните команду выполните команду [`dotnet new sln`](../tools/dotnet-new.md), чтобы создать решение.</span><span class="sxs-lookup"><span data-stu-id="ef83c-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="ef83c-111">С помощью решения упрощается управление библиотекой классов и проектом модульного теста.</span><span class="sxs-lookup"><span data-stu-id="ef83c-111">Having a solution makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="ef83c-112">В каталоге решения создайте каталог *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="ef83c-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="ef83c-113">Актуальная структура каталогов и файлов должны иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="ef83c-113">The directory and file structure thus far should be as follows:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

<span data-ttu-id="ef83c-114">Перейдите в каталог *PrimeService* и выполните команду [`dotnet new classlib`](../tools/dotnet-new.md), чтобы создать исходный проект.</span><span class="sxs-lookup"><span data-stu-id="ef83c-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="ef83c-115">Переименуйте *Class1.cs* в *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="ef83c-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="ef83c-116">Чтобы использовать разработку на основе тестирования (TDD), сначала требуется создать сбойную реализацию класса `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="ef83c-116">To use test-driven development (TDD), you first create a failing implementation of the `PrimeService` class:</span></span>

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            throw new NotImplementedException("Please create a test first");
        }
    }
}
```

<span data-ttu-id="ef83c-117">Вернитесь в каталог *unit-testing-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="ef83c-117">Change the directory back to the *unit-testing-using-dotnet-test* directory.</span></span>

<span data-ttu-id="ef83c-118">Чтобы добавить проект библиотеки классов в решение, выполните команду [dotnet sln](../tools/dotnet-sln.md):</span><span class="sxs-lookup"><span data-stu-id="ef83c-118">Run the [dotnet sln](../tools/dotnet-sln.md) command to add the class library project to the solution:</span></span>

```
dotnet sln add .\PrimeService\PrimeService.csproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="ef83c-119">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="ef83c-119">Creating the test project</span></span>

<span data-ttu-id="ef83c-120">Затем создайте каталог *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="ef83c-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="ef83c-121">Ниже представлена структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="ef83c-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="ef83c-122">Перейдите в каталог *PrimeService.Tests* и создайте проект с помощью [`dotnet new xunit`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="ef83c-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="ef83c-123">Эта команда создает тестовый проект, использующий xUnit в качестве библиотеки тестов.</span><span class="sxs-lookup"><span data-stu-id="ef83c-123">This command creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="ef83c-124">Созданный шаблон настраивает средство запуска тестов в файле *PrimeServiceTests.csproj*, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="ef83c-124">The generated template configures the test runner in the *PrimeServiceTests.csproj* file similar to the following code:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="ef83c-125">Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда</span><span class="sxs-lookup"><span data-stu-id="ef83c-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="ef83c-126">В предыдущем шаге `dotnet new` добавила пакет xUnit и средство запуска xUnit.</span><span class="sxs-lookup"><span data-stu-id="ef83c-126">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="ef83c-127">Теперь добавьте в проект библиотеку классов `PrimeService` в качестве еще одной зависимости.</span><span class="sxs-lookup"><span data-stu-id="ef83c-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="ef83c-128">Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="ef83c-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="ef83c-129">Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="ef83c-129">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="ef83c-130">Ниже показан окончательный макет решения:</span><span class="sxs-lookup"><span data-stu-id="ef83c-130">The following shows the final solution layout:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="ef83c-131">Чтобы добавить тестовый проект в решение, выполните команду [dotnet sln](../tools/dotnet-sln.md) в каталоге *unit-testing-using-dotnet-test*:</span><span class="sxs-lookup"><span data-stu-id="ef83c-131">To add the test project to the solution, run the [dotnet sln](../tools/dotnet-sln.md) command in the *unit-testing-using-dotnet-test* directory:</span></span>

```
dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="ef83c-132">Создание первого теста</span><span class="sxs-lookup"><span data-stu-id="ef83c-132">Creating the first test</span></span>

<span data-ttu-id="ef83c-133">Подход TDD предполагает создание теста, который завершается ошибкой, обеспечение его успешного выполнения и повтор этого процесса.</span><span class="sxs-lookup"><span data-stu-id="ef83c-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="ef83c-134">Удалите файл *UnitTest1.cs* из каталога *PrimeService.Tests* и создайте новый файл C# с именем *PrimeService_IsPrimeShould.cs*.</span><span class="sxs-lookup"><span data-stu-id="ef83c-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs*.</span></span> <span data-ttu-id="ef83c-135">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="ef83c-135">Add the following code:</span></span>

```csharp
using Xunit;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Fact]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="ef83c-136">Атрибут `[Fact]` обозначает метод теста, который выполняется с помощью средства выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="ef83c-136">The `[Fact]` attribute indicates a test method that is run by the test runner.</span></span> <span data-ttu-id="ef83c-137">Из папки *PrimeService.Tests* выполните команду [`dotnet test`](../tools/dotnet-test.md) для создания тестов и библиотеки классов, а затем выполните тесты.</span><span class="sxs-lookup"><span data-stu-id="ef83c-137">From the *PrimeService.Tests* folder, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="ef83c-138">Средство запуска тестов xUnit содержит точку входа в программу для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="ef83c-138">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="ef83c-139">`dotnet test` запускает средство выполнения тестов с помощью проекта модульного теста, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="ef83c-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="ef83c-140">Тест не будет пройден.</span><span class="sxs-lookup"><span data-stu-id="ef83c-140">Your test fails.</span></span> <span data-ttu-id="ef83c-141">Вы еще не создали реализацию.</span><span class="sxs-lookup"><span data-stu-id="ef83c-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="ef83c-142">Чтобы тест был пройден, напишите простейший код в классе `PrimeService`, который работает.</span><span class="sxs-lookup"><span data-stu-id="ef83c-142">Make this test by writing the simplest code in the `PrimeService` class that works.</span></span> <span data-ttu-id="ef83c-143">Замените существующую реализацию метода `IsPrime` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="ef83c-143">Replace the existing `IsPrime` method implementation with the following code:</span></span>

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first");
}
```

<span data-ttu-id="ef83c-144">В каталоге *PrimeService.Tests* выполните `dotnet test` еще раз.</span><span class="sxs-lookup"><span data-stu-id="ef83c-144">In the *PrimeService.Tests* directory, run `dotnet test` again.</span></span> <span data-ttu-id="ef83c-145">Команда `dotnet test` запускает сборку для проекта `PrimeService` и затем для проекта `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="ef83c-145">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="ef83c-146">После сборки обоих проектов она запускает этот отдельный тест.</span><span class="sxs-lookup"><span data-stu-id="ef83c-146">After building both projects, it runs this single test.</span></span> <span data-ttu-id="ef83c-147">Он выполняется.</span><span class="sxs-lookup"><span data-stu-id="ef83c-147">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="ef83c-148">Добавление дополнительных возможностей</span><span class="sxs-lookup"><span data-stu-id="ef83c-148">Adding more features</span></span>

<span data-ttu-id="ef83c-149">Теперь, когда тест проходит успешно, пора создать дополнительные тесты.</span><span class="sxs-lookup"><span data-stu-id="ef83c-149">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="ef83c-150">Есть еще ряд элементарных случаев с простыми числами: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="ef83c-150">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="ef83c-151">Можно добавить их в качестве тестов с помощью атрибута `[Fact]`, но это скоро станет утомительным.</span><span class="sxs-lookup"><span data-stu-id="ef83c-151">You could add those cases as new tests with the `[Fact]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="ef83c-152">Есть другие атрибуты xUnit, которые позволяют создавать наборы похожих тестов.</span><span class="sxs-lookup"><span data-stu-id="ef83c-152">There are other xUnit attributes that enable you to write a suite of similar tests:</span></span>

- <span data-ttu-id="ef83c-153">`[Theory]` представляет набор тестов, которые выполняют один и тот же код, но имеют разные входные аргументы.</span><span class="sxs-lookup"><span data-stu-id="ef83c-153">`[Theory]` represents a suite of tests that execute the same code but have different input arguments.</span></span>

- <span data-ttu-id="ef83c-154">Атрибут `[InlineData]` задает значения для этих входных данных.</span><span class="sxs-lookup"><span data-stu-id="ef83c-154">`[InlineData]` attribute specifies values for those inputs.</span></span>

<span data-ttu-id="ef83c-155">Вместо того чтобы создавать новые тесты, используйте эти два атрибута, `[Theory]` и `[InlineData]`, чтобы создать в файле *PrimeService_IsPrimeShould.cs* единый алгоритм,</span><span class="sxs-lookup"><span data-stu-id="ef83c-155">Instead of creating new tests, apply these two attributes, `[Theory]` and `[InlineData]`, to create a single theory in the *PrimeService_IsPrimeShould.cs* file.</span></span> <span data-ttu-id="ef83c-156">который проверяет несколько значений меньше 2, то есть наименьшего простого числа:</span><span class="sxs-lookup"><span data-stu-id="ef83c-156">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="ef83c-157">Выполните `dotnet test` повторно. Два из этих тестов должны завершиться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ef83c-157">Run `dotnet test` again, and two of these tests should fail.</span></span> <span data-ttu-id="ef83c-158">Для успешного выполнения всех тестов нужно изменить предложение `if` в начале метода `IsPrime` в файле *PrimeService.cs*:</span><span class="sxs-lookup"><span data-stu-id="ef83c-158">To make all of the tests pass, change the `if` clause at the beginning of the `IsPrime` method in the *PrimeService.cs* file:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="ef83c-159">Продолжайте итерации, добавляя тесты, алгоритмы и код в главной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="ef83c-159">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="ef83c-160">В результате вы получите [готовую версию тестов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) и [полную реализацию библиотеки](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="ef83c-160">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ef83c-161">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ef83c-161">Additional resources</span></span>

[<span data-ttu-id="ef83c-162">Тестирование логики контроллера в ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ef83c-162">Testing controller logic in ASP.NET Core</span></span>](/aspnet/core/mvc/controllers/testing)
