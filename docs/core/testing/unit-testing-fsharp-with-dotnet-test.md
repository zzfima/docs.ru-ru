---
title: Модульное тестирование F# в .NET Core с помощью dotnet test и xUnit
description: Сведения о концепциях модульного тестирования для F# в .NET Core в рамках пошаговой процедуры по созданию примера решения с помощью команды dotnet-test и xUnit.
author: billwagner
ms.author: wiwagn
ms.date: 08/30/2017
ms.openlocfilehash: 5fe4a8faddd87334439513368f24d808abc58e65
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157314"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="1f026-103">Модульное тестирование библиотек F# в .NET Core с использованием dotnet-test и xUnit</span><span class="sxs-lookup"><span data-stu-id="1f026-103">Unit testing F# libraries in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="1f026-104">Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="1f026-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="1f026-105">Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp/) перед началом работы.</span><span class="sxs-lookup"><span data-stu-id="1f026-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp/) before you begin.</span></span> <span data-ttu-id="1f026-106">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="1f026-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="creating-the-source-project"></a><span data-ttu-id="1f026-107">Создание исходного проекта</span><span class="sxs-lookup"><span data-stu-id="1f026-107">Creating the source project</span></span>

<span data-ttu-id="1f026-108">Откройте окно оболочки.</span><span class="sxs-lookup"><span data-stu-id="1f026-108">Open a shell window.</span></span> <span data-ttu-id="1f026-109">Создайте каталог с именем *unit-testing-with-fsharp* для хранения решения.</span><span class="sxs-lookup"><span data-stu-id="1f026-109">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="1f026-110">В этом каталоге выполните команду `dotnet new sln`, чтобы создать решение.</span><span class="sxs-lookup"><span data-stu-id="1f026-110">Inside this new directory, run `dotnet new sln` to create a new solution.</span></span> <span data-ttu-id="1f026-111">Это упрощает управление библиотекой классов и проектом модульного теста.</span><span class="sxs-lookup"><span data-stu-id="1f026-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="1f026-112">В каталоге решения создайте каталог *MathService*.</span><span class="sxs-lookup"><span data-stu-id="1f026-112">Inside the solution directory, create a *MathService* directory.</span></span> <span data-ttu-id="1f026-113">Актуальная структура каталогов и файлов приведена ниже:</span><span class="sxs-lookup"><span data-stu-id="1f026-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="1f026-114">Чтобы создать исходный проект, перейдите в каталог *MathService* и выполните команду `dotnet new classlib -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="1f026-114">Make *MathService* the current directory, and run `dotnet new classlib -lang "F#"` to create the source project.</span></span> <span data-ttu-id="1f026-115">Создайте реализацию службы вычислений со сбоем:</span><span class="sxs-lookup"><span data-stu-id="1f026-115">You'll create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="1f026-116">Вернитесь в каталог *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="1f026-116">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="1f026-117">Чтобы добавить проект библиотеки классов в решение, выполните команду `dotnet sln add .\MathService\MathService.fsproj`.</span><span class="sxs-lookup"><span data-stu-id="1f026-117">Run `dotnet sln add .\MathService\MathService.fsproj` to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="1f026-118">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="1f026-118">Creating the test project</span></span>

<span data-ttu-id="1f026-119">Затем создайте каталог *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="1f026-119">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="1f026-120">Ниже представлена структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="1f026-120">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="1f026-121">Перейдите в каталог *MathService.Tests* и создайте проект с помощью `dotnet new xunit -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="1f026-121">Make the *MathService.Tests* directory the current directory and create a new project using `dotnet new xunit -lang "F#"`.</span></span> <span data-ttu-id="1f026-122">Эта команда создает тестовый проект, использующий xUnit в качестве библиотеки тестов.</span><span class="sxs-lookup"><span data-stu-id="1f026-122">This creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="1f026-123">Созданный шаблон настраивает средство выполнения тестов в файле *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="1f026-123">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="1f026-124">Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда</span><span class="sxs-lookup"><span data-stu-id="1f026-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="1f026-125">В предыдущем шаге `dotnet new` добавила пакет xUnit и средство запуска xUnit.</span><span class="sxs-lookup"><span data-stu-id="1f026-125">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="1f026-126">Теперь добавьте в проект библиотеку классов `MathService` в качестве еще одной зависимости.</span><span class="sxs-lookup"><span data-stu-id="1f026-126">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="1f026-127">Используйте команду `dotnet add reference`:</span><span class="sxs-lookup"><span data-stu-id="1f026-127">Use the `dotnet add reference` command:</span></span>

```dotnetcli
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="1f026-128">Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="1f026-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="1f026-129">Ниже показан окончательный макет решения:</span><span class="sxs-lookup"><span data-stu-id="1f026-129">You have the following final solution layout:</span></span>

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

<span data-ttu-id="1f026-130">Выполните команду `dotnet sln add .\MathService.Tests\MathService.Tests.fsproj` в каталоге *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="1f026-130">Execute `dotnet sln add .\MathService.Tests\MathService.Tests.fsproj` in the *unit-testing-with-fsharp* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="1f026-131">Создание первого теста</span><span class="sxs-lookup"><span data-stu-id="1f026-131">Creating the first test</span></span>

<span data-ttu-id="1f026-132">Напишите один тест сбоя теста, запустите его, а затем повторите этот процесс.</span><span class="sxs-lookup"><span data-stu-id="1f026-132">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="1f026-133">Откройте файл *Tests.fs* и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="1f026-133">Open *Tests.fs* and add the following code:</span></span>

```fsharp
[<Fact>]
let ``My test`` () =
    Assert.True(true)

[<Fact>]
let ``Fail every time`` () = Assert.True(false)
```

<span data-ttu-id="1f026-134">Атрибут `[<Fact>]` обозначает метод теста, который выполняется с помощью средства выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="1f026-134">The `[<Fact>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="1f026-135">В каталоге *unit-testing-with-fsharp* выполните команду `dotnet test` для создания тестов и библиотеки классов, а затем выполните тесты.</span><span class="sxs-lookup"><span data-stu-id="1f026-135">From the *unit-testing-with-fsharp*, execute `dotnet test` to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="1f026-136">Средство запуска тестов xUnit содержит точку входа в программу для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="1f026-136">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="1f026-137">`dotnet test` запускает средство выполнения тестов с помощью проекта модульного теста, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="1f026-137">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="1f026-138">Эти два теста демонстрируют самые простые тесты, которые выполняются и завершаются сбоем.</span><span class="sxs-lookup"><span data-stu-id="1f026-138">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="1f026-139">`My test` выполняется успешно, а `Fail every time` завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="1f026-139">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="1f026-140">Сейчас создайте тест для метода `squaresOfOdds`.</span><span class="sxs-lookup"><span data-stu-id="1f026-140">Now, create a test for the `squaresOfOdds` method.</span></span> <span data-ttu-id="1f026-141">Метод `squaresOfOdds` возвращает последовательность квадратов всех нечетных целочисленных значений, которые являются частью входной последовательности.</span><span class="sxs-lookup"><span data-stu-id="1f026-141">The `squaresOfOdds` method returns a sequence of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="1f026-142">Вместо того чтобы писать все эти функции одновременно, можно постепенно создавать тесты, проверяющие функциональность.</span><span class="sxs-lookup"><span data-stu-id="1f026-142">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="1f026-143">Если тест выполняется успешно, создается необходимая функция метода.</span><span class="sxs-lookup"><span data-stu-id="1f026-143">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="1f026-144">Самый простой тест — вызов `squaresOfOdds` со всеми четными числами, где результатом должна быть пустая последовательность целых чисел.</span><span class="sxs-lookup"><span data-stu-id="1f026-144">The simplest test we can write is to call `squaresOfOdds` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="1f026-145">Вот этот тест:</span><span class="sxs-lookup"><span data-stu-id="1f026-145">Here's that test:</span></span>

```fsharp
[<Fact>]
let ``Sequence of Evens returns empty collection`` () =
    let expected = Seq.empty<int>
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.Equal<Collections.Generic.IEnumerable<int>>(expected, actual)
```

<span data-ttu-id="1f026-146">Тест не будет пройден.</span><span class="sxs-lookup"><span data-stu-id="1f026-146">Your test fails.</span></span> <span data-ttu-id="1f026-147">Вы еще не создали реализацию.</span><span class="sxs-lookup"><span data-stu-id="1f026-147">You haven't created the implementation yet.</span></span> <span data-ttu-id="1f026-148">Чтобы тест был пройден, напишите простейший код в классе `MathService`, который работает:</span><span class="sxs-lookup"><span data-stu-id="1f026-148">Make this test pass by writing the simplest code in the `MathService` class that works:</span></span>

```fsharp
let squaresOfOdds xs =
    Seq.empty<int>
```

<span data-ttu-id="1f026-149">В каталоге *unit-testing-with-fsharp* снова выполните команду `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="1f026-149">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="1f026-150">Команда `dotnet test` запускает сборку для проекта `MathService` и затем для проекта `MathService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="1f026-150">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="1f026-151">После сборки обоих проектов она запускает этот отдельный тест.</span><span class="sxs-lookup"><span data-stu-id="1f026-151">After building both projects, it runs this single test.</span></span> <span data-ttu-id="1f026-152">Он выполняется.</span><span class="sxs-lookup"><span data-stu-id="1f026-152">It passes.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="1f026-153">Выполнение требований</span><span class="sxs-lookup"><span data-stu-id="1f026-153">Completing the requirements</span></span>

<span data-ttu-id="1f026-154">Теперь, когда тест проходит успешно, пора создать дополнительные тесты.</span><span class="sxs-lookup"><span data-stu-id="1f026-154">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="1f026-155">Следующий простой пример работает с последовательностью, единственным нечетным числом которой является `1`.</span><span class="sxs-lookup"><span data-stu-id="1f026-155">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="1f026-156">Число 1 использовать проще, потому что квадрат 1 равен 1.</span><span class="sxs-lookup"><span data-stu-id="1f026-156">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="1f026-157">Вот этот тест:</span><span class="sxs-lookup"><span data-stu-id="1f026-157">Here's that next test:</span></span>

```fsharp
[<Fact>]
let ``Sequences of Ones and Evens returns Ones`` () =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.Equal<Collections.Generic.IEnumerable<int>>(expected, actual)
```

<span data-ttu-id="1f026-158">Выполнение `dotnet test` запускает ваши тесты. В результатах видно, что новый тест завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="1f026-158">Executing `dotnet test` runs your tests and shows you that the new test fails.</span></span> <span data-ttu-id="1f026-159">Теперь необходимо обновить метод `squaresOfOdds`, чтобы обработать этот новый тест.</span><span class="sxs-lookup"><span data-stu-id="1f026-159">Now, update the `squaresOfOdds` method to handle this new test.</span></span> <span data-ttu-id="1f026-160">Чтобы тест выполнялся успешно, необходимо отфильтровать все четные числа из последовательности.</span><span class="sxs-lookup"><span data-stu-id="1f026-160">You filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="1f026-161">Чтобы сделать это, напишите небольшую функцию фильтра и используйте `Seq.filter`:</span><span class="sxs-lookup"><span data-stu-id="1f026-161">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
```

<span data-ttu-id="1f026-162">Нужно выполнить еще один шаг: определить квадрат каждого из нечетных чисел.</span><span class="sxs-lookup"><span data-stu-id="1f026-162">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="1f026-163">Начнем с написания нового теста:</span><span class="sxs-lookup"><span data-stu-id="1f026-163">Start by writing a new test:</span></span>

```fsharp
[<Fact>]
let ``SquaresOfOdds works`` () =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.Equal(expected, actual)
```

<span data-ttu-id="1f026-164">Чтобы вычислить квадрат каждого нечетного числа, можно исправить тест, пропустив фильтрованную последовательность через операцию сопоставления:</span><span class="sxs-lookup"><span data-stu-id="1f026-164">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
```

<span data-ttu-id="1f026-165">Вы создали небольшую библиотеку и набор модульных тестов для нее.</span><span class="sxs-lookup"><span data-stu-id="1f026-165">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="1f026-166">Вы структурировали решение, чтобы сделать добавление новых пакетов и тестов частью обычного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="1f026-166">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="1f026-167">и получить возможность сосредоточиться на задачах приложения.</span><span class="sxs-lookup"><span data-stu-id="1f026-167">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f026-168">См. также</span><span class="sxs-lookup"><span data-stu-id="1f026-168">See also</span></span>

- [<span data-ttu-id="1f026-169">dotnet new</span><span class="sxs-lookup"><span data-stu-id="1f026-169">dotnet new</span></span>](../tools/dotnet-new.md)
- [<span data-ttu-id="1f026-170">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="1f026-170">dotnet sln</span></span>](../tools/dotnet-new.md)
- [<span data-ttu-id="1f026-171">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="1f026-171">dotnet add reference</span></span>](../tools/dotnet-add-reference.md)
- [<span data-ttu-id="1f026-172">dotnet test</span><span class="sxs-lookup"><span data-stu-id="1f026-172">dotnet test</span></span>](../tools/dotnet-test.md)
