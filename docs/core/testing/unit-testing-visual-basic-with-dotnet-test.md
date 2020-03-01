---
title: Модульное тестирование .NET Core в Visual Basic с помощью dotnet test и xUnit
description: Сведения о концепциях модульного тестирования в .NET Core в рамках пошаговой процедуры по созданию примера решения Visual Basic с использованием dotnet test и xUnit.
author: billwagner
ms.author: wiwagn
ms.date: 09/01/2017
ms.openlocfilehash: 2a2bed9628d50ea1fc635334766023dfb6de4248
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157301"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-xunit"></a><span data-ttu-id="91a85-103">Модульное тестирование библиотек .NET Core в Visual Basic с использованием dotnet test и xUnit</span><span class="sxs-lookup"><span data-stu-id="91a85-103">Unit testing Visual Basic .NET Core libraries using dotnet test and xUnit</span></span>

<span data-ttu-id="91a85-104">Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="91a85-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="91a85-105">Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-dotnet-test) перед началом работы.</span><span class="sxs-lookup"><span data-stu-id="91a85-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-dotnet-test) before you begin.</span></span> <span data-ttu-id="91a85-106">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="91a85-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="creating-the-source-project"></a><span data-ttu-id="91a85-107">Создание исходного проекта</span><span class="sxs-lookup"><span data-stu-id="91a85-107">Creating the source project</span></span>

<span data-ttu-id="91a85-108">Откройте окно оболочки.</span><span class="sxs-lookup"><span data-stu-id="91a85-108">Open a shell window.</span></span> <span data-ttu-id="91a85-109">Создайте каталог с именем *unit-testing-vb-using-dotnet-test* для хранения решения.</span><span class="sxs-lookup"><span data-stu-id="91a85-109">Create a directory called *unit-testing-vb-using-dotnet-test* to hold the solution.</span></span>
<span data-ttu-id="91a85-110">В этом каталоге выполните команду выполните команду [`dotnet new sln`](../tools/dotnet-new.md), чтобы создать решение.</span><span class="sxs-lookup"><span data-stu-id="91a85-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="91a85-111">Этот метод упрощает управление библиотекой классов и проектом модульного теста.</span><span class="sxs-lookup"><span data-stu-id="91a85-111">This practice makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="91a85-112">В каталоге решения создайте каталог *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="91a85-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="91a85-113">На данный момент структура каталогов и файлов выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="91a85-113">You have the following directory and file structure thus far:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

<span data-ttu-id="91a85-114">Перейдите в каталог *PrimeService* и выполните команду [`dotnet new classlib -lang VB`](../tools/dotnet-new.md), чтобы создать исходный проект.</span><span class="sxs-lookup"><span data-stu-id="91a85-114">Make *PrimeService* the current directory and run [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="91a85-115">Переименуйте *Class1.VB* в *PrimeService.VB*.</span><span class="sxs-lookup"><span data-stu-id="91a85-115">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="91a85-116">Создайте сбойную реализацию класса `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="91a85-116">You create a failing implementation of the `PrimeService` class:</span></span>

```vb
Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="91a85-117">Вернитесь в каталог *unit-testing-vb-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="91a85-117">Change the directory back to the *unit-testing-vb-using-dotnet-test* directory.</span></span> <span data-ttu-id="91a85-118">Чтобы добавить проект библиотеки классов в решение, выполните команду [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md).</span><span class="sxs-lookup"><span data-stu-id="91a85-118">Run [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="91a85-119">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="91a85-119">Creating the test project</span></span>

<span data-ttu-id="91a85-120">Затем создайте каталог *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="91a85-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="91a85-121">Ниже представлена структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="91a85-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-vb-using-dotnet-test
    unit-testing-vb-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="91a85-122">Перейдите в каталог *PrimeService.Tests* и создайте проект с помощью [`dotnet new xunit -lang VB`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="91a85-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit -lang VB`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="91a85-123">Эта команда создает тестовый проект, использующий xUnit в качестве библиотеки тестов.</span><span class="sxs-lookup"><span data-stu-id="91a85-123">This command creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="91a85-124">Созданный шаблон настраивает средство выполнения тестов в файле *PrimeServiceTests.vbproj*:</span><span class="sxs-lookup"><span data-stu-id="91a85-124">The generated template configures the test runner in the *PrimeServiceTests.vbproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="91a85-125">Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда</span><span class="sxs-lookup"><span data-stu-id="91a85-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="91a85-126">В предыдущем шаге `dotnet new` добавила пакет xUnit и средство запуска xUnit.</span><span class="sxs-lookup"><span data-stu-id="91a85-126">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="91a85-127">Теперь добавьте в проект библиотеку классов `PrimeService` в качестве еще одной зависимости.</span><span class="sxs-lookup"><span data-stu-id="91a85-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="91a85-128">Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="91a85-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="91a85-129">Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService.Tests.vbproj) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="91a85-129">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="91a85-130">Ниже показана окончательная структура папок:</span><span class="sxs-lookup"><span data-stu-id="91a85-130">You have the following final folder layout:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

<span data-ttu-id="91a85-131">Выполните команду [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) в каталоге *unit-testing-vb-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="91a85-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) in the *unit-testing-vb-using-dotnet-test* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="91a85-132">Создание первого теста</span><span class="sxs-lookup"><span data-stu-id="91a85-132">Creating the first test</span></span>

<span data-ttu-id="91a85-133">Напишите один тест сбоя теста, запустите его, а затем повторите этот процесс.</span><span class="sxs-lookup"><span data-stu-id="91a85-133">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="91a85-134">Удалите файл *UnitTest1.vb* из каталога *PrimeService.Tests* и создайте файл Visual Basic с именем *PrimeService_IsPrimeShould.VB*.</span><span class="sxs-lookup"><span data-stu-id="91a85-134">Remove *UnitTest1.vb* from the *PrimeService.Tests* directory and create a new Visual Basic file named *PrimeService_IsPrimeShould.VB*.</span></span> <span data-ttu-id="91a85-135">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="91a85-135">Add the following code:</span></span>

```vb
Imports Xunit

Namespace PrimeService.Tests
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Fact>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="91a85-136">Атрибут `<Fact>` обозначает метод теста, который выполняется с помощью средства выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="91a85-136">The `<Fact>` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="91a85-137">Из каталога *unit-testing-using-dotnet-test* выполните команду [`dotnet test`](../tools/dotnet-test.md) для создания тестов и библиотеки классов, а затем выполните тесты.</span><span class="sxs-lookup"><span data-stu-id="91a85-137">From the *unit-testing-using-dotnet-test*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="91a85-138">Средство запуска тестов xUnit содержит точку входа в программу для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="91a85-138">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="91a85-139">`dotnet test` запускает средство выполнения тестов с помощью проекта модульного теста, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="91a85-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="91a85-140">Тест не будет пройден.</span><span class="sxs-lookup"><span data-stu-id="91a85-140">Your test fails.</span></span> <span data-ttu-id="91a85-141">Вы еще не создали реализацию.</span><span class="sxs-lookup"><span data-stu-id="91a85-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="91a85-142">Чтобы тест был пройден, напишите простейший код в классе `PrimeService`, который работает:</span><span class="sxs-lookup"><span data-stu-id="91a85-142">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first.")
End Function
```

<span data-ttu-id="91a85-143">Выполните команду `dotnet test` еще раз в каталоге *unit-testing-vb-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="91a85-143">In the *unit-testing-vb-using-dotnet-test* directory, run `dotnet test` again.</span></span> <span data-ttu-id="91a85-144">Команда `dotnet test` запускает сборку для проекта `PrimeService` и затем для проекта `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="91a85-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="91a85-145">После сборки обоих проектов она запускает этот отдельный тест.</span><span class="sxs-lookup"><span data-stu-id="91a85-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="91a85-146">Он выполняется.</span><span class="sxs-lookup"><span data-stu-id="91a85-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="91a85-147">Добавление дополнительных возможностей</span><span class="sxs-lookup"><span data-stu-id="91a85-147">Adding more features</span></span>

<span data-ttu-id="91a85-148">Теперь, когда тест проходит успешно, пора создать дополнительные тесты.</span><span class="sxs-lookup"><span data-stu-id="91a85-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="91a85-149">Есть еще ряд элементарных случаев с простыми числами 0, -1.</span><span class="sxs-lookup"><span data-stu-id="91a85-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="91a85-150">Можно добавить их в качестве тестов с помощью атрибута `<Fact>`, но это скоро станет утомительным.</span><span class="sxs-lookup"><span data-stu-id="91a85-150">You could add those cases as new tests with the `<Fact>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="91a85-151">Есть другие атрибуты xUnit, которые позволяют создавать наборы похожих тестов.</span><span class="sxs-lookup"><span data-stu-id="91a85-151">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="91a85-152">Атрибут `<Theory>` представляет набор тестов, которые выполняют один и тот же код, но имеют разные входные аргументы.</span><span class="sxs-lookup"><span data-stu-id="91a85-152">A `<Theory>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="91a85-153">С помощью атрибута `<InlineData>` можно указать значения для этих входных аргументов.</span><span class="sxs-lookup"><span data-stu-id="91a85-153">You can use the `<InlineData>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="91a85-154">Вместо того чтобы создавать новые тесты, используйте эти два атрибута, чтобы создать единый алгоритм,</span><span class="sxs-lookup"><span data-stu-id="91a85-154">Instead of creating new tests, apply these two attributes to create a single theory.</span></span> <span data-ttu-id="91a85-155">который проверяет несколько значений меньше 2, то есть наименьшего простого числа:</span><span class="sxs-lookup"><span data-stu-id="91a85-155">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="91a85-156">Выполните команду `dotnet test`, и два из этих тестов завершаются ошибкой.</span><span class="sxs-lookup"><span data-stu-id="91a85-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="91a85-157">Для успешного выполнения всех тестов нужно изменить предложение `if` в начале метода:</span><span class="sxs-lookup"><span data-stu-id="91a85-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="91a85-158">Продолжайте итерации, добавляя тесты, алгоритмы и код в главной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="91a85-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="91a85-159">В результате вы получите [готовую версию тестов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) и [полную реализацию библиотеки](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="91a85-159">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="91a85-160">Вы создали небольшую библиотеку и набор модульных тестов для нее.</span><span class="sxs-lookup"><span data-stu-id="91a85-160">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="91a85-161">Вы структурировали решение, чтобы сделать добавление новых пакетов и тестов частью обычного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="91a85-161">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="91a85-162">и получить возможность сосредоточиться на задачах приложения.</span><span class="sxs-lookup"><span data-stu-id="91a85-162">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
