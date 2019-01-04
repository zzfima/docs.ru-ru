---
title: Модульное тестирование F# в .NET Core с помощью dotnet test и MSTest
description: Сведения о концепциях модульного тестирования для F# в .NET Core в рамках пошаговой процедуры по созданию примера решения c помощью команды dotnet test и MSTest.
author: billwagner
ms.author: wiwagn
ms.date: 08/30/2017
dev_langs:
- fsharp
ms.custom: seodec18
ms.openlocfilehash: dacf820e8e49a337792fa927838fe4b262712e41
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240090"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-mstest"></a><span data-ttu-id="883ae-103">Модульное тестирование библиотек F# в .NET Core с использованием dotnet test и MSTest</span><span class="sxs-lookup"><span data-stu-id="883ae-103">Unit testing F# libraries in .NET Core using dotnet test and MSTest</span></span>

<span data-ttu-id="883ae-104">Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="883ae-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="883ae-105">Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-mstest/) перед началом работы.</span><span class="sxs-lookup"><span data-stu-id="883ae-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-mstest/) before you begin.</span></span> <span data-ttu-id="883ae-106">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="883ae-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="883ae-107">Создание исходного проекта</span><span class="sxs-lookup"><span data-stu-id="883ae-107">Creating the source project</span></span>

<span data-ttu-id="883ae-108">Откройте окно оболочки.</span><span class="sxs-lookup"><span data-stu-id="883ae-108">Open a shell window.</span></span> <span data-ttu-id="883ae-109">Создайте каталог с именем *unit-testing-with-fsharp* для хранения решения.</span><span class="sxs-lookup"><span data-stu-id="883ae-109">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="883ae-110">В этом каталоге выполните команду выполните команду [`dotnet new sln`](../tools/dotnet-new.md), чтобы создать решение.</span><span class="sxs-lookup"><span data-stu-id="883ae-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="883ae-111">Это упрощает управление библиотекой классов и проектом модульного теста.</span><span class="sxs-lookup"><span data-stu-id="883ae-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="883ae-112">В каталоге решения создайте каталог *MathService*.</span><span class="sxs-lookup"><span data-stu-id="883ae-112">Inside the solution directory, create a *MathService* directory.</span></span> <span data-ttu-id="883ae-113">Актуальная структура каталогов и файлов приведена ниже:</span><span class="sxs-lookup"><span data-stu-id="883ae-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="883ae-114">Чтобы создать исходный проект, перейдите в каталог *MathService* и выполните команду [`dotnet new classlib -lang F#`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="883ae-114">Make *MathService* the current directory and run [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) to create the source project.</span></span>  <span data-ttu-id="883ae-115">Чтобы использовать разработку на основе тестирования (TDD), требуется создать сбойную реализацию службы вычислений:</span><span class="sxs-lookup"><span data-stu-id="883ae-115">To use test-driven development (TDD), you'll create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="883ae-116">Вернитесь в каталог *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="883ae-116">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="883ae-117">Чтобы добавить проект библиотеки классов в решение, выполните команду [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md).</span><span class="sxs-lookup"><span data-stu-id="883ae-117">Run [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="883ae-118">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="883ae-118">Creating the test project</span></span>

<span data-ttu-id="883ae-119">Затем создайте каталог *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="883ae-119">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="883ae-120">Ниже представлена структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="883ae-120">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="883ae-121">Перейдите в каталог *MathService.Tests* и создайте проект с помощью [`dotnet new mstest -lang F#`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="883ae-121">Make the *MathService.Tests* directory the current directory and create a new project using [`dotnet new mstest -lang F#`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="883ae-122">При этом создается тестовый проект, который использует MSTest в качестве среды тестирования.</span><span class="sxs-lookup"><span data-stu-id="883ae-122">This creates a test project that uses MSTest as the test framework.</span></span> <span data-ttu-id="883ae-123">Созданный шаблон настраивает средство выполнения тестов в файле *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="883ae-123">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="883ae-124">Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда</span><span class="sxs-lookup"><span data-stu-id="883ae-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="883ae-125">`dotnet new` на предыдущем шаге добавила MSTest и средство выполнения тестов MSTest.</span><span class="sxs-lookup"><span data-stu-id="883ae-125">`dotnet new` in the previous step added MSTest and the MSTest runner.</span></span> <span data-ttu-id="883ae-126">Теперь добавьте в проект библиотеку классов `MathService` в качестве еще одной зависимости.</span><span class="sxs-lookup"><span data-stu-id="883ae-126">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="883ae-127">Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="883ae-127">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="883ae-128">Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="883ae-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="883ae-129">Ниже показан окончательный макет решения:</span><span class="sxs-lookup"><span data-stu-id="883ae-129">You have the following final solution layout:</span></span>

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

<span data-ttu-id="883ae-130">Выполните команду [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) в каталоге *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="883ae-130">Execute [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) in the *unit-testing-with-fsharp* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="883ae-131">Создание первого теста</span><span class="sxs-lookup"><span data-stu-id="883ae-131">Creating the first test</span></span>

<span data-ttu-id="883ae-132">Подход TDD предполагает создание теста, который завершается ошибкой, обеспечение его успешного выполнения и повтор этого процесса.</span><span class="sxs-lookup"><span data-stu-id="883ae-132">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="883ae-133">Откройте файл *Tests.fs* и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="883ae-133">Open *Tests.fs* and add the following code:</span></span>

```fsharp
namespace MathService.Tests

open System
open Microsoft.VisualStudio.TestTools.UnitTesting
open MathService

[<TestClass>]
type TestClass () =

    [<TestMethod>]
    member this.TestMethodPassing() =
        Assert.IsTrue(true)

    [<TestMethod>]
     member this.FailEveryTime() = Assert.IsTrue(false)
```

<span data-ttu-id="883ae-134">Атрибут `[<TestClass>]` обозначает класс, который содержит тесты.</span><span class="sxs-lookup"><span data-stu-id="883ae-134">The `[<TestClass>]` attribute denotes a class that contains tests.</span></span> <span data-ttu-id="883ae-135">Атрибут `[<TestMethod>]` обозначает метод теста, который выполняется с помощью средства выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="883ae-135">The `[<TestMethod>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="883ae-136">Из каталога *unit-testing-with-fsharp* выполните команду [`dotnet test`](../tools/dotnet-test.md) для создания тестов и библиотеки классов, а затем выполните тесты.</span><span class="sxs-lookup"><span data-stu-id="883ae-136">From the *unit-testing-with-fsharp* directory, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="883ae-137">Средство запуска тестов MSTest содержит точку входа в программу для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="883ae-137">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="883ae-138">`dotnet test` запускает средство выполнения тестов с помощью проекта модульного теста, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="883ae-138">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="883ae-139">Эти два теста демонстрируют самые простые тесты, которые выполняются и завершаются сбоем.</span><span class="sxs-lookup"><span data-stu-id="883ae-139">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="883ae-140">`My test` выполняется успешно, а `Fail every time` завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="883ae-140">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="883ae-141">Сейчас создайте тест для метода `squaresOfOdds`.</span><span class="sxs-lookup"><span data-stu-id="883ae-141">Now, create a test for the `squaresOfOdds` method.</span></span> <span data-ttu-id="883ae-142">Метод `squaresOfOdds` возвращает список квадратов всех нечетных целочисленных значений, которые являются частью входной последовательности.</span><span class="sxs-lookup"><span data-stu-id="883ae-142">The `squaresOfOdds` method returns a list of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="883ae-143">Вместо того чтобы писать все эти функции одновременно, можно постепенно создавать тесты, проверяющие функциональность.</span><span class="sxs-lookup"><span data-stu-id="883ae-143">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="883ae-144">Если тест выполняется успешно, создается необходимая функция метода.</span><span class="sxs-lookup"><span data-stu-id="883ae-144">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="883ae-145">Самый простой тест — вызов `squaresOfOdds` со всеми четными числами, где результатом должна быть пустая последовательность целых чисел.</span><span class="sxs-lookup"><span data-stu-id="883ae-145">The simplest test we can write is to call `squaresOfOdds` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="883ae-146">Вот этот тест:</span><span class="sxs-lookup"><span data-stu-id="883ae-146">Here's that test:</span></span>

```fsharp
[<TestMethod>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int> |> Seq.toList
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="883ae-147">Обратите внимание, что последовательность `expected` преобразована в список.</span><span class="sxs-lookup"><span data-stu-id="883ae-147">Notice that the `expected` sequence has been converted to a list.</span></span> <span data-ttu-id="883ae-148">Библиотека MSTest зависит от многих стандартных типов .NET.</span><span class="sxs-lookup"><span data-stu-id="883ae-148">The MSTest library relies on many standard .NET types.</span></span> <span data-ttu-id="883ae-149">Эта зависимость означает, что ваш открытый интерфейс и ожидаемые результаты поддерживают интерфейс <xref:System.Collections.ICollection>, а не <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="883ae-149">That dependency means that your public interface and expected results support <xref:System.Collections.ICollection> rather than <xref:System.Collections.IEnumerable>.</span></span>

<span data-ttu-id="883ae-150">Когда вы запустите этот тест, он завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="883ae-150">When you run the test, you see that your test fails.</span></span> <span data-ttu-id="883ae-151">Вы еще не создали реализацию.</span><span class="sxs-lookup"><span data-stu-id="883ae-151">You haven't created the implementation yet.</span></span> <span data-ttu-id="883ae-152">Чтобы тест был пройден, напишите простейший код в классе `Mathservice`, который работает:</span><span class="sxs-lookup"><span data-stu-id="883ae-152">Make this test by writing the simplest code in the `Mathservice` class that works:</span></span>

```csharp
let squaresOfOdds xs =
    Seq.empty<int> |> Seq.toList
```

<span data-ttu-id="883ae-153">В каталоге *unit-testing-with-fsharp* снова выполните команду `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="883ae-153">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="883ae-154">Команда `dotnet test` запускает сборку для проекта `MathService` и затем для проекта `MathService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="883ae-154">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="883ae-155">После сборки обоих проектов она запускает этот отдельный тест.</span><span class="sxs-lookup"><span data-stu-id="883ae-155">After building both projects, it runs this single test.</span></span> <span data-ttu-id="883ae-156">Он выполняется.</span><span class="sxs-lookup"><span data-stu-id="883ae-156">It passes.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="883ae-157">Выполнение требований</span><span class="sxs-lookup"><span data-stu-id="883ae-157">Completing the requirements</span></span>

<span data-ttu-id="883ae-158">Теперь, когда тест проходит успешно, пора создать дополнительные тесты.</span><span class="sxs-lookup"><span data-stu-id="883ae-158">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="883ae-159">Следующий простой пример работает с последовательностью, единственным нечетным числом которой является `1`.</span><span class="sxs-lookup"><span data-stu-id="883ae-159">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="883ae-160">Число 1 использовать проще, потому что квадрат 1 равен 1.</span><span class="sxs-lookup"><span data-stu-id="883ae-160">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="883ae-161">Вот этот тест:</span><span class="sxs-lookup"><span data-stu-id="883ae-161">Here's that next test:</span></span>

```fsharp
[<TestMethod>]
member public this.TestOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="883ae-162">Когда вы запустите `dotnet test`, новый тест завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="883ae-162">Executing `dotnet test` fails the new test.</span></span> <span data-ttu-id="883ae-163">Необходимо обновить метод `squaresOfOdds`, чтобы обработать этот новый тест.</span><span class="sxs-lookup"><span data-stu-id="883ae-163">You must update the `squaresOfOdds` method to handle this new test.</span></span> <span data-ttu-id="883ae-164">Чтобы тест выполнялся успешно, необходимо отфильтровать все четные числа из последовательности.</span><span class="sxs-lookup"><span data-stu-id="883ae-164">You must filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="883ae-165">Чтобы сделать это, напишите небольшую функцию фильтра и используйте `Seq.filter`:</span><span class="sxs-lookup"><span data-stu-id="883ae-165">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd |> Seq.toList
```

<span data-ttu-id="883ae-166">Обратите внимание на вызов `Seq.toList`.</span><span class="sxs-lookup"><span data-stu-id="883ae-166">Notice the call to `Seq.toList`.</span></span> <span data-ttu-id="883ae-167">В результате создается список, который реализует интерфейс <xref:System.Collections.ICollection>.</span><span class="sxs-lookup"><span data-stu-id="883ae-167">That creates a list, which implements the <xref:System.Collections.ICollection> interface.</span></span>

<span data-ttu-id="883ae-168">Нужно выполнить еще один шаг: определить квадрат каждого из нечетных чисел.</span><span class="sxs-lookup"><span data-stu-id="883ae-168">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="883ae-169">Начнем с написания нового теста:</span><span class="sxs-lookup"><span data-stu-id="883ae-169">Start by writing a new test:</span></span>

```fsharp
[<TestMethod>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="883ae-170">Чтобы вычислить квадрат каждого нечетного числа, можно исправить тест, пропустив фильтрованную последовательность через операцию сопоставления:</span><span class="sxs-lookup"><span data-stu-id="883ae-170">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
    |> Seq.toList
```

<span data-ttu-id="883ae-171">Вы создали небольшую библиотеку и набор модульных тестов для нее.</span><span class="sxs-lookup"><span data-stu-id="883ae-171">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="883ae-172">Вы структурировали решение, чтобы сделать добавление новых пакетов и тестов частью обычного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="883ae-172">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="883ae-173">и получить возможность сосредоточиться на задачах приложения.</span><span class="sxs-lookup"><span data-stu-id="883ae-173">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
