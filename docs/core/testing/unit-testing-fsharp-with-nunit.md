---
title: Модульное тестирование библиотек F# в .NET Core с использованием dotnet-test и NUnit
description: Сведения о концепциях модульного тестирования для F# в .NET Core в рамках пошаговой процедуры по созданию примера решения с помощью команды dotnet-test и NUnit.
author: rprouse
ms.date: 12/01/2017
ms.topic: article
dev_langs:
- fsharp
ms.prod: .net-core
ms.openlocfilehash: c38be75ff39fae3afd371a5a3a9332ee5ac96022
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-nunit"></a><span data-ttu-id="86c8a-103">Модульное тестирование библиотек F# в .NET Core с использованием dotnet-test и NUnit</span><span class="sxs-lookup"><span data-stu-id="86c8a-103">Unit testing F# libraries in .NET Core using dotnet test and NUnit</span></span>

<span data-ttu-id="86c8a-104">Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="86c8a-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="86c8a-105">Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-nunit/) перед началом работы.</span><span class="sxs-lookup"><span data-stu-id="86c8a-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-nunit/) before you begin.</span></span> <span data-ttu-id="86c8a-106">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="86c8a-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="86c8a-107">Создание исходного проекта</span><span class="sxs-lookup"><span data-stu-id="86c8a-107">Creating the source project</span></span>

<span data-ttu-id="86c8a-108">Откройте окно оболочки.</span><span class="sxs-lookup"><span data-stu-id="86c8a-108">Open a shell window.</span></span> <span data-ttu-id="86c8a-109">Создайте каталог с именем *unit-testing-with-fsharp* для хранения решения.</span><span class="sxs-lookup"><span data-stu-id="86c8a-109">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="86c8a-110">В этом каталоге выполните команду выполните команду [`dotnet new sln`](../tools/dotnet-new.md), чтобы создать решение.</span><span class="sxs-lookup"><span data-stu-id="86c8a-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="86c8a-111">Это упрощает управление библиотекой классов и проектом модульного теста.</span><span class="sxs-lookup"><span data-stu-id="86c8a-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="86c8a-112">В каталоге решения создайте каталог *MathService*.</span><span class="sxs-lookup"><span data-stu-id="86c8a-112">Inside the solution directory, create a *MathService* directory.</span></span> <span data-ttu-id="86c8a-113">Актуальная структура каталогов и файлов приведена ниже:</span><span class="sxs-lookup"><span data-stu-id="86c8a-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="86c8a-114">Чтобы создать исходный проект, перейдите в каталог *MathService* и выполните команду [`dotnet new classlib -lang F#`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="86c8a-114">Make *MathService* the current directory and run [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) to create the source project.</span></span>  <span data-ttu-id="86c8a-115">Чтобы использовать разработку на основе тестирования (TDD), требуется создать сбойную реализацию службы вычислений:</span><span class="sxs-lookup"><span data-stu-id="86c8a-115">To use test-driven development (TDD), you'll create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="86c8a-116">Вернитесь в каталог *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="86c8a-116">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="86c8a-117">Чтобы добавить проект библиотеки классов в решение, выполните команду [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md).</span><span class="sxs-lookup"><span data-stu-id="86c8a-117">Run [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="install-the-nunit-project-template"></a><span data-ttu-id="86c8a-118">Установка шаблона проекта NUnit</span><span class="sxs-lookup"><span data-stu-id="86c8a-118">Install the NUnit project template</span></span>

<span data-ttu-id="86c8a-119">Перед созданием тестового проекта необходимо установить шаблоны тестовых проектов NUnit.</span><span class="sxs-lookup"><span data-stu-id="86c8a-119">The NUnit test project templates need to be installed before creating a test project.</span></span> <span data-ttu-id="86c8a-120">Это действие необходимо выполнить только один раз на каждом компьютере разработчика, где создаются новые проекты NUnit.</span><span class="sxs-lookup"><span data-stu-id="86c8a-120">This only needs to be done once on each developer machine where you'll create new NUnit projects.</span></span> <span data-ttu-id="86c8a-121">Для установки шаблонов NUnit выполните [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="86c8a-121">Run [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) to install the NUnit templates.</span></span>

 ```
 dotnet new -i NUnit3.DotNetNew.Template
 ```

## <a name="creating-the-test-project"></a><span data-ttu-id="86c8a-122">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="86c8a-122">Creating the test project</span></span>

<span data-ttu-id="86c8a-123">Затем создайте каталог *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="86c8a-123">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="86c8a-124">Ниже представлена структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="86c8a-124">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="86c8a-125">Перейдите в каталог *MathService.Tests* и создайте проект с помощью [`dotnet new nunit -lang F#`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="86c8a-125">Make the *MathService.Tests* directory the current directory and create a new project using [`dotnet new nunit -lang F#`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="86c8a-126">При этом создается тестовый проект, который использует NUnit в качестве среды тестирования.</span><span class="sxs-lookup"><span data-stu-id="86c8a-126">This creates a test project that uses NUnit as the test framework.</span></span> <span data-ttu-id="86c8a-127">Созданный шаблон настраивает средство выполнения тестов в файле *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="86c8a-127">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="86c8a-128">Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда</span><span class="sxs-lookup"><span data-stu-id="86c8a-128">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="86c8a-129">`dotnet new` на предыдущем шаге добавляет NUnit и адаптер тестирования NUnit.</span><span class="sxs-lookup"><span data-stu-id="86c8a-129">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="86c8a-130">Теперь добавьте в проект библиотеку классов `MathService` в качестве еще одной зависимости.</span><span class="sxs-lookup"><span data-stu-id="86c8a-130">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="86c8a-131">Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="86c8a-131">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="86c8a-132">Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="86c8a-132">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="86c8a-133">Ниже показан окончательный макет решения:</span><span class="sxs-lookup"><span data-stu-id="86c8a-133">You have the following final solution layout:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathServiceTests.fsproj
```

<span data-ttu-id="86c8a-134">Выполните команду [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) в каталоге *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="86c8a-134">Execute [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) in the *unit-testing-with-fsharp* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="86c8a-135">Создание первого теста</span><span class="sxs-lookup"><span data-stu-id="86c8a-135">Creating the first test</span></span>

<span data-ttu-id="86c8a-136">Подход TDD предполагает создание теста, который завершается ошибкой, обеспечение его успешного выполнения и повтор этого процесса.</span><span class="sxs-lookup"><span data-stu-id="86c8a-136">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="86c8a-137">Откройте файл *Tests.fs* и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="86c8a-137">Open *Tests.fs* and add the following code:</span></span>

```fsharp
namespace MathService.Tests

open System
open NUnit.Framework
open MathService

[<TestFixture>]
type TestClass () =

    [<Test>]
    member this.TestMethodPassing() =
        Assert.True(true)

    [<Test>]
     member this.FailEveryTime() = Assert.True(false)
```

<span data-ttu-id="86c8a-138">Атрибут `[<TestFixture>]` обозначает класс, который содержит тесты.</span><span class="sxs-lookup"><span data-stu-id="86c8a-138">The `[<TestFixture>]` attribute denotes a class that contains tests.</span></span> <span data-ttu-id="86c8a-139">Атрибут `[<Test>]` обозначает метод теста, который выполняется с помощью средства выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="86c8a-139">The `[<Test>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="86c8a-140">Из каталога *unit-testing-with-fsharp* выполните команду [`dotnet test`](../tools/dotnet-test.md) для создания тестов и библиотеки классов, а затем выполните тесты.</span><span class="sxs-lookup"><span data-stu-id="86c8a-140">From the *unit-testing-with-fsharp* directory, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="86c8a-141">Средство запуска тестов NUnit содержит точку входа в программу для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="86c8a-141">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="86c8a-142">`dotnet test` запускает средство выполнения тестов с помощью проекта модульного теста, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="86c8a-142">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="86c8a-143">Эти два теста демонстрируют самые простые тесты, которые выполняются и завершаются сбоем.</span><span class="sxs-lookup"><span data-stu-id="86c8a-143">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="86c8a-144">`My test` выполняется успешно, а `Fail every time` завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="86c8a-144">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="86c8a-145">Сейчас создайте тест для метода `squaresOfOdds`.</span><span class="sxs-lookup"><span data-stu-id="86c8a-145">Now, create a test for the `squaresOfOdds` method.</span></span> <span data-ttu-id="86c8a-146">Метод `squaresOfOdds` возвращает последовательность квадратов всех нечетных целочисленных значений, которые являются частью входной последовательности.</span><span class="sxs-lookup"><span data-stu-id="86c8a-146">The `squaresOfOdds` method returns a sequence of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="86c8a-147">Вместо того чтобы писать все эти функции одновременно, можно постепенно создавать тесты, проверяющие функциональность.</span><span class="sxs-lookup"><span data-stu-id="86c8a-147">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="86c8a-148">Если тест выполняется успешно, создается необходимая функция метода.</span><span class="sxs-lookup"><span data-stu-id="86c8a-148">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="86c8a-149">Самый простой тест — вызов `squaresOfOdds` со всеми четными числами, где результатом должна быть пустая последовательность целых чисел.</span><span class="sxs-lookup"><span data-stu-id="86c8a-149">The simplest test we can write is to call `squaresOfOdds` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="86c8a-150">Вот этот тест:</span><span class="sxs-lookup"><span data-stu-id="86c8a-150">Here's that test:</span></span>

```fsharp
[<Test>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int>
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="86c8a-151">Обратите внимание, что последовательность `expected` преобразована в список.</span><span class="sxs-lookup"><span data-stu-id="86c8a-151">Notice that the `expected` sequence has been converted to a list.</span></span> <span data-ttu-id="86c8a-152">Платформа NUnit зависит от многих стандартных типов .NET.</span><span class="sxs-lookup"><span data-stu-id="86c8a-152">The NUnit framework relies on many standard .NET types.</span></span> <span data-ttu-id="86c8a-153">Эта зависимость означает, что ваш открытый интерфейс и ожидаемые результаты поддерживают интерфейс <xref:System.Collections.ICollection>, а не <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="86c8a-153">That dependency means that your public interface and expected results support <xref:System.Collections.ICollection> rather than <xref:System.Collections.IEnumerable>.</span></span>

<span data-ttu-id="86c8a-154">Когда вы запустите этот тест, он завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="86c8a-154">When you run the test, you see that your test fails.</span></span> <span data-ttu-id="86c8a-155">Вы еще не создали реализацию.</span><span class="sxs-lookup"><span data-stu-id="86c8a-155">You haven't created the implementation yet.</span></span> <span data-ttu-id="86c8a-156">Чтобы тест был пройден, напишите простейший код в классе `Mathservice`, который работает:</span><span class="sxs-lookup"><span data-stu-id="86c8a-156">Make this test by writing the simplest code in the `Mathservice` class that works:</span></span>

```csharp
let squaresOfOdds xs =
    Seq.empty<int>
```

<span data-ttu-id="86c8a-157">В каталоге *unit-testing-with-fsharp* снова выполните команду `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="86c8a-157">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="86c8a-158">Команда `dotnet test` запускает сборку для проекта `MathService` и затем для проекта `MathService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="86c8a-158">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="86c8a-159">После сборки обоих проектов она запускает этот отдельный тест.</span><span class="sxs-lookup"><span data-stu-id="86c8a-159">After building both projects, it runs this single test.</span></span> <span data-ttu-id="86c8a-160">Он выполняется.</span><span class="sxs-lookup"><span data-stu-id="86c8a-160">It passes.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="86c8a-161">Выполнение требований</span><span class="sxs-lookup"><span data-stu-id="86c8a-161">Completing the requirements</span></span>

<span data-ttu-id="86c8a-162">Теперь, когда тест проходит успешно, пора создать дополнительные тесты.</span><span class="sxs-lookup"><span data-stu-id="86c8a-162">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="86c8a-163">Следующий простой пример работает с последовательностью, единственным нечетным числом которой является `1`.</span><span class="sxs-lookup"><span data-stu-id="86c8a-163">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="86c8a-164">Число 1 использовать проще, потому что квадрат 1 равен 1.</span><span class="sxs-lookup"><span data-stu-id="86c8a-164">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="86c8a-165">Вот этот тест:</span><span class="sxs-lookup"><span data-stu-id="86c8a-165">Here's that next test:</span></span>

```fsharp
[<Test>]
member public this.TestOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="86c8a-166">Когда вы запустите `dotnet test`, новый тест завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="86c8a-166">Executing `dotnet test` fails the new test.</span></span> <span data-ttu-id="86c8a-167">Необходимо обновить метод `squaresOfOdds`, чтобы обработать этот новый тест.</span><span class="sxs-lookup"><span data-stu-id="86c8a-167">You must update the `squaresOfOdds` method to handle this new test.</span></span> <span data-ttu-id="86c8a-168">Чтобы тест выполнялся успешно, необходимо отфильтровать все четные числа из последовательности.</span><span class="sxs-lookup"><span data-stu-id="86c8a-168">You must filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="86c8a-169">Чтобы сделать это, напишите небольшую функцию фильтра и используйте `Seq.filter`:</span><span class="sxs-lookup"><span data-stu-id="86c8a-169">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
```

<span data-ttu-id="86c8a-170">Обратите внимание на вызов `Seq.toList`.</span><span class="sxs-lookup"><span data-stu-id="86c8a-170">Notice the call to `Seq.toList`.</span></span> <span data-ttu-id="86c8a-171">В результате создается список, который реализует интерфейс <xref:System.Collections.ICollection>.</span><span class="sxs-lookup"><span data-stu-id="86c8a-171">That creates a list, which implements the <xref:System.Collections.ICollection> interface.</span></span>

<span data-ttu-id="86c8a-172">Нужно выполнить еще один шаг: определить квадрат каждого из нечетных чисел.</span><span class="sxs-lookup"><span data-stu-id="86c8a-172">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="86c8a-173">Начнем с написания нового теста:</span><span class="sxs-lookup"><span data-stu-id="86c8a-173">Start by writing a new test:</span></span>

```fsharp
[<Test>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="86c8a-174">Чтобы вычислить квадрат каждого нечетного числа, можно исправить тест, пропустив фильтрованную последовательность через операцию сопоставления:</span><span class="sxs-lookup"><span data-stu-id="86c8a-174">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
```

<span data-ttu-id="86c8a-175">Вы создали небольшую библиотеку и набор модульных тестов для нее.</span><span class="sxs-lookup"><span data-stu-id="86c8a-175">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="86c8a-176">Вы структурировали решение, чтобы сделать добавление новых пакетов и тестов частью обычного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="86c8a-176">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="86c8a-177">и получить возможность сосредоточиться на задачах приложения.</span><span class="sxs-lookup"><span data-stu-id="86c8a-177">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
