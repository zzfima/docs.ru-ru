---
title: "Модульное тестирование с использованием MSTest и .NET Core"
description: "Использование MSTest с .NET Core"
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d1cb9f6667e1317e74d246988ef1257d0712c431
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="unit-testing-with-mstest-and-net-core"></a><span data-ttu-id="c037b-104">Модульное тестирование с использованием MSTest и .NET Core</span><span class="sxs-lookup"><span data-stu-id="c037b-104">Unit testing with MSTest and .NET Core</span></span>

<span data-ttu-id="c037b-105">Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="c037b-105">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="c037b-106">Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/) перед началом работы.</span><span class="sxs-lookup"><span data-stu-id="c037b-106">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="c037b-107">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="c037b-107">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="creating-the-source-project"></a><span data-ttu-id="c037b-108">Создание исходного проекта</span><span class="sxs-lookup"><span data-stu-id="c037b-108">Creating the source project</span></span>

<span data-ttu-id="c037b-109">Откройте окно оболочки.</span><span class="sxs-lookup"><span data-stu-id="c037b-109">Open a shell window.</span></span> <span data-ttu-id="c037b-110">Создайте каталог с именем *unit-testing-using-dotnet-test* для хранения решения.</span><span class="sxs-lookup"><span data-stu-id="c037b-110">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="c037b-111">Внутри него создайте каталог *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="c037b-111">Inside this new directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="c037b-112">Актуальная структура каталогов приведена ниже:</span><span class="sxs-lookup"><span data-stu-id="c037b-112">The directory structure thus far is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
```

<span data-ttu-id="c037b-113">Перейдите в каталог *PrimeService* и выполните команду [`dotnet new classlib`](../tools/dotnet-new.md), чтобы создать исходный проект.</span><span class="sxs-lookup"><span data-stu-id="c037b-113">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="c037b-114">Переименуйте *Class1.cs* в *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="c037b-114">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="c037b-115">Чтобы использовать разработку на основе тестирования (TDD), вы создадите сбойную реализацию класса `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="c037b-115">To use test-driven development (TDD), you'll create a failing implementation of the `PrimeService` class:</span></span>

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

### <a name="creating-the-test-project"></a><span data-ttu-id="c037b-116">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="c037b-116">Creating the test project</span></span>

<span data-ttu-id="c037b-117">Вернитесь в каталог *unit-testing-using-mstest* и создайте каталог *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="c037b-117">Change the directory back to the *unit-testing-using-mstest* directory and create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="c037b-118">Соответствующая структура каталогов приведена ниже:</span><span class="sxs-lookup"><span data-stu-id="c037b-118">The directory structure is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="c037b-119">Перейдите в каталог *PrimeService.Tests* и создайте проект с помощью [`dotnet new mstest`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="c037b-119">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="c037b-120">При этом создается тестовый проект, который использует MStest в качестве библиотеки тестов.</span><span class="sxs-lookup"><span data-stu-id="c037b-120">This creates a test project that uses MStest as the test library.</span></span> <span data-ttu-id="c037b-121">Созданный шаблон настраивает средство запуска тестов в файле *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="c037b-121">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.11" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.11" />
</ItemGroup>
```

<span data-ttu-id="c037b-122">Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда</span><span class="sxs-lookup"><span data-stu-id="c037b-122">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="c037b-123">Команда `dotnet new` в предыдущем шаге добавила пакет SDK MSTest, платформу тестирования MSTest и средство запуска MSTest.</span><span class="sxs-lookup"><span data-stu-id="c037b-123">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="c037b-124">Теперь добавьте в проект библиотеку классов `PrimeService` в качестве еще одной зависимости.</span><span class="sxs-lookup"><span data-stu-id="c037b-124">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="c037b-125">Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="c037b-125">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="c037b-126">Можно также вручную изменить файл *PrimeService.Tests.csproj*.</span><span class="sxs-lookup"><span data-stu-id="c037b-126">Another option is to edit the *PrimeService.Tests.csproj* file.</span></span> <span data-ttu-id="c037b-127">Сразу после первого узла `<ItemGroup>` добавьте еще один узел `<ItemGroup>` со ссылкой на проект библиотеки:</span><span class="sxs-lookup"><span data-stu-id="c037b-127">Directly under the first `<ItemGroup>` node, add another `<ItemGroup>` node with a reference to the library project:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
</ItemGroup>
```

<span data-ttu-id="c037b-128">Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="c037b-128">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="c037b-129">Ниже показан окончательный макет решения:</span><span class="sxs-lookup"><span data-stu-id="c037b-129">The final solution layout is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService
        PrimeServiceTests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="c037b-130">Создание первого теста</span><span class="sxs-lookup"><span data-stu-id="c037b-130">Creating the first test</span></span>

<span data-ttu-id="c037b-131">Перед созданием библиотеки или тестов запустите [`dotnet restore`](../tools/dotnet-restore.md) в каталоге *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="c037b-131">Before building the library or the tests, execute [`dotnet restore`](../tools/dotnet-restore.md) in the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="c037b-132">Эта команда восстанавливает все необходимые пакеты NuGet для каждого проекта.</span><span class="sxs-lookup"><span data-stu-id="c037b-132">This command restores all the necessary NuGet packages for each project.</span></span>

<span data-ttu-id="c037b-133">Подход TDD предполагает создание теста, который завершается ошибкой, обеспечение его успешного выполнения и повтор этого процесса.</span><span class="sxs-lookup"><span data-stu-id="c037b-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="c037b-134">Удалите *UnitTest1.cs* из каталога *PrimeService.Tests* и создайте файл C# *PrimeService_IsPrimeShould.cs* со следующим содержимым:</span><span class="sxs-lookup"><span data-stu-id="c037b-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

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
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, $"1 should not be prime");
        }
    }
}
```

<span data-ttu-id="c037b-135">Атрибут `[TestClass]` обозначает класс, содержащий модульные тесты.</span><span class="sxs-lookup"><span data-stu-id="c037b-135">The `[TestClass]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="c037b-136">Атрибут `[TestMethod]` означает, что метод используется как отдельный тест.</span><span class="sxs-lookup"><span data-stu-id="c037b-136">The `[TestMethod]` attribute denotes a method as a single test.</span></span> 

<span data-ttu-id="c037b-137">Сохраните этот файл и выполните [`dotnet test`](../tools/dotnet-test.md), чтобы создать тесты и библиотеку классов, а затем запустите тесты.</span><span class="sxs-lookup"><span data-stu-id="c037b-137">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="c037b-138">Средство запуска тестов MSTest содержит точку входа в программу для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="c037b-138">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="c037b-139">`dotnet test` запускает средство запуска тестов и передает ему аргумент командной строки, который указывает на сборку, содержащую тесты.</span><span class="sxs-lookup"><span data-stu-id="c037b-139">`dotnet test` starts the test runner and provides a command-line argument to the test runner indicating the assembly that contains your tests.</span></span>

<span data-ttu-id="c037b-140">Тест не будет пройден.</span><span class="sxs-lookup"><span data-stu-id="c037b-140">Your test fails.</span></span> <span data-ttu-id="c037b-141">Вы еще не создали реализацию.</span><span class="sxs-lookup"><span data-stu-id="c037b-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="c037b-142">Напишите простейший код в классе `PrimeService`, чтобы тест выполнялся успешно:</span><span class="sxs-lookup"><span data-stu-id="c037b-142">Write the simplest code in the `PrimeService` class to make this test pass:</span></span>

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

<span data-ttu-id="c037b-143">В каталоге *PrimeService.Tests* выполните `dotnet test` еще раз.</span><span class="sxs-lookup"><span data-stu-id="c037b-143">In the *PrimeService.Tests* directory, run `dotnet test` again.</span></span> <span data-ttu-id="c037b-144">Команда `dotnet test` запускает сборку для проекта `PrimeService` и затем для проекта `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="c037b-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="c037b-145">После сборки обоих проектов она запускает этот отдельный тест.</span><span class="sxs-lookup"><span data-stu-id="c037b-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="c037b-146">Он выполняется.</span><span class="sxs-lookup"><span data-stu-id="c037b-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="c037b-147">Добавление дополнительных возможностей</span><span class="sxs-lookup"><span data-stu-id="c037b-147">Adding more features</span></span>

<span data-ttu-id="c037b-148">Теперь, когда тест проходит успешно, пора создать дополнительные тесты.</span><span class="sxs-lookup"><span data-stu-id="c037b-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="c037b-149">Есть еще ряд элементарных случаев с простыми числами: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="c037b-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="c037b-150">Можно добавить их в качестве тестов с помощью атрибута `[TestMethod]`, но это скоро станет утомительным.</span><span class="sxs-lookup"><span data-stu-id="c037b-150">You could add those as new tests with the `[TestMethod]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="c037b-151">Есть другие атрибуты MSTest, которые позволяют создавать наборы похожих тестов.</span><span class="sxs-lookup"><span data-stu-id="c037b-151">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="c037b-152">Атрибут `[DataTestMethod]` представляет набор тестов, которые выполняют один и тот же код, но имеют разные входные аргументы.</span><span class="sxs-lookup"><span data-stu-id="c037b-152">A `[DataTestMethod]`attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="c037b-153">С помощью атрибута `[DataRow]` можно указать значения для этих входных аргументов.</span><span class="sxs-lookup"><span data-stu-id="c037b-153">You can use the `[DataRow]` attribute to specify values for those inputs.</span></span> 
 
<span data-ttu-id="c037b-154">Вместо создания тестов используйте эти два атрибута, чтобы создать единый метод тестирования данных, который проверяет несколько значений меньше 2, то есть наименьшего простого числа:</span><span class="sxs-lookup"><span data-stu-id="c037b-154">Instead of creating new tests, leverage these two attributes to create a single data test method that tests several values less than two, which is the lowest prime number:</span></span>

<span data-ttu-id="c037b-155">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span><span class="sxs-lookup"><span data-stu-id="c037b-155">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span></span>

<span data-ttu-id="c037b-156">Выполните команду `dotnet test`, и два из этих тестов завершаются ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c037b-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="c037b-157">Для успешного выполнения всех тестов нужно изменить предложение `if` в начале метода:</span><span class="sxs-lookup"><span data-stu-id="c037b-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="c037b-158">Продолжайте итерации, добавляя тесты, алгоритмы и код в главной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="c037b-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="c037b-159">В результате вы получите [готовую версию тестов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) и [полную реализацию библиотеки](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="c037b-159">You'll end up with the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="c037b-160">Вы создали небольшую библиотеку и набор модульных тестов для нее.</span><span class="sxs-lookup"><span data-stu-id="c037b-160">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="c037b-161">Вы структурировали решение, чтобы упростить добавление новых пакетов и тестов, и теперь можете посвятить больше времени и сил решению основных задач для приложения.</span><span class="sxs-lookup"><span data-stu-id="c037b-161">You've structured the solution so that adding new packages and tests is seamless, and you can concentrate most of your time and effort on solving the goals of the applicaiton.</span></span>

