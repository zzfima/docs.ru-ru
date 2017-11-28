---
title: "Модульное тестирование .NET Core в Visual Basic с использованием dotnet test и MSTest"
description: "Сведения о концепциях модульного тестирования в .NET Core в рамках пошаговой процедуры по созданию примера Visual Basic решения с помощью MSTest."
author: billwagner
ms.author: wiwagn
ms.date: 09/01/2017
ms.topic: article
dev_langs: vb
ms.prod: .net-core
ms.openlocfilehash: b656ae4746691f2e72eaa666542e98d4abc91069
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-mstest"></a><span data-ttu-id="ccc10-103">Модульное тестирование библиотек .NET Core в Visual Basic с использованием dotnet test и MStest</span><span class="sxs-lookup"><span data-stu-id="ccc10-103">Unit testing Visual Basic .NET Core libraries using dotnet test and MStest</span></span>

<span data-ttu-id="ccc10-104">Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="ccc10-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="ccc10-105">Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-mstest/) перед началом работы.</span><span class="sxs-lookup"><span data-stu-id="ccc10-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="ccc10-106">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="ccc10-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="ccc10-107">Создание исходного проекта</span><span class="sxs-lookup"><span data-stu-id="ccc10-107">Creating the source project</span></span>

<span data-ttu-id="ccc10-108">Откройте окно оболочки.</span><span class="sxs-lookup"><span data-stu-id="ccc10-108">Open a shell window.</span></span> <span data-ttu-id="ccc10-109">Создайте каталог с именем *unit-testing-using-dotnet-test* для хранения решения.</span><span class="sxs-lookup"><span data-stu-id="ccc10-109">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span>
<span data-ttu-id="ccc10-110">В этом каталоге выполните команду выполните команду [`dotnet new sln`](../tools/dotnet-new.md), чтобы создать решение.</span><span class="sxs-lookup"><span data-stu-id="ccc10-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="ccc10-111">Этот метод упрощает управление библиотекой классов и проектом модульного теста.</span><span class="sxs-lookup"><span data-stu-id="ccc10-111">This practice makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="ccc10-112">В каталоге решения создайте каталог *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="ccc10-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="ccc10-113">На данный момент структура каталогов и файлов выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ccc10-113">You have the following directory and file structure thus far:</span></span>

```
/unit-testing-vb-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="ccc10-114">Перейдите в каталог *PrimeService* и выполните команду [`dotnet new classlib -lang VB`](../tools/dotnet-new.md), чтобы создать исходный проект.</span><span class="sxs-lookup"><span data-stu-id="ccc10-114">Make *PrimeService* the current directory and run [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="ccc10-115">Переименуйте *Class1.VB* в *PrimeService.VB*.</span><span class="sxs-lookup"><span data-stu-id="ccc10-115">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="ccc10-116">Чтобы использовать разработку на основе тестирования (TDD), требуется создать сбойную реализацию класса `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="ccc10-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

```vb
Imports System

Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="ccc10-117">Вернитесь в каталог *unit-testing-vb-using-stest*.</span><span class="sxs-lookup"><span data-stu-id="ccc10-117">Change the directory back to the *unit-testing-vb-using-stest* directory.</span></span> <span data-ttu-id="ccc10-118">Чтобы добавить проект библиотеки классов в решение, выполните команду [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md).</span><span class="sxs-lookup"><span data-stu-id="ccc10-118">Run [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="ccc10-119">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="ccc10-119">Creating the test project</span></span>

<span data-ttu-id="ccc10-120">Затем создайте каталог *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="ccc10-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="ccc10-121">Ниже представлена структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="ccc10-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-vb-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="ccc10-122">Перейдите в каталог *PrimeService.Tests* и создайте проект с помощью [`dotnet new mstest -lang VB`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="ccc10-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest -lang VB`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="ccc10-123">Эта команда создает тестовый проект, использующий xUnit в качестве библиотеки тестов.</span><span class="sxs-lookup"><span data-stu-id="ccc10-123">This command creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="ccc10-124">Созданный шаблон настраивает средство выполнения тестов в файле *PrimeServiceTests.vbproj*:</span><span class="sxs-lookup"><span data-stu-id="ccc10-124">The generated template configures the test runner in the *PrimeServiceTests.vbproj*:</span></span>

```xml
<ItemGroup>
<PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
<PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
<PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="ccc10-125">Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда</span><span class="sxs-lookup"><span data-stu-id="ccc10-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="ccc10-126">`dotnet new` на предыдущем шаге добавила MSTest и средство выполнения тестов MSTest.</span><span class="sxs-lookup"><span data-stu-id="ccc10-126">`dotnet new` in the previous step added MSTest and the MSTest runner.</span></span> <span data-ttu-id="ccc10-127">Теперь добавьте в проект библиотеку классов `PrimeService` в качестве еще одной зависимости.</span><span class="sxs-lookup"><span data-stu-id="ccc10-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="ccc10-128">Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="ccc10-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="ccc10-129">Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService.Tests/PrimeService.Tests.vbproj) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="ccc10-129">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="ccc10-130">Ниже показан окончательный макет решения:</span><span class="sxs-lookup"><span data-stu-id="ccc10-130">You have the following final solution layout:</span></span>

```
/unit-testing-vb-using-mstest
    unit-testing-vb-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

<span data-ttu-id="ccc10-131">Выполните команду [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) в каталоге *unit-testing-vb-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="ccc10-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) in the *unit-testing-vb-using-mstest* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="ccc10-132">Создание первого теста</span><span class="sxs-lookup"><span data-stu-id="ccc10-132">Creating the first test</span></span>

<span data-ttu-id="ccc10-133">Подход TDD предполагает создание теста, который завершается ошибкой, обеспечение его успешного выполнения и повтор этого процесса.</span><span class="sxs-lookup"><span data-stu-id="ccc10-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="ccc10-134">Удалите файл *UnitTest1.vb* из каталога *PrimeService.Tests* и создайте файл Visual Basic с именем *PrimeService_IsPrimeShould.VB*.</span><span class="sxs-lookup"><span data-stu-id="ccc10-134">Remove *UnitTest1.vb* from the *PrimeService.Tests* directory and create a new Visual Basic file named *PrimeService_IsPrimeShould.VB*.</span></span> <span data-ttu-id="ccc10-135">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="ccc10-135">Add the following code:</span></span>

```vb
Imports Microsoft.VisualStudio.TestTools.UnitTesting

Namespace PrimeService.Tests
    <TestClass>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <TestMethod>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="ccc10-136">Атрибут `<TestClass>` указывает класс, который содержит тесты.</span><span class="sxs-lookup"><span data-stu-id="ccc10-136">The `<TestClass>` attribute indicates a class that contains tests.</span></span> <span data-ttu-id="ccc10-137">Атрибут `<TestMethod>` обозначает метод, который выполняется с помощью средства выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="ccc10-137">The `<TestMethod>` attribute denotes a method that is run by the test runner.</span></span> <span data-ttu-id="ccc10-138">Из каталога *unit-testing-vb-using-mstest* выполните команду [`dotnet test`](../tools/dotnet-test.md) для создания тестов и библиотеки классов, а затем выполните тесты.</span><span class="sxs-lookup"><span data-stu-id="ccc10-138">From the *unit-testing-vb-using-mstest*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="ccc10-139">Средство запуска тестов xUnit содержит точку входа в программу для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="ccc10-139">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="ccc10-140">`dotnet test` запускает средство выполнения тестов с помощью проекта модульного теста, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="ccc10-140">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="ccc10-141">Тест не будет пройден.</span><span class="sxs-lookup"><span data-stu-id="ccc10-141">Your test fails.</span></span> <span data-ttu-id="ccc10-142">Вы еще не создали реализацию.</span><span class="sxs-lookup"><span data-stu-id="ccc10-142">You haven't created the implementation yet.</span></span> <span data-ttu-id="ccc10-143">Чтобы тест был пройден, напишите простейший код в классе `PrimeService`, который работает:</span><span class="sxs-lookup"><span data-stu-id="ccc10-143">Make this test by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

<span data-ttu-id="ccc10-144">Выполните команду `dotnet test` еще раз в каталоге *unit-testing-vb-using-stest*.</span><span class="sxs-lookup"><span data-stu-id="ccc10-144">In the *unit-testing-vb-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="ccc10-145">Команда `dotnet test` запускает сборку для проекта `PrimeService` и затем для проекта `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="ccc10-145">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="ccc10-146">После сборки обоих проектов она запускает этот отдельный тест.</span><span class="sxs-lookup"><span data-stu-id="ccc10-146">After building both projects, it runs this single test.</span></span> <span data-ttu-id="ccc10-147">Он выполняется.</span><span class="sxs-lookup"><span data-stu-id="ccc10-147">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="ccc10-148">Добавление дополнительных возможностей</span><span class="sxs-lookup"><span data-stu-id="ccc10-148">Adding more features</span></span>

<span data-ttu-id="ccc10-149">Теперь, когда тест проходит успешно, пора создать дополнительные тесты.</span><span class="sxs-lookup"><span data-stu-id="ccc10-149">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="ccc10-150">Есть еще ряд элементарных случаев с простыми числами: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="ccc10-150">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="ccc10-151">Можно добавить их в качестве тестов с помощью атрибута `<TestMethod>`, но это скоро станет утомительным.</span><span class="sxs-lookup"><span data-stu-id="ccc10-151">You could add those cases as new tests with the `<TestMethod>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="ccc10-152">Есть другие атрибуты xUnit, которые позволяют создавать наборы похожих тестов.</span><span class="sxs-lookup"><span data-stu-id="ccc10-152">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="ccc10-153">Атрибут `<DataTestMethod>` представляет набор тестов, которые выполняют один и тот же код, но имеют разные входные аргументы.</span><span class="sxs-lookup"><span data-stu-id="ccc10-153">A `<DataTestMethod>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="ccc10-154">С помощью атрибута `<DataRow>` можно указать значения для этих входных аргументов.</span><span class="sxs-lookup"><span data-stu-id="ccc10-154">You can use the `<DataRow>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="ccc10-155">Вместо того чтобы создавать новые тесты, используйте эти два атрибута, чтобы создать единый алгоритм,</span><span class="sxs-lookup"><span data-stu-id="ccc10-155">Instead of creating new tests, apply these two attributes to create a single theory.</span></span> <span data-ttu-id="ccc10-156">который проверяет несколько значений меньше 2, то есть наименьшего простого числа:</span><span class="sxs-lookup"><span data-stu-id="ccc10-156">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="ccc10-157">Выполните команду `dotnet test`, и два из этих тестов завершаются ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ccc10-157">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="ccc10-158">Для успешного выполнения всех тестов нужно изменить предложение `if` в начале метода:</span><span class="sxs-lookup"><span data-stu-id="ccc10-158">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="ccc10-159">Продолжайте итерации, добавляя тесты, алгоритмы и код в главной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="ccc10-159">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="ccc10-160">В результате вы получите [готовую версию тестов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb) и [полную реализацию библиотеки](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="ccc10-160">You have the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="ccc10-161">Вы создали небольшую библиотеку и набор модульных тестов для нее.</span><span class="sxs-lookup"><span data-stu-id="ccc10-161">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="ccc10-162">Вы структурировали решение, чтобы сделать добавление новых пакетов и тестов частью обычного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="ccc10-162">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="ccc10-163">и получить возможность сосредоточиться на задачах приложения.</span><span class="sxs-lookup"><span data-stu-id="ccc10-163">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
