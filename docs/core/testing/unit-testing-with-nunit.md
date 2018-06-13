---
title: Модульное тестирование кода C# с использованием NUnit и .NET Core
description: Сведения о концепциях модульного тестирования в C# и .NET Core в рамках пошаговой процедуры по созданию примера решения с помощью команды dotnet test и NUnit.
author: rprouse
ms.date: 12/01/2017
ms.openlocfilehash: 8cf9e28353dd4dad6143f0dc3f8c0a8245715ea2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214410"
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a><span data-ttu-id="acd70-103">Модульное тестирование кода C# с использованием NUnit и .NET Core</span><span class="sxs-lookup"><span data-stu-id="acd70-103">Unit testing C# with NUnit and .NET Core</span></span>

<span data-ttu-id="acd70-104">Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="acd70-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="acd70-105">Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) перед началом работы.</span><span class="sxs-lookup"><span data-stu-id="acd70-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) before you begin.</span></span> <span data-ttu-id="acd70-106">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="acd70-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="acd70-107">Создание исходного проекта</span><span class="sxs-lookup"><span data-stu-id="acd70-107">Creating the source project</span></span>

<span data-ttu-id="acd70-108">Откройте окно оболочки.</span><span class="sxs-lookup"><span data-stu-id="acd70-108">Open a shell window.</span></span> <span data-ttu-id="acd70-109">Создайте каталог с именем *unit-testing-using-nunit* для хранения решения.</span><span class="sxs-lookup"><span data-stu-id="acd70-109">Create a directory called *unit-testing-using-nunit* to hold the solution.</span></span> <span data-ttu-id="acd70-110">В этом каталоге выполните команду [`dotnet new sln`](../tools/dotnet-new.md), чтобы создать файл решения для библиотеки классов и тестового проекта.</span><span class="sxs-lookup"><span data-stu-id="acd70-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="acd70-111">Затем создайте каталог *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="acd70-111">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="acd70-112">Ниже приведена актуальная структура каталогов и файлов:</span><span class="sxs-lookup"><span data-stu-id="acd70-112">The following outline shows the directory and file structure thus far:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

<span data-ttu-id="acd70-113">Перейдите в каталог *PrimeService* и выполните команду [`dotnet new classlib`](../tools/dotnet-new.md), чтобы создать исходный проект.</span><span class="sxs-lookup"><span data-stu-id="acd70-113">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="acd70-114">Переименуйте *Class1.cs* в *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="acd70-114">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="acd70-115">Чтобы использовать разработку на основе тестирования (TDD), требуется создать сбойную реализацию класса `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="acd70-115">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="acd70-116">Вернитесь в каталог *unit-testing-using-nunit*.</span><span class="sxs-lookup"><span data-stu-id="acd70-116">Change the directory back to the *unit-testing-using-nunit* directory.</span></span> <span data-ttu-id="acd70-117">Чтобы добавить проект библиотеки классов в решение, выполните команду [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md).</span><span class="sxs-lookup"><span data-stu-id="acd70-117">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="install-the-nunit-project-template"></a><span data-ttu-id="acd70-118">Установка шаблона проекта NUnit</span><span class="sxs-lookup"><span data-stu-id="acd70-118">Install the NUnit project template</span></span>

<span data-ttu-id="acd70-119">Перед созданием тестового проекта необходимо установить шаблоны тестовых проектов NUnit.</span><span class="sxs-lookup"><span data-stu-id="acd70-119">The NUnit test project templates need to be installed before creating a test project.</span></span> <span data-ttu-id="acd70-120">Это действие необходимо выполнить только один раз на каждом компьютере разработчика, где создаются новые проекты NUnit.</span><span class="sxs-lookup"><span data-stu-id="acd70-120">This only needs to be done once on each developer machine where you'll create new NUnit projects.</span></span> <span data-ttu-id="acd70-121">Для установки шаблонов NUnit выполните [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="acd70-121">Run [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) to install the NUnit templates.</span></span>

```
dotnet new -i NUnit3.DotNetNew.Template
```

### <a name="creating-the-test-project"></a><span data-ttu-id="acd70-122">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="acd70-122">Creating the test project</span></span>

<span data-ttu-id="acd70-123">Затем создайте каталог *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="acd70-123">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="acd70-124">Ниже представлена структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="acd70-124">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="acd70-125">Перейдите в каталог *PrimeService.Tests* и создайте проект с помощью [`dotnet new nunit`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="acd70-125">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new nunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="acd70-126">Команда dotnet new создает тестовый проект, который использует NUnit в качестве библиотеки тестов.</span><span class="sxs-lookup"><span data-stu-id="acd70-126">The dotnet new command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="acd70-127">Созданный шаблон настраивает средство запуска тестов в файле *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="acd70-127">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="acd70-128">Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда</span><span class="sxs-lookup"><span data-stu-id="acd70-128">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="acd70-129">`dotnet new` на предыдущем шаге добавляет пакет SDK тестирования от Майкрософт, платформу тестирования NUnit и адаптер тестирования NUnit.</span><span class="sxs-lookup"><span data-stu-id="acd70-129">`dotnet new` in the previous step added the Microsoft test SDK, the NUnit test framework, and the NUnit test adapter.</span></span> <span data-ttu-id="acd70-130">Теперь добавьте в проект библиотеку классов `PrimeService` в качестве еще одной зависимости.</span><span class="sxs-lookup"><span data-stu-id="acd70-130">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="acd70-131">Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="acd70-131">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="acd70-132">Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="acd70-132">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="acd70-133">Ниже показан окончательный макет решения:</span><span class="sxs-lookup"><span data-stu-id="acd70-133">The following outline shows the final solution layout:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="acd70-134">Выполните команду [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) в каталоге *unit-testing-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="acd70-134">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-dotnet-test* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="acd70-135">Создание первого теста</span><span class="sxs-lookup"><span data-stu-id="acd70-135">Creating the first test</span></span>

<span data-ttu-id="acd70-136">Подход TDD предполагает создание теста, который завершается ошибкой, обеспечение его успешного выполнения и повтор этого процесса.</span><span class="sxs-lookup"><span data-stu-id="acd70-136">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="acd70-137">Удалите *UnitTest1.cs* из каталога *PrimeService.Tests* и создайте файл C# *PrimeService_IsPrimeShould.cs* со следующим содержимым:</span><span class="sxs-lookup"><span data-stu-id="acd70-137">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using NUnit.Framework;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestFixture]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Test]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="acd70-138">Атрибут `[TestFixture]` обозначает класс, содержащий модульные тесты.</span><span class="sxs-lookup"><span data-stu-id="acd70-138">The `[TestFixture]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="acd70-139">Атрибут `[Test]` указывает, что метод — это метода теста.</span><span class="sxs-lookup"><span data-stu-id="acd70-139">The `[Test]` attribute indicates a method is a test method.</span></span>

<span data-ttu-id="acd70-140">Сохраните этот файл и выполните [`dotnet test`](../tools/dotnet-test.md), чтобы создать тесты и библиотеку классов, а затем запустите тесты.</span><span class="sxs-lookup"><span data-stu-id="acd70-140">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="acd70-141">Средство запуска тестов NUnit содержит точку входа в программу для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="acd70-141">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="acd70-142">`dotnet test` запускает средство выполнения тестов с помощью проекта модульного теста, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="acd70-142">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="acd70-143">Тест не будет пройден.</span><span class="sxs-lookup"><span data-stu-id="acd70-143">Your test fails.</span></span> <span data-ttu-id="acd70-144">Вы еще не создали реализацию.</span><span class="sxs-lookup"><span data-stu-id="acd70-144">You haven't created the implementation yet.</span></span> <span data-ttu-id="acd70-145">Чтобы тест был пройден, напишите простейший код в классе `PrimeService`, который работает:</span><span class="sxs-lookup"><span data-stu-id="acd70-145">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="acd70-146">Выполните команду `dotnet test` еще раз в каталоге *unit-testing-using-nunit*.</span><span class="sxs-lookup"><span data-stu-id="acd70-146">In the *unit-testing-using-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="acd70-147">Команда `dotnet test` запускает сборку для проекта `PrimeService` и затем для проекта `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="acd70-147">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="acd70-148">После сборки обоих проектов она запускает этот отдельный тест.</span><span class="sxs-lookup"><span data-stu-id="acd70-148">After building both projects, it runs this single test.</span></span> <span data-ttu-id="acd70-149">Он выполняется.</span><span class="sxs-lookup"><span data-stu-id="acd70-149">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="acd70-150">Добавление дополнительных возможностей</span><span class="sxs-lookup"><span data-stu-id="acd70-150">Adding more features</span></span>

<span data-ttu-id="acd70-151">Теперь, когда тест проходит успешно, пора создать дополнительные тесты.</span><span class="sxs-lookup"><span data-stu-id="acd70-151">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="acd70-152">Есть еще ряд элементарных случаев с простыми числами: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="acd70-152">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="acd70-153">Можно добавить новые тесты с помощью атрибута `[Test]`, но это скоро станет утомительным.</span><span class="sxs-lookup"><span data-stu-id="acd70-153">You could add new tests with the `[Test]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="acd70-154">Есть другие атрибуты NUnit, которые позволяют создавать наборы похожих тестов.</span><span class="sxs-lookup"><span data-stu-id="acd70-154">There are other NUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="acd70-155">Атрибут `[TestCase]` используется для создания набора тестов, которые выполняют один и тот же код, но имеют разные входные аргументы.</span><span class="sxs-lookup"><span data-stu-id="acd70-155">A `[TestCase]` attribute is used to create a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="acd70-156">С помощью атрибута `[TestCase]` можно указать значения для этих входных аргументов.</span><span class="sxs-lookup"><span data-stu-id="acd70-156">You can use the `[TestCase]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="acd70-157">Вместо того чтобы создавать новые тесты, используйте этот атрибут, чтобы создать единый управляемый данными тест,</span><span class="sxs-lookup"><span data-stu-id="acd70-157">Instead of creating new tests, apply this attribute to create a single data driven test.</span></span> <span data-ttu-id="acd70-158">который проверяет несколько значений меньше 2, то есть наименьшего простого числа.</span><span class="sxs-lookup"><span data-stu-id="acd70-158">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="acd70-159">Выполните команду `dotnet test`, и два из этих тестов завершаются ошибкой.</span><span class="sxs-lookup"><span data-stu-id="acd70-159">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="acd70-160">Для успешного выполнения всех тестов нужно изменить предложение `if` в начале метода:</span><span class="sxs-lookup"><span data-stu-id="acd70-160">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="acd70-161">Продолжайте итерации, добавляя тесты, алгоритмы и код в главной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="acd70-161">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="acd70-162">В результате вы получите [готовую версию тестов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) и [полную реализацию библиотеки](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="acd70-162">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="acd70-163">Вы создали небольшую библиотеку и набор модульных тестов для нее.</span><span class="sxs-lookup"><span data-stu-id="acd70-163">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="acd70-164">Вы структурировали решение, чтобы сделать добавление новых пакетов и тестов частью обычного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="acd70-164">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="acd70-165">и получить возможность сосредоточиться на задачах приложения.</span><span class="sxs-lookup"><span data-stu-id="acd70-165">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
