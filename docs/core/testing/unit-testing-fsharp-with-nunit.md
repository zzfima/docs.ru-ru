---
title: Модульное тестирование F# в .NET Core с помощью dotnet test и NUnit
description: Сведения о концепциях модульного тестирования для F# в .NET Core в рамках пошаговой процедуры по созданию примера решения с помощью команды dotnet-test и NUnit.
author: rprouse
ms.date: 10/04/2018
dev_langs:
- fsharp
ms.custom: seodec18
ms.openlocfilehash: 7b559d94c03081a8ef67cf91ccfb7d08ff5b6c60
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626459"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-nunit"></a><span data-ttu-id="387cc-103">Модульное тестирование библиотек F# в .NET Core с использованием dotnet-test и NUnit</span><span class="sxs-lookup"><span data-stu-id="387cc-103">Unit testing F# libraries in .NET Core using dotnet test and NUnit</span></span>

<span data-ttu-id="387cc-104">Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="387cc-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="387cc-105">Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-nunit/) перед началом работы.</span><span class="sxs-lookup"><span data-stu-id="387cc-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-nunit/) before you begin.</span></span> <span data-ttu-id="387cc-106">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="387cc-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="387cc-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="387cc-107">Prerequisites</span></span>

- <span data-ttu-id="387cc-108">[Пакет SDK для .NET Core 2.1](https://www.microsoft.com/net/download) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="387cc-108">[.NET Core 2.1 SDK](https://www.microsoft.com/net/download) or later versions.</span></span>
- <span data-ttu-id="387cc-109">Текстовый редактор или редактор кода по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="387cc-109">A text editor or code editor of your choice.</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="387cc-110">Создание исходного проекта</span><span class="sxs-lookup"><span data-stu-id="387cc-110">Creating the source project</span></span>

<span data-ttu-id="387cc-111">Откройте окно оболочки.</span><span class="sxs-lookup"><span data-stu-id="387cc-111">Open a shell window.</span></span> <span data-ttu-id="387cc-112">Создайте каталог с именем *unit-testing-with-fsharp* для хранения решения.</span><span class="sxs-lookup"><span data-stu-id="387cc-112">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="387cc-113">В этом каталоге выполните следующую команду, чтобы создать файл решения для библиотеки классов и тестового проекта:</span><span class="sxs-lookup"><span data-stu-id="387cc-113">Inside this new directory, run the following command to create a new solution file for the class library and the test project:</span></span>

```console
dotnet new sln
```

<span data-ttu-id="387cc-114">Затем создайте каталог *MathService*.</span><span class="sxs-lookup"><span data-stu-id="387cc-114">Next, create a *MathService* directory.</span></span> <span data-ttu-id="387cc-115">Ниже приведена актуальная структура каталогов и файлов:</span><span class="sxs-lookup"><span data-stu-id="387cc-115">The following outline shows the directory and file structure so far:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="387cc-116">Перейдите к каталогу *MathService* и выполните следующую команду, чтобы создать исходный проект:</span><span class="sxs-lookup"><span data-stu-id="387cc-116">Make *MathService* the current directory and run the following command to create the source project:</span></span>

```console
dotnet new classlib -lang F#
```

<span data-ttu-id="387cc-117">Создайте реализацию службы вычислений со сбоем:</span><span class="sxs-lookup"><span data-stu-id="387cc-117">You create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="387cc-118">Вернитесь в каталог *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="387cc-118">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="387cc-119">Чтобы добавить проект библиотеки классов в решение, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="387cc-119">Run the following command to add the class library project to the solution:</span></span>

```console
dotnet sln add .\MathService\MathService.fsproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="387cc-120">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="387cc-120">Creating the test project</span></span>

<span data-ttu-id="387cc-121">Затем создайте каталог *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="387cc-121">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="387cc-122">Ниже представлена структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="387cc-122">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="387cc-123">Перейдите к каталогу *MathService.Tests* и создайте проект, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="387cc-123">Make the *MathService.Tests* directory the current directory and create a new project using the following command:</span></span>

```console
dotnet new nunit -lang F#
```

<span data-ttu-id="387cc-124">При этом создается тестовый проект, который использует NUnit в качестве среды тестирования.</span><span class="sxs-lookup"><span data-stu-id="387cc-124">This creates a test project that uses NUnit as the test framework.</span></span> <span data-ttu-id="387cc-125">Созданный шаблон настраивает средство выполнения тестов в файле *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="387cc-125">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="387cc-126">Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда</span><span class="sxs-lookup"><span data-stu-id="387cc-126">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="387cc-127">`dotnet new` на предыдущем шаге добавляет NUnit и адаптер тестирования NUnit.</span><span class="sxs-lookup"><span data-stu-id="387cc-127">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="387cc-128">Теперь добавьте в проект библиотеку классов `MathService` в качестве еще одной зависимости.</span><span class="sxs-lookup"><span data-stu-id="387cc-128">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="387cc-129">Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="387cc-129">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```console
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="387cc-130">Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="387cc-130">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="387cc-131">Ниже показан окончательный макет решения:</span><span class="sxs-lookup"><span data-stu-id="387cc-131">You have the following final solution layout:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathService.Tests.fsproj
```

<span data-ttu-id="387cc-132">Выполните следующую команду в каталоге *unit-testing-with-fsharp*:</span><span class="sxs-lookup"><span data-stu-id="387cc-132">Execute the following command in the *unit-testing-with-fsharp* directory:</span></span>

```console
dotnet sln add .\MathService.Tests\MathService.Tests.fsproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="387cc-133">Создание первого теста</span><span class="sxs-lookup"><span data-stu-id="387cc-133">Creating the first test</span></span>

<span data-ttu-id="387cc-134">Напишите один тест сбоя теста, запустите его, а затем повторите этот процесс.</span><span class="sxs-lookup"><span data-stu-id="387cc-134">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="387cc-135">Откройте файл *UnitTest1.fs* и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="387cc-135">Open *UnitTest1.fs* and add the following code:</span></span>

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

<span data-ttu-id="387cc-136">Атрибут `[<TestFixture>]` обозначает класс, который содержит тесты.</span><span class="sxs-lookup"><span data-stu-id="387cc-136">The `[<TestFixture>]` attribute denotes a class that contains tests.</span></span> <span data-ttu-id="387cc-137">Атрибут `[<Test>]` обозначает метод теста, который выполняется с помощью средства выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="387cc-137">The `[<Test>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="387cc-138">Из каталога *unit-testing-with-fsharp* выполните команду [`dotnet test`](../tools/dotnet-test.md) для создания тестов и библиотеки классов, а затем выполните тесты.</span><span class="sxs-lookup"><span data-stu-id="387cc-138">From the *unit-testing-with-fsharp* directory, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="387cc-139">Средство запуска тестов NUnit содержит точку входа в программу для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="387cc-139">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="387cc-140">`dotnet test` запускает средство выполнения тестов с помощью проекта модульного теста, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="387cc-140">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="387cc-141">Эти два теста демонстрируют самые простые тесты, которые выполняются и завершаются сбоем.</span><span class="sxs-lookup"><span data-stu-id="387cc-141">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="387cc-142">`My test` выполняется успешно, а `Fail every time` завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="387cc-142">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="387cc-143">Сейчас создайте тест для метода `squaresOfOdds`.</span><span class="sxs-lookup"><span data-stu-id="387cc-143">Now, create a test for the `squaresOfOdds` method.</span></span> <span data-ttu-id="387cc-144">Метод `squaresOfOdds` возвращает последовательность квадратов всех нечетных целочисленных значений, которые являются частью входной последовательности.</span><span class="sxs-lookup"><span data-stu-id="387cc-144">The `squaresOfOdds` method returns a sequence of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="387cc-145">Вместо того чтобы писать все эти функции одновременно, можно постепенно создавать тесты, проверяющие функциональность.</span><span class="sxs-lookup"><span data-stu-id="387cc-145">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="387cc-146">Если тест выполняется успешно, создается необходимая функция метода.</span><span class="sxs-lookup"><span data-stu-id="387cc-146">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="387cc-147">Самый простой тест — вызов `squaresOfOdds` со всеми четными числами, где результатом должна быть пустая последовательность целых чисел.</span><span class="sxs-lookup"><span data-stu-id="387cc-147">The simplest test we can write is to call `squaresOfOdds` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="387cc-148">Вот этот тест:</span><span class="sxs-lookup"><span data-stu-id="387cc-148">Here's that test:</span></span>

```fsharp
[<Test>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int>
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="387cc-149">Обратите внимание, что последовательность `expected` преобразована в список.</span><span class="sxs-lookup"><span data-stu-id="387cc-149">Notice that the `expected` sequence has been converted to a list.</span></span> <span data-ttu-id="387cc-150">Платформа NUnit зависит от многих стандартных типов .NET.</span><span class="sxs-lookup"><span data-stu-id="387cc-150">The NUnit framework relies on many standard .NET types.</span></span> <span data-ttu-id="387cc-151">Эта зависимость означает, что ваш открытый интерфейс и ожидаемые результаты поддерживают интерфейс <xref:System.Collections.ICollection>, а не <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="387cc-151">That dependency means that your public interface and expected results support <xref:System.Collections.ICollection> rather than <xref:System.Collections.IEnumerable>.</span></span>

<span data-ttu-id="387cc-152">Когда вы запустите этот тест, он завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="387cc-152">When you run the test, you see that your test fails.</span></span> <span data-ttu-id="387cc-153">Вы еще не создали реализацию.</span><span class="sxs-lookup"><span data-stu-id="387cc-153">You haven't created the implementation yet.</span></span> <span data-ttu-id="387cc-154">Чтобы этот тест прошел успешно, напишите простейший код в классе *Library.fs* в своем рабочем проекте MathService:</span><span class="sxs-lookup"><span data-stu-id="387cc-154">Make this test pass by writing the simplest code in the *Library.fs* class in your MathService project that works:</span></span>

```fsharp
let squaresOfOdds xs =
    Seq.empty<int>
```

<span data-ttu-id="387cc-155">В каталоге *unit-testing-with-fsharp* снова выполните команду `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="387cc-155">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="387cc-156">Команда `dotnet test` запускает сборку для проекта `MathService` и затем для проекта `MathService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="387cc-156">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="387cc-157">После сборки обоих проектов команда позволяет запустить ваши тесты.</span><span class="sxs-lookup"><span data-stu-id="387cc-157">After building both projects, it runs your tests.</span></span> <span data-ttu-id="387cc-158">Теперь два теста пройдены.</span><span class="sxs-lookup"><span data-stu-id="387cc-158">Two tests pass now.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="387cc-159">Выполнение требований</span><span class="sxs-lookup"><span data-stu-id="387cc-159">Completing the requirements</span></span>

<span data-ttu-id="387cc-160">Теперь, когда тест проходит успешно, пора создать дополнительные тесты.</span><span class="sxs-lookup"><span data-stu-id="387cc-160">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="387cc-161">Следующий простой пример работает с последовательностью, единственным нечетным числом которой является `1`.</span><span class="sxs-lookup"><span data-stu-id="387cc-161">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="387cc-162">Число 1 использовать проще, потому что квадрат 1 равен 1.</span><span class="sxs-lookup"><span data-stu-id="387cc-162">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="387cc-163">Вот этот тест:</span><span class="sxs-lookup"><span data-stu-id="387cc-163">Here's that next test:</span></span>

```fsharp
[<Test>]
member public this.TestOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="387cc-164">Когда вы запустите `dotnet test`, новый тест завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="387cc-164">Executing `dotnet test` fails the new test.</span></span> <span data-ttu-id="387cc-165">Необходимо обновить метод `squaresOfOdds`, чтобы обработать этот новый тест.</span><span class="sxs-lookup"><span data-stu-id="387cc-165">You must update the `squaresOfOdds` method to handle this new test.</span></span> <span data-ttu-id="387cc-166">Чтобы тест выполнялся успешно, необходимо отфильтровать все четные числа из последовательности.</span><span class="sxs-lookup"><span data-stu-id="387cc-166">You must filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="387cc-167">Чтобы сделать это, напишите небольшую функцию фильтра и используйте `Seq.filter`:</span><span class="sxs-lookup"><span data-stu-id="387cc-167">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
```

<span data-ttu-id="387cc-168">Обратите внимание на вызов `Seq.toList`.</span><span class="sxs-lookup"><span data-stu-id="387cc-168">Notice the call to `Seq.toList`.</span></span> <span data-ttu-id="387cc-169">В результате создается список, который реализует интерфейс <xref:System.Collections.ICollection>.</span><span class="sxs-lookup"><span data-stu-id="387cc-169">That creates a list, which implements the <xref:System.Collections.ICollection> interface.</span></span>

<span data-ttu-id="387cc-170">Нужно выполнить еще один шаг: определить квадрат каждого из нечетных чисел.</span><span class="sxs-lookup"><span data-stu-id="387cc-170">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="387cc-171">Начнем с написания нового теста:</span><span class="sxs-lookup"><span data-stu-id="387cc-171">Start by writing a new test:</span></span>

```fsharp
[<Test>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="387cc-172">Чтобы вычислить квадрат каждого нечетного числа, можно исправить тест, пропустив фильтрованную последовательность через операцию сопоставления:</span><span class="sxs-lookup"><span data-stu-id="387cc-172">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
```

<span data-ttu-id="387cc-173">Вы создали небольшую библиотеку и набор модульных тестов для нее.</span><span class="sxs-lookup"><span data-stu-id="387cc-173">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="387cc-174">Вы структурировали решение, чтобы сделать добавление новых пакетов и тестов частью обычного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="387cc-174">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="387cc-175">и получить возможность сосредоточиться на задачах приложения.</span><span class="sxs-lookup"><span data-stu-id="387cc-175">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
