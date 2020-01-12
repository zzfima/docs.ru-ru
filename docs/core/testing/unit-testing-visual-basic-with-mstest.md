---
title: Модульное тестирование .NET Core в Visual Basic с помощью dotnet test и MSTest
description: Сведения о концепциях модульного тестирования в .NET Core в рамках пошаговой процедуры по созданию примера Visual Basic решения с помощью MSTest.
author: billwagner
ms.author: wiwagn
ms.date: 09/01/2017
ms.openlocfilehash: 14c145ffc227078378897feeb75db0df8da4be6f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714252"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-mstest"></a><span data-ttu-id="08a2a-103">Модульное тестирование библиотек .NET Core в Visual Basic с использованием dotnet test и MSTest</span><span class="sxs-lookup"><span data-stu-id="08a2a-103">Unit testing Visual Basic .NET Core libraries using dotnet test and MSTest</span></span>

<span data-ttu-id="08a2a-104">Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="08a2a-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="08a2a-105">Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-mstest/) перед началом работы.</span><span class="sxs-lookup"><span data-stu-id="08a2a-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-mstest/) before you begin.</span></span> <span data-ttu-id="08a2a-106">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="08a2a-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="creating-the-source-project"></a><span data-ttu-id="08a2a-107">Создание исходного проекта</span><span class="sxs-lookup"><span data-stu-id="08a2a-107">Creating the source project</span></span>

<span data-ttu-id="08a2a-108">Откройте окно оболочки.</span><span class="sxs-lookup"><span data-stu-id="08a2a-108">Open a shell window.</span></span> <span data-ttu-id="08a2a-109">Создайте каталог с именем *unit-testing-vb-mstest* для хранения решения.</span><span class="sxs-lookup"><span data-stu-id="08a2a-109">Create a directory called *unit-testing-vb-mstest* to hold the solution.</span></span>
<span data-ttu-id="08a2a-110">В этом каталоге выполните команду выполните команду [`dotnet new sln`](../tools/dotnet-new.md), чтобы создать решение.</span><span class="sxs-lookup"><span data-stu-id="08a2a-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="08a2a-111">Этот метод упрощает управление библиотекой классов и проектом модульного теста.</span><span class="sxs-lookup"><span data-stu-id="08a2a-111">This practice makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="08a2a-112">В каталоге решения создайте каталог *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="08a2a-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="08a2a-113">На данный момент структура каталогов и файлов выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="08a2a-113">You have the following directory and file structure thus far:</span></span>

```console
/unit-testing-vb-mstest
    unit-testing-vb-mstest.sln
    /PrimeService
```

<span data-ttu-id="08a2a-114">Перейдите в каталог *PrimeService* и выполните команду [`dotnet new classlib -lang VB`](../tools/dotnet-new.md), чтобы создать исходный проект.</span><span class="sxs-lookup"><span data-stu-id="08a2a-114">Make *PrimeService* the current directory and run [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="08a2a-115">Переименуйте *Class1.VB* в *PrimeService.VB*.</span><span class="sxs-lookup"><span data-stu-id="08a2a-115">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="08a2a-116">Создайте сбойную реализацию класса `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="08a2a-116">You create a failing implementation of the `PrimeService` class:</span></span>

```vb
Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="08a2a-117">Вернитесь в каталог *unit-testing-vb-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="08a2a-117">Change the directory back to the *unit-testing-vb-using-mstest* directory.</span></span> <span data-ttu-id="08a2a-118">Чтобы добавить проект библиотеки классов в решение, выполните команду [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md).</span><span class="sxs-lookup"><span data-stu-id="08a2a-118">Run [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="08a2a-119">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="08a2a-119">Creating the test project</span></span>

<span data-ttu-id="08a2a-120">Затем создайте каталог *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="08a2a-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="08a2a-121">Ниже представлена структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="08a2a-121">The following outline shows the directory structure:</span></span>

```console
/unit-testing-vb-mstest
    unit-testing-vb-mstest.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="08a2a-122">Перейдите в каталог *PrimeService.Tests* и создайте проект с помощью [`dotnet new mstest -lang VB`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="08a2a-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest -lang VB`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="08a2a-123">Эта команда создает тестовый проект, использующий MSTest в качестве библиотеки тестов.</span><span class="sxs-lookup"><span data-stu-id="08a2a-123">This command creates a test project that uses MSTest as the test library.</span></span> <span data-ttu-id="08a2a-124">Созданный шаблон настраивает средство выполнения тестов в файле *PrimeServiceTests.vbproj*:</span><span class="sxs-lookup"><span data-stu-id="08a2a-124">The generated template configures the test runner in the *PrimeServiceTests.vbproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="08a2a-125">Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда</span><span class="sxs-lookup"><span data-stu-id="08a2a-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="08a2a-126">`dotnet new` на предыдущем шаге добавила MSTest и средство выполнения тестов MSTest.</span><span class="sxs-lookup"><span data-stu-id="08a2a-126">`dotnet new` in the previous step added MSTest and the MSTest runner.</span></span> <span data-ttu-id="08a2a-127">Теперь добавьте в проект библиотеку классов `PrimeService` в качестве еще одной зависимости.</span><span class="sxs-lookup"><span data-stu-id="08a2a-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="08a2a-128">Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="08a2a-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="08a2a-129">Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService.Tests.vbproj) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="08a2a-129">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="08a2a-130">Ниже показан окончательный макет решения:</span><span class="sxs-lookup"><span data-stu-id="08a2a-130">You have the following final solution layout:</span></span>

```console
/unit-testing-vb-mstest
    unit-testing-vb-mstest.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

<span data-ttu-id="08a2a-131">Выполните команду [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) в каталоге *unit-testing-vb-mstest*.</span><span class="sxs-lookup"><span data-stu-id="08a2a-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) in the *unit-testing-vb-mstest* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="08a2a-132">Создание первого теста</span><span class="sxs-lookup"><span data-stu-id="08a2a-132">Creating the first test</span></span>

<span data-ttu-id="08a2a-133">Напишите один тест сбоя теста, запустите его, а затем повторите этот процесс.</span><span class="sxs-lookup"><span data-stu-id="08a2a-133">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="08a2a-134">Удалите файл *UnitTest1.vb* из каталога *PrimeService.Tests* и создайте файл Visual Basic с именем *PrimeService_IsPrimeShould.VB*.</span><span class="sxs-lookup"><span data-stu-id="08a2a-134">Remove *UnitTest1.vb* from the *PrimeService.Tests* directory and create a new Visual Basic file named *PrimeService_IsPrimeShould.VB*.</span></span> <span data-ttu-id="08a2a-135">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="08a2a-135">Add the following code:</span></span>

```vb
Imports Microsoft.VisualStudio.TestTools.UnitTesting

Namespace PrimeService.Tests
    <TestClass>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <TestMethod>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.IsFalse(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="08a2a-136">Атрибут `<TestClass>` указывает класс, который содержит тесты.</span><span class="sxs-lookup"><span data-stu-id="08a2a-136">The `<TestClass>` attribute indicates a class that contains tests.</span></span> <span data-ttu-id="08a2a-137">Атрибут `<TestMethod>` обозначает метод, который выполняется с помощью средства выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="08a2a-137">The `<TestMethod>` attribute denotes a method that is run by the test runner.</span></span> <span data-ttu-id="08a2a-138">Из каталога *unit-testing-vb-mstest* выполните команду [`dotnet test`](../tools/dotnet-test.md) для создания тестов и библиотеки классов, а затем выполните тесты.</span><span class="sxs-lookup"><span data-stu-id="08a2a-138">From the *unit-testing-vb-mstest*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="08a2a-139">Средство запуска тестов MSTest содержит точку входа в программу для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="08a2a-139">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="08a2a-140">`dotnet test` запускает средство выполнения тестов с помощью проекта модульного теста, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="08a2a-140">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="08a2a-141">Тест не будет пройден.</span><span class="sxs-lookup"><span data-stu-id="08a2a-141">Your test fails.</span></span> <span data-ttu-id="08a2a-142">Вы еще не создали реализацию.</span><span class="sxs-lookup"><span data-stu-id="08a2a-142">You haven't created the implementation yet.</span></span> <span data-ttu-id="08a2a-143">Чтобы тест был пройден, напишите простейший код в классе `PrimeService`, который работает:</span><span class="sxs-lookup"><span data-stu-id="08a2a-143">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first.")
End Function
```

<span data-ttu-id="08a2a-144">Выполните команду `dotnet test` еще раз в каталоге *unit-testing-vb-mstest*.</span><span class="sxs-lookup"><span data-stu-id="08a2a-144">In the *unit-testing-vb-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="08a2a-145">Команда `dotnet test` запускает сборку для проекта `PrimeService` и затем для проекта `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="08a2a-145">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="08a2a-146">После сборки обоих проектов она запускает этот отдельный тест.</span><span class="sxs-lookup"><span data-stu-id="08a2a-146">After building both projects, it runs this single test.</span></span> <span data-ttu-id="08a2a-147">Он выполняется.</span><span class="sxs-lookup"><span data-stu-id="08a2a-147">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="08a2a-148">Добавление дополнительных возможностей</span><span class="sxs-lookup"><span data-stu-id="08a2a-148">Adding more features</span></span>

<span data-ttu-id="08a2a-149">Теперь, когда тест проходит успешно, пора создать дополнительные тесты.</span><span class="sxs-lookup"><span data-stu-id="08a2a-149">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="08a2a-150">Есть еще ряд элементарных случаев с простыми числами 0, -1.</span><span class="sxs-lookup"><span data-stu-id="08a2a-150">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="08a2a-151">Можно добавить их в качестве тестов с помощью атрибута `<TestMethod>`, но это скоро станет утомительным.</span><span class="sxs-lookup"><span data-stu-id="08a2a-151">You could add those cases as new tests with the `<TestMethod>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="08a2a-152">Есть другие атрибуты MSTest, которые позволяют создавать наборы похожих тестов.</span><span class="sxs-lookup"><span data-stu-id="08a2a-152">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="08a2a-153">Атрибут `<DataTestMethod>` представляет набор тестов, которые выполняют один и тот же код, но имеют разные входные аргументы.</span><span class="sxs-lookup"><span data-stu-id="08a2a-153">A `<DataTestMethod>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="08a2a-154">С помощью атрибута `<DataRow>` можно указать значения для этих входных аргументов.</span><span class="sxs-lookup"><span data-stu-id="08a2a-154">You can use the `<DataRow>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="08a2a-155">Вместо того чтобы создавать новые тесты, используйте эти два атрибута, чтобы создать единый алгоритм,</span><span class="sxs-lookup"><span data-stu-id="08a2a-155">Instead of creating new tests, apply these two attributes to create a single theory.</span></span> <span data-ttu-id="08a2a-156">который проверяет несколько значений меньше 2, то есть наименьшего простого числа:</span><span class="sxs-lookup"><span data-stu-id="08a2a-156">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="08a2a-157">Выполните команду `dotnet test`, и два из этих тестов завершаются ошибкой.</span><span class="sxs-lookup"><span data-stu-id="08a2a-157">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="08a2a-158">Для успешного выполнения всех тестов нужно изменить предложение `if` в начале метода:</span><span class="sxs-lookup"><span data-stu-id="08a2a-158">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="08a2a-159">Продолжайте итерации, добавляя тесты, алгоритмы и код в главной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="08a2a-159">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="08a2a-160">В результате вы получите [готовую версию тестов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb) и [полную реализацию библиотеки](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="08a2a-160">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="08a2a-161">Вы создали небольшую библиотеку и набор модульных тестов для нее.</span><span class="sxs-lookup"><span data-stu-id="08a2a-161">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="08a2a-162">Вы структурировали решение, чтобы сделать добавление новых пакетов и тестов частью обычного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="08a2a-162">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="08a2a-163">и получить возможность сосредоточиться на задачах приложения.</span><span class="sxs-lookup"><span data-stu-id="08a2a-163">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
