---
title: "Тестирование модулей в .NET Core с помощью команды dotnet-test и xUnit"
description: "Сведения о концепциях модульного тестирования в .NET Core в рамках пошаговой процедуры по созданию примера решения с помощью команды dotnet-test и xUnit."
author: ardalis
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net-core
ms.translationtype: HT
ms.sourcegitcommit: 867f9eb286fa7ff5ef3e9167c1ab944c81161216
ms.openlocfilehash: d989ee731d7ffd0439bac69afe1458e2aa10733a
ms.contentlocale: ru-ru
ms.lasthandoff: 08/17/2017

---
# <a name="unit-testing-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="b83ca-103">Тестирование модулей в .NET Core с помощью команды dotnet-test и xUnit</span><span class="sxs-lookup"><span data-stu-id="b83ca-103">Unit testing in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="b83ca-104">Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="b83ca-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="b83ca-105">Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/) перед началом работы.</span><span class="sxs-lookup"><span data-stu-id="b83ca-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/) before you begin.</span></span> <span data-ttu-id="b83ca-106">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="b83ca-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="b83ca-107">Создание исходного проекта</span><span class="sxs-lookup"><span data-stu-id="b83ca-107">Creating the source project</span></span>

<span data-ttu-id="b83ca-108">Откройте окно оболочки.</span><span class="sxs-lookup"><span data-stu-id="b83ca-108">Open a shell window.</span></span> <span data-ttu-id="b83ca-109">Создайте каталог с именем *unit-testing-using-dotnet-test* для хранения решения.</span><span class="sxs-lookup"><span data-stu-id="b83ca-109">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="b83ca-110">Внутри него создайте каталог *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="b83ca-110">Inside this new directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="b83ca-111">Актуальная структура каталогов приведена ниже:</span><span class="sxs-lookup"><span data-stu-id="b83ca-111">The directory structure thus far is shown below:</span></span>

```
/unit-testing-using-dotnet-test
    /PrimeService
```

<span data-ttu-id="b83ca-112">Перейдите в каталог *PrimeService* и выполните команду [`dotnet new classlib`](../tools/dotnet-new.md), чтобы создать исходный проект.</span><span class="sxs-lookup"><span data-stu-id="b83ca-112">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="b83ca-113">Переименуйте *Class1.cs* в *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="b83ca-113">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="b83ca-114">Чтобы использовать разработку на основе тестирования (TDD), вы создадите сбойную реализацию класса `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="b83ca-114">To use test-driven development (TDD), you'll create a failing implementation of the `PrimeService` class:</span></span>

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

## <a name="creating-the-test-project"></a><span data-ttu-id="b83ca-115">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="b83ca-115">Creating the test project</span></span>

<span data-ttu-id="b83ca-116">Вернитесь в каталог *unit-testing-using-dotnet-test* и создайте каталог *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="b83ca-116">Change the directory back to the *unit-testing-using-dotnet-test* directory and create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="b83ca-117">Соответствующая структура каталогов приведена ниже:</span><span class="sxs-lookup"><span data-stu-id="b83ca-117">The directory structure is shown below:</span></span>

```
/unit-testing-using-dotnet-test
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="b83ca-118">Перейдите в каталог *PrimeService.Tests* и создайте проект с помощью [`dotnet new xunit`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="b83ca-118">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="b83ca-119">Эта команда создает тестовый проект, использующий xUnit в качестве библиотеки тестов.</span><span class="sxs-lookup"><span data-stu-id="b83ca-119">This creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="b83ca-120">Созданный шаблон настраивает средство запуска тестов в файле *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="b83ca-120">The generated template configures the test runner in the *PrimeServiceTests.csproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="b83ca-121">Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда</span><span class="sxs-lookup"><span data-stu-id="b83ca-121">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="b83ca-122">В предыдущем шаге `dotnet new` добавила пакет xUnit и средство запуска xUnit.</span><span class="sxs-lookup"><span data-stu-id="b83ca-122">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="b83ca-123">Теперь добавьте в проект библиотеку классов `PrimeService` в качестве еще одной зависимости.</span><span class="sxs-lookup"><span data-stu-id="b83ca-123">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="b83ca-124">Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="b83ca-124">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="b83ca-125">Можно также вручную изменить файл *PrimeService.Tests.csproj*.</span><span class="sxs-lookup"><span data-stu-id="b83ca-125">Another option is to edit the *PrimeService.Tests.csproj* file.</span></span> <span data-ttu-id="b83ca-126">Сразу после первого узла `<ItemGroup>` добавьте еще один узел `<ItemGroup>` со ссылкой на проект библиотеки:</span><span class="sxs-lookup"><span data-stu-id="b83ca-126">Directly under the first `<ItemGroup>` node, add another `<ItemGroup>` node with a reference to the library project:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
</ItemGroup>
```

<span data-ttu-id="b83ca-127">Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="b83ca-127">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="b83ca-128">Ниже показан окончательный макет решения:</span><span class="sxs-lookup"><span data-stu-id="b83ca-128">The final solution layout is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService
        PrimeServiceTests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="b83ca-129">Создание первого теста</span><span class="sxs-lookup"><span data-stu-id="b83ca-129">Creating the first test</span></span>

<span data-ttu-id="b83ca-130">Перед созданием библиотеки или тестов запустите [`dotnet restore`](../tools/dotnet-restore.md) в каталоге *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="b83ca-130">Before building the library or the tests, execute [`dotnet restore`](../tools/dotnet-restore.md) in the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="b83ca-131">Эта команда восстанавливает все необходимые пакеты NuGet для каждого проекта.</span><span class="sxs-lookup"><span data-stu-id="b83ca-131">This command restores all the necessary NuGet packages for each project.</span></span>

<span data-ttu-id="b83ca-132">Подход TDD предполагает создание теста, который завершается ошибкой, обеспечение его успешного выполнения и повтор этого процесса.</span><span class="sxs-lookup"><span data-stu-id="b83ca-132">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="b83ca-133">Удалите *UnitTest1.cs* из каталога *PrimeService.Tests* и создайте файл C# *PrimeService_IsPrimeShould.cs* со следующим содержимым:</span><span class="sxs-lookup"><span data-stu-id="b83ca-133">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

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

            Assert.False(result, $"1 should not be prime");
        }
    }
}
```

<span data-ttu-id="b83ca-134">Атрибут `[Fact]` означает, что метод используется как отдельный тест.</span><span class="sxs-lookup"><span data-stu-id="b83ca-134">The `[Fact]` attribute denotes a method as a single test.</span></span> <span data-ttu-id="b83ca-135">Выполните [`dotnet test`](../tools/dotnet-test.md), чтобы создать тесты и библиотеку классов, а затем запустите тесты.</span><span class="sxs-lookup"><span data-stu-id="b83ca-135">Execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="b83ca-136">Средство запуска тестов xUnit содержит точку входа в программу для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="b83ca-136">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="b83ca-137">`dotnet test` запускает средство запуска тестов и передает ему аргумент командной строки, который указывает на сборку, содержащую тесты.</span><span class="sxs-lookup"><span data-stu-id="b83ca-137">`dotnet test` starts the test runner and provides a command-line argument to the test runner indicating the assembly that contains your tests.</span></span>

<span data-ttu-id="b83ca-138">Тест не будет пройден.</span><span class="sxs-lookup"><span data-stu-id="b83ca-138">Your test fails.</span></span> <span data-ttu-id="b83ca-139">Вы еще не создали реализацию.</span><span class="sxs-lookup"><span data-stu-id="b83ca-139">You haven't created the implementation yet.</span></span> <span data-ttu-id="b83ca-140">Напишите простейший код в классе `PrimeService`, чтобы тест выполнялся успешно:</span><span class="sxs-lookup"><span data-stu-id="b83ca-140">Write the simplest code in the `PrimeService` class to make this test pass:</span></span>

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

<span data-ttu-id="b83ca-141">В каталоге *PrimeService.Tests* выполните `dotnet test` еще раз.</span><span class="sxs-lookup"><span data-stu-id="b83ca-141">In the *PrimeService.Tests* directory, run `dotnet test` again.</span></span> <span data-ttu-id="b83ca-142">Команда `dotnet test` запускает сборку для проекта `PrimeService` и затем для проекта `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="b83ca-142">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="b83ca-143">После сборки обоих проектов она запускает этот отдельный тест.</span><span class="sxs-lookup"><span data-stu-id="b83ca-143">After building both projects, it runs this single test.</span></span> <span data-ttu-id="b83ca-144">Он выполняется.</span><span class="sxs-lookup"><span data-stu-id="b83ca-144">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="b83ca-145">Добавление дополнительных возможностей</span><span class="sxs-lookup"><span data-stu-id="b83ca-145">Adding more features</span></span>

<span data-ttu-id="b83ca-146">Теперь, когда тест проходит успешно, пора создать дополнительные тесты.</span><span class="sxs-lookup"><span data-stu-id="b83ca-146">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="b83ca-147">Есть еще ряд элементарных случаев с простыми числами: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="b83ca-147">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="b83ca-148">Можно добавить их в качестве тестов с помощью атрибута `[Fact]`, но это скоро станет утомительным.</span><span class="sxs-lookup"><span data-stu-id="b83ca-148">You could add those as new tests with the `[Fact]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="b83ca-149">Есть другие атрибуты xUnit, которые позволяют создавать наборы похожих тестов.</span><span class="sxs-lookup"><span data-stu-id="b83ca-149">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="b83ca-150">Атрибут `[Theory]` представляет набор тестов, которые выполняют один и тот же код, но имеют разные входные аргументы.</span><span class="sxs-lookup"><span data-stu-id="b83ca-150">A `[Theory]` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="b83ca-151">С помощью атрибута `[InlineData]` можно указать значения для этих входных аргументов.</span><span class="sxs-lookup"><span data-stu-id="b83ca-151">You can use the `[InlineData]` attribute to specify values for those inputs.</span></span> 
 
<span data-ttu-id="b83ca-152">Вместо создания тестов используйте эти два атрибута, чтобы создать единый алгоритм, который проверяет несколько значений меньше 2, то есть наименьшего простого числа:</span><span class="sxs-lookup"><span data-stu-id="b83ca-152">Instead of creating new tests, leverage these two attributes to create a single theory that tests several values less than two, which is the lowest prime number:</span></span>

<span data-ttu-id="b83ca-153">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span><span class="sxs-lookup"><span data-stu-id="b83ca-153">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span></span>

<span data-ttu-id="b83ca-154">Выполните команду `dotnet test`, и два из этих тестов завершаются ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b83ca-154">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="b83ca-155">Для успешного выполнения всех тестов нужно изменить предложение `if` в начале метода:</span><span class="sxs-lookup"><span data-stu-id="b83ca-155">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="b83ca-156">Продолжайте итерации, добавляя тесты, алгоритмы и код в главной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="b83ca-156">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="b83ca-157">В результате вы получите [готовую версию тестов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) и [полную реализацию библиотеки](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="b83ca-157">You'll end up with the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="b83ca-158">Вы создали небольшую библиотеку и набор модульных тестов для нее.</span><span class="sxs-lookup"><span data-stu-id="b83ca-158">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="b83ca-159">Вы структурировали решение, чтобы упростить добавление новых пакетов и тестов, и теперь можете посвятить больше времени и сил решению основных задач для приложения.</span><span class="sxs-lookup"><span data-stu-id="b83ca-159">You've structured the solution so that adding new packages and tests is seamless, and you can concentrate most of your time and effort on solving the goals of the applicaiton.</span></span>

