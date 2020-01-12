---
title: Модульное тестирование кода C# с использованием NUnit и .NET Core
description: Сведения о концепциях модульного тестирования в C# и .NET Core в рамках пошаговой процедуры по созданию примера решения с помощью команды dotnet test и NUnit.
author: rprouse
ms.date: 08/31/2018
ms.openlocfilehash: 1ea17d9f830d8ac20e2bad79eebab5db767e0af8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714218"
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a><span data-ttu-id="2afc7-103">Модульное тестирование кода C# с использованием NUnit и .NET Core</span><span class="sxs-lookup"><span data-stu-id="2afc7-103">Unit testing C# with NUnit and .NET Core</span></span>

<span data-ttu-id="2afc7-104">Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="2afc7-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="2afc7-105">Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) перед началом работы.</span><span class="sxs-lookup"><span data-stu-id="2afc7-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) before you begin.</span></span> <span data-ttu-id="2afc7-106">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="2afc7-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a><span data-ttu-id="2afc7-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2afc7-107">Prerequisites</span></span>

- <span data-ttu-id="2afc7-108">[Пакет SDK для .NET Core 2.1](https://dotnet.microsoft.com/download) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="2afc7-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="2afc7-109">Текстовый редактор или редактор кода по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="2afc7-109">A text editor or code editor of your choice.</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="2afc7-110">Создание исходного проекта</span><span class="sxs-lookup"><span data-stu-id="2afc7-110">Creating the source project</span></span>

<span data-ttu-id="2afc7-111">Откройте окно оболочки.</span><span class="sxs-lookup"><span data-stu-id="2afc7-111">Open a shell window.</span></span> <span data-ttu-id="2afc7-112">Создайте каталог с именем *unit-testing-using-nunit* для хранения решения.</span><span class="sxs-lookup"><span data-stu-id="2afc7-112">Create a directory called *unit-testing-using-nunit* to hold the solution.</span></span> <span data-ttu-id="2afc7-113">В этом каталоге выполните следующую команду, чтобы создать файл решения для библиотеки классов и тестового проекта:</span><span class="sxs-lookup"><span data-stu-id="2afc7-113">Inside this new directory, run the following command to create a new solution file for the class library and the test project:</span></span>

```dotnetcli
dotnet new sln
```
 
<span data-ttu-id="2afc7-114">Затем создайте каталог *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="2afc7-114">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="2afc7-115">Ниже приведена актуальная структура каталогов и файлов:</span><span class="sxs-lookup"><span data-stu-id="2afc7-115">The following outline shows the directory and file structure so far:</span></span>

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

<span data-ttu-id="2afc7-116">Перейдите в каталог *PrimeService* и выполните следующую команду, чтобы создать исходный проект:</span><span class="sxs-lookup"><span data-stu-id="2afc7-116">Make *PrimeService* the current directory and run the following command to create the source project:</span></span>

```dotnetcli
dotnet new classlib
```

<span data-ttu-id="2afc7-117">Переименуйте *Class1.cs* в *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="2afc7-117">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="2afc7-118">Создайте сбойную реализацию класса `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="2afc7-118">You create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="2afc7-119">Вернитесь в каталог *unit-testing-using-nunit*.</span><span class="sxs-lookup"><span data-stu-id="2afc7-119">Change the directory back to the *unit-testing-using-nunit* directory.</span></span> <span data-ttu-id="2afc7-120">Чтобы добавить проект библиотеки классов в решение, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2afc7-120">Run the following command to add the class library project to the solution:</span></span>

```dotnetcli
dotnet sln add PrimeService/PrimeService.csproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="2afc7-121">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="2afc7-121">Creating the test project</span></span>

<span data-ttu-id="2afc7-122">Затем создайте каталог *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="2afc7-122">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="2afc7-123">Ниже представлена структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="2afc7-123">The following outline shows the directory structure:</span></span>

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="2afc7-124">Перейдите в каталог *PrimeService.Tests* и создайте проект, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2afc7-124">Make the *PrimeService.Tests* directory the current directory and create a new project using the following command:</span></span>

```dotnetcli
dotnet new nunit
```

<span data-ttu-id="2afc7-125">Команда [dotnet new](../tools/dotnet-new.md) создает тестовый проект, который использует NUnit в качестве библиотеки тестов.</span><span class="sxs-lookup"><span data-stu-id="2afc7-125">The [dotnet new](../tools/dotnet-new.md) command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="2afc7-126">Созданный шаблон настраивает средство запуска тестов в файле *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="2afc7-126">The generated template configures the test runner in the *PrimeService.Tests.csproj* file:</span></span>

[!code-xml[Packages](~/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj#Packages)]

<span data-ttu-id="2afc7-127">Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда</span><span class="sxs-lookup"><span data-stu-id="2afc7-127">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="2afc7-128">`dotnet new` на предыдущем шаге добавляет пакет SDK тестирования от Майкрософт, платформу тестирования NUnit и адаптер тестирования NUnit.</span><span class="sxs-lookup"><span data-stu-id="2afc7-128">`dotnet new` in the previous step added the Microsoft test SDK, the NUnit test framework, and the NUnit test adapter.</span></span> <span data-ttu-id="2afc7-129">Теперь добавьте в проект библиотеку классов `PrimeService` в качестве еще одной зависимости.</span><span class="sxs-lookup"><span data-stu-id="2afc7-129">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="2afc7-130">Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="2afc7-130">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="2afc7-131">Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="2afc7-131">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="2afc7-132">Ниже показан окончательный макет решения:</span><span class="sxs-lookup"><span data-stu-id="2afc7-132">The following outline shows the final solution layout:</span></span>

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.csproj
```

<span data-ttu-id="2afc7-133">Выполните следующую команду в каталоге *unit-testing-using-nunit*:</span><span class="sxs-lookup"><span data-stu-id="2afc7-133">Execute the following command in the *unit-testing-using-nunit* directory:</span></span>

```dotnetcli
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="2afc7-134">Создание первого теста</span><span class="sxs-lookup"><span data-stu-id="2afc7-134">Creating the first test</span></span>

<span data-ttu-id="2afc7-135">Напишите один тест сбоя теста, запустите его, а затем повторите этот процесс.</span><span class="sxs-lookup"><span data-stu-id="2afc7-135">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="2afc7-136">В каталоге *PrimeService.Tests* переименуйте файл *UnitTest1.cs* в *PrimeService_IsPrimeShould.cs* и замените его содержимое следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="2afc7-136">In the *PrimeService.Tests* directory, rename the *UnitTest1.cs* file to *PrimeService_IsPrimeShould.cs* and replace its entire contents with the following code:</span></span>

```csharp
using NUnit.Framework;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestFixture]
    public class PrimeService_IsPrimeShould
    {
        [Test]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            PrimeService primeService = CreatePrimeService();
            var result = primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
        
        /*
        More tests
        */
        
        private PrimeService CreatePrimeService()
        {
             return new PrimeService();
        }
    }
}
```

<span data-ttu-id="2afc7-137">Атрибут `[TestFixture]` обозначает класс, содержащий модульные тесты.</span><span class="sxs-lookup"><span data-stu-id="2afc7-137">The `[TestFixture]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="2afc7-138">Атрибут `[Test]` указывает, что метод — это метода теста.</span><span class="sxs-lookup"><span data-stu-id="2afc7-138">The `[Test]` attribute indicates a method is a test method.</span></span>

<span data-ttu-id="2afc7-139">Сохраните этот файл и выполните [`dotnet test`](../tools/dotnet-test.md), чтобы создать тесты и библиотеку классов, а затем запустите тесты.</span><span class="sxs-lookup"><span data-stu-id="2afc7-139">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="2afc7-140">Средство запуска тестов NUnit содержит точку входа в программу для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="2afc7-140">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="2afc7-141">`dotnet test` запускает средство выполнения тестов с помощью проекта модульного теста, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="2afc7-141">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="2afc7-142">Тест не будет пройден.</span><span class="sxs-lookup"><span data-stu-id="2afc7-142">Your test fails.</span></span> <span data-ttu-id="2afc7-143">Вы еще не создали реализацию.</span><span class="sxs-lookup"><span data-stu-id="2afc7-143">You haven't created the implementation yet.</span></span> <span data-ttu-id="2afc7-144">Чтобы тест был пройден, напишите простейший код в классе `PrimeService`, который работает:</span><span class="sxs-lookup"><span data-stu-id="2afc7-144">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="2afc7-145">Выполните команду `dotnet test` еще раз в каталоге *unit-testing-using-nunit*.</span><span class="sxs-lookup"><span data-stu-id="2afc7-145">In the *unit-testing-using-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="2afc7-146">Команда `dotnet test` запускает сборку для проекта `PrimeService` и затем для проекта `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="2afc7-146">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="2afc7-147">После сборки обоих проектов она запускает этот отдельный тест.</span><span class="sxs-lookup"><span data-stu-id="2afc7-147">After building both projects, it runs this single test.</span></span> <span data-ttu-id="2afc7-148">Он выполняется.</span><span class="sxs-lookup"><span data-stu-id="2afc7-148">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="2afc7-149">Добавление дополнительных возможностей</span><span class="sxs-lookup"><span data-stu-id="2afc7-149">Adding more features</span></span>

<span data-ttu-id="2afc7-150">Теперь, когда тест проходит успешно, пора создать дополнительные тесты.</span><span class="sxs-lookup"><span data-stu-id="2afc7-150">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="2afc7-151">Есть еще ряд элементарных случаев с простыми числами 0, -1.</span><span class="sxs-lookup"><span data-stu-id="2afc7-151">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="2afc7-152">Можно добавить новые тесты с помощью атрибута `[Test]`, но это скоро станет утомительным.</span><span class="sxs-lookup"><span data-stu-id="2afc7-152">You could add new tests with the `[Test]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="2afc7-153">Есть другие атрибуты NUnit, которые позволяют создавать наборы похожих тестов.</span><span class="sxs-lookup"><span data-stu-id="2afc7-153">There are other NUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="2afc7-154">Атрибут `[TestCase]` используется для создания набора тестов, которые выполняют один и тот же код, но имеют разные входные аргументы.</span><span class="sxs-lookup"><span data-stu-id="2afc7-154">A `[TestCase]` attribute is used to create a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="2afc7-155">С помощью атрибута `[TestCase]` можно указать значения для этих входных аргументов.</span><span class="sxs-lookup"><span data-stu-id="2afc7-155">You can use the `[TestCase]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="2afc7-156">Вместо того чтобы создавать новые тесты, используйте этот атрибут, чтобы создать единый управляемый данными тест,</span><span class="sxs-lookup"><span data-stu-id="2afc7-156">Instead of creating new tests, apply this attribute to create a single data driven test.</span></span> <span data-ttu-id="2afc7-157">который проверяет несколько значений меньше 2, то есть наименьшего простого числа.</span><span class="sxs-lookup"><span data-stu-id="2afc7-157">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="2afc7-158">Выполните команду `dotnet test`, и два из этих тестов завершаются ошибкой.</span><span class="sxs-lookup"><span data-stu-id="2afc7-158">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="2afc7-159">Для успешного выполнения всех тестов нужно изменить предложение `if` в начале метода `Main` в файле *PrimeService.cs*:</span><span class="sxs-lookup"><span data-stu-id="2afc7-159">To make all of the tests pass, change the `if` clause at the beginning of the `Main` method in the *PrimeService.cs* file:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="2afc7-160">Продолжайте итерации, добавляя тесты, алгоритмы и код в главной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="2afc7-160">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="2afc7-161">В результате вы получите [готовую версию тестов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) и [полную реализацию библиотеки](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="2afc7-161">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="2afc7-162">Вы создали небольшую библиотеку и набор модульных тестов для нее.</span><span class="sxs-lookup"><span data-stu-id="2afc7-162">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="2afc7-163">Вы структурировали решение, чтобы сделать добавление новых пакетов и тестов частью обычного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="2afc7-163">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="2afc7-164">и получить возможность сосредоточиться на задачах приложения.</span><span class="sxs-lookup"><span data-stu-id="2afc7-164">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
