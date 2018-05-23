---
title: Работа с LINQ
description: В этом руководстве мы научим вас создавать последовательности с помощью LINQ, создавать методы для использования в запросах LINQ, а также различать упреждающее и отложенное вычисление.
ms.date: 03/28/2017
ms.assetid: 0db12548-82cb-4903-ac88-13103d70aa77
ms.openlocfilehash: e5f9baab13cddfb9e294de1e1a6ce967ccbe0813
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
---
# <a name="working-with-linq"></a><span data-ttu-id="30eda-103">Работа с LINQ</span><span class="sxs-lookup"><span data-stu-id="30eda-103">Working with LINQ</span></span>

## <a name="introduction"></a><span data-ttu-id="30eda-104">Вступление</span><span class="sxs-lookup"><span data-stu-id="30eda-104">Introduction</span></span>

<span data-ttu-id="30eda-105">Это руководство раскроет для вас некоторые возможности .NET Core и языка C#.</span><span class="sxs-lookup"><span data-stu-id="30eda-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="30eda-106">Вы узнаете:</span><span class="sxs-lookup"><span data-stu-id="30eda-106">You’ll learn:</span></span>

*   <span data-ttu-id="30eda-107">как создать последовательности с помощью LINQ;</span><span class="sxs-lookup"><span data-stu-id="30eda-107">How to generate sequences with LINQ</span></span>
*   <span data-ttu-id="30eda-108">как написать методы, которые можно применять в запросах LINQ;</span><span class="sxs-lookup"><span data-stu-id="30eda-108">How to write methods that can be easily used in LINQ queries.</span></span>
*   <span data-ttu-id="30eda-109">как различать упреждающее и отложенное вычисление.</span><span class="sxs-lookup"><span data-stu-id="30eda-109">How to distinguish between eager and lazy evaluation.</span></span>

<span data-ttu-id="30eda-110">Вы освоите эти методы на примере приложения, которое демонстрирует один из основных навыков любого иллюзиониста: [тасовка по методу фаро](https://en.wikipedia.org/wiki/Faro_shuffle).</span><span class="sxs-lookup"><span data-stu-id="30eda-110">You'll learn these techniques by building an application that demonstrates one of the basic skills of any magician: the [faro shuffle](https://en.wikipedia.org/wiki/Faro_shuffle).</span></span> <span data-ttu-id="30eda-111">Так называют метод тасовки, при котором колода делится ровно на две части, а затем собирается заново так, что карты из каждой половины следуют строго поочередно.</span><span class="sxs-lookup"><span data-stu-id="30eda-111">Briefly, a faro shuffle is a technique where you split a card deck exactly in half, then the shuffle interleaves each one card from each half to rebuild the original deck.</span></span>

<span data-ttu-id="30eda-112">Этот метод очень удобен для иллюзионистов, поскольку положение каждой карты после каждой тасовки точно известно, и через несколько циклов порядок карт восстанавливается.</span><span class="sxs-lookup"><span data-stu-id="30eda-112">Magicians use this technique because every card is in a known location after each shuffle, and the order is a repeating pattern.</span></span> 

<span data-ttu-id="30eda-113">Здесь же мы используем его в качестве не слишком серьезного примера для процессов управления последовательностями данных.</span><span class="sxs-lookup"><span data-stu-id="30eda-113">For our purposes, it is a light hearted look at manipulating sequences of data.</span></span> <span data-ttu-id="30eda-114">Приложение, которое вы создадите, будет моделировать колоду карт и выполнять для них серию тасовок, выводя новый порядок карт после каждой из них.</span><span class="sxs-lookup"><span data-stu-id="30eda-114">The application you'll build will construct a card deck, and then perform a sequence of shuffles, writing the sequence out each time.</span></span> <span data-ttu-id="30eda-115">Вы сможете сравнить новый порядок карт с исходным.</span><span class="sxs-lookup"><span data-stu-id="30eda-115">You'll also compare the updated order to the original order.</span></span>

<span data-ttu-id="30eda-116">Это руководство описывает несколько шагов.</span><span class="sxs-lookup"><span data-stu-id="30eda-116">This tutorial has multiple steps.</span></span> <span data-ttu-id="30eda-117">После каждого из них вы сможете запустить приложение и оценить результаты.</span><span class="sxs-lookup"><span data-stu-id="30eda-117">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="30eda-118">[Готовый пример](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) доступен в репозитории dotnet/samples на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="30eda-118">You can also see the [completed sample](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) in the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="30eda-119">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="30eda-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="30eda-120">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="30eda-120">Prerequisites</span></span>

<span data-ttu-id="30eda-121">Компьютер должен быть настроен для выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="30eda-121">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="30eda-122">Инструкции по установке см. на странице [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="30eda-122">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="30eda-123">Это приложение можно запустить в ОС Windows, Ubuntu Linux, OS X или в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="30eda-123">You can run this application on Windows, Ubuntu Linux, OS X or in a Docker container.</span></span> <span data-ttu-id="30eda-124">Вам потребуется редактор кода, но вы можете выбрать любой привычный для вас.</span><span class="sxs-lookup"><span data-stu-id="30eda-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="30eda-125">В примерах ниже используется кроссплатформенный редактор [Visual Studio Code](https://code.visualstudio.com/) с открытым исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="30eda-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="30eda-126">Вы можете заменить его на любое другое средство, с которым вам удобно работать.</span><span class="sxs-lookup"><span data-stu-id="30eda-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="30eda-127">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="30eda-127">Create the Application</span></span>

<span data-ttu-id="30eda-128">Первым шагом является создание нового приложения.</span><span class="sxs-lookup"><span data-stu-id="30eda-128">The first step is to create a new application.</span></span> <span data-ttu-id="30eda-129">Откройте командную строку и создайте новый каталог для приложения.</span><span class="sxs-lookup"><span data-stu-id="30eda-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="30eda-130">Перейдите в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="30eda-130">Make that the current directory.</span></span> <span data-ttu-id="30eda-131">В командной строке введите команду `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="30eda-131">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="30eda-132">Эта команда создает начальный набор файлов для базового приложения Hello World.</span><span class="sxs-lookup"><span data-stu-id="30eda-132">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="30eda-133">Если вы раньше никогда не работали с C#, изучите структуру программы C# по [этому руководству](console-teleprompter.md).</span><span class="sxs-lookup"><span data-stu-id="30eda-133">If you've never used C# before, [this tutorial](console-teleprompter.md) explains the structure of a C# program.</span></span> <span data-ttu-id="30eda-134">Мы рекомендуем сначала ознакомиться с ним, а затем вернуться сюда и продолжить изучение LINQ.</span><span class="sxs-lookup"><span data-stu-id="30eda-134">You can read that and then return here to learn more about LINQ.</span></span> 

## <a name="creating-the-data-set"></a><span data-ttu-id="30eda-135">Создание набора данных</span><span class="sxs-lookup"><span data-stu-id="30eda-135">Creating the Data Set</span></span>

<span data-ttu-id="30eda-136">Первым делом мы создадим колоду карт.</span><span class="sxs-lookup"><span data-stu-id="30eda-136">Let's start by creating a deck of cards.</span></span> <span data-ttu-id="30eda-137">В этом вам поможет запрос LINQ по двум источникам (один для четырех мастей и второй для тринадцати достоинств).</span><span class="sxs-lookup"><span data-stu-id="30eda-137">You'll do this using a LINQ query that has two sources (one for the four suits, one for the thirteen values).</span></span> <span data-ttu-id="30eda-138">Эти источники объединяются в колоду из 52 карт.</span><span class="sxs-lookup"><span data-stu-id="30eda-138">You'll combine those sources into a 52 card deck.</span></span> <span data-ttu-id="30eda-139">Инструкция `Console.WriteLine` в цикле `foreach` отображает карты.</span><span class="sxs-lookup"><span data-stu-id="30eda-139">A `Console.WriteLine` statement inside a `foreach` loop displays the cards.</span></span>

<span data-ttu-id="30eda-140">Этот запрос выглядит так:</span><span class="sxs-lookup"><span data-stu-id="30eda-140">Here's the query:</span></span>

```csharp
var startingDeck = from s in Suits()
                   from r in Ranks()
                   select new { Suit = s, Rank = r };

foreach (var c in startingDeck)
{
    Console.WriteLine(c);
}
```

<span data-ttu-id="30eda-141">Несколько выражений `from` создают запрос `SelectMany`, который формирует одну последовательность из сочетаний каждого элемента первой последовательности с каждым элементом второй последовательности.</span><span class="sxs-lookup"><span data-stu-id="30eda-141">The multiple `from` clauses produce a `SelectMany`, which creates a single sequence from combining each element in the first sequence with each element in the second sequence.</span></span> <span data-ttu-id="30eda-142">Для нашего примера важен порядок последовательности.</span><span class="sxs-lookup"><span data-stu-id="30eda-142">The order is important for our purposes.</span></span> <span data-ttu-id="30eda-143">Первый элемент первой последовательности (масти) поочередно сочетается с каждым элементом второй последовательности (достоинства).</span><span class="sxs-lookup"><span data-stu-id="30eda-143">The first element in the first source sequence (Suits) is combined with every element in the second sequence (Values).</span></span> <span data-ttu-id="30eda-144">В итоге мы получаем все тринадцать карт первой масти.</span><span class="sxs-lookup"><span data-stu-id="30eda-144">This produces all thirteen cards of first suit.</span></span> <span data-ttu-id="30eda-145">Этот процесс повторяется для каждого элемента первой последовательности (масти).</span><span class="sxs-lookup"><span data-stu-id="30eda-145">That process is repeated with each element in the first sequence (Suits).</span></span> <span data-ttu-id="30eda-146">Конечным результатом является колода карт, упорядоченная сначала по мастям, а затем по достоинствам.</span><span class="sxs-lookup"><span data-stu-id="30eda-146">The end result is a deck of cards ordered by suits, followed by values.</span></span>

<span data-ttu-id="30eda-147">Теперь нам нужно создать методы Suits() и Ranks().</span><span class="sxs-lookup"><span data-stu-id="30eda-147">Next, you'll need to build the Suits() and Ranks() methods.</span></span> <span data-ttu-id="30eda-148">Начнем мы с самых простых *методов итератора*, которые создают последовательность в виде перечисления строк:</span><span class="sxs-lookup"><span data-stu-id="30eda-148">Let's start with a really simple set of *iterator methods* that generate the sequence as an enumerable of strings:</span></span>

```csharp
static IEnumerable<string> Suits()
{
    yield return "clubs";
    yield return "diamonds";
    yield return "hearts";
    yield return "spades";
}

static IEnumerable<string> Ranks()
{
    yield return "two";
    yield return "three";
    yield return "four";
    yield return "five";
    yield return "six";
    yield return "seven";
    yield return "eight";
    yield return "nine";
    yield return "ten";
    yield return "jack";
    yield return "queen";
    yield return "king";
    yield return "ace";
}
```

<span data-ttu-id="30eda-149">Оба эти два метода используют синтаксис `yield return`, создавая последовательность по мере выполнения.</span><span class="sxs-lookup"><span data-stu-id="30eda-149">These two methods both utilize the `yield return` syntax to produce a sequence as they run.</span></span> <span data-ttu-id="30eda-150">Компилятор создаст объект, который реализует интерфейс `IEnumerable<T>`, и сохранит в него последовательность строк по мере их получения.</span><span class="sxs-lookup"><span data-stu-id="30eda-150">The compiler builds an object that implements `IEnumerable<T>` and generates the sequence of strings as they are requested.</span></span>

<span data-ttu-id="30eda-151">Теперь давайте выполним пример, который вы создали к этому моменту.</span><span class="sxs-lookup"><span data-stu-id="30eda-151">Go ahead and run the sample you've built at this point.</span></span> <span data-ttu-id="30eda-152">Он отобразит все 52 карты колоды.</span><span class="sxs-lookup"><span data-stu-id="30eda-152">It will display all 52 cards in the deck.</span></span> <span data-ttu-id="30eda-153">Возможно, вам будет интересно выполнить этот пример в отладчике и проследить за выполнением методов `Suits()` и `Values()`.</span><span class="sxs-lookup"><span data-stu-id="30eda-153">You may find it very helpful to run this sample under a debugger to observe how the `Suits()` and `Values()` methods execute.</span></span> <span data-ttu-id="30eda-154">Вы сможете заметить, что каждая строка в каждой последовательности создается только по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="30eda-154">You can clearly see that each string in each sequence is generated only as it is needed.</span></span>

![Окно консоли с приложением, которое выводит 52 карты](./media/working-with-linq/console.png)

## <a name="manipulating-the-order"></a><span data-ttu-id="30eda-156">Управление порядком</span><span class="sxs-lookup"><span data-stu-id="30eda-156">Manipulating the Order</span></span>

<span data-ttu-id="30eda-157">Теперь мы создадим служебный метод, который выполняет тасовку.</span><span class="sxs-lookup"><span data-stu-id="30eda-157">Next, let's build a utility method that can perform the shuffle.</span></span> <span data-ttu-id="30eda-158">Сначала он разделит нашу колоду на две части.</span><span class="sxs-lookup"><span data-stu-id="30eda-158">The first step is to split the deck in two.</span></span> <span data-ttu-id="30eda-159">Эту возможность нам предоставят методы `Take()` и `Skip()`, входящие в интерфейсы API LINQ:</span><span class="sxs-lookup"><span data-stu-id="30eda-159">The `Take()` and `Skip()` methods that are part of the LINQ APIs provide that feature for us:</span></span>

```csharp
var top = startingDeck.Take(26);
var bottom = startingDeck.Skip(26);
```

<span data-ttu-id="30eda-160">Метод для тасовки не реализован в стандартной библиотеке, поэтому вам нужно написать собственный.</span><span class="sxs-lookup"><span data-stu-id="30eda-160">The shuffle method doesn't exist in the standard library, so you'll have to write your own.</span></span> <span data-ttu-id="30eda-161">Этот новый метод использует несколько приемов, которые часто нужны в приложениях LINQ. Сейчас мы по порядку объясним вам каждый элемент этого метода.</span><span class="sxs-lookup"><span data-stu-id="30eda-161">This new method illustrates several techniques that you'll use with LINQ-based programs, so let's explain each part of the method in steps.</span></span>

<span data-ttu-id="30eda-162">Сигнатура этого метода создает *метод расширения*:</span><span class="sxs-lookup"><span data-stu-id="30eda-162">The signature for the method creates an *extension method*:</span></span>

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T>
    (this IEnumerable<T> first, IEnumerable<T> second)
```

<span data-ttu-id="30eda-163">Метод расширения представляет собой специализированный *статический метод.*</span><span class="sxs-lookup"><span data-stu-id="30eda-163">An extension method is a special purpose *static method.*</span></span> <span data-ttu-id="30eda-164">Как вы видите, для первого аргумента этого метода добавлен модификатор `this`.</span><span class="sxs-lookup"><span data-stu-id="30eda-164">You can see the addition of the `this` modifier on the first argument to the method.</span></span> <span data-ttu-id="30eda-165">Это означает, что метод вызывается так, как если бы он был методом-членом и имел тип, указанный для первого аргумента.</span><span class="sxs-lookup"><span data-stu-id="30eda-165">That means you call the method as though it were a member method of the type of the first argument.</span></span>

<span data-ttu-id="30eda-166">Методы расширения можно объявлять только внутри классов `static`, поэтому нам нужен новый статический класс с именем `extensions`.</span><span class="sxs-lookup"><span data-stu-id="30eda-166">Extension methods can be declared only inside `static` classes, so let's create a new static class called `extensions` for this functionality.</span></span> <span data-ttu-id="30eda-167">При дальнейшей работе с этим руководством вы будете добавлять дополнительные методы, помещая их в этот же класс.</span><span class="sxs-lookup"><span data-stu-id="30eda-167">You'll add more extension methods as you continue this tutorial, and those will be placed in the same class.</span></span>

<span data-ttu-id="30eda-168">Такое объявление методов соответствует стандартному принципу, по которому для входа и выхода используется тип `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="30eda-168">This method declaration also follows a standard idiom where the input and output types are `IEnumerable<T>`.</span></span> <span data-ttu-id="30eda-169">Такая практика позволяет объединять методы LINQ в цепочку, чтобы создавать более сложные запросы.</span><span class="sxs-lookup"><span data-stu-id="30eda-169">That practice enables LINQ methods to be chained together to perform more complex queries.</span></span>

```csharp
using System.Collections.Generic;

namespace LinqFaroShuffle
{
    public static class Extensions
    {
        public static IEnumerable<T> InterleaveSequenceWith<T>
            (this IEnumerable<T> first, IEnumerable<T> second)
        {
            // implementation coming.
        }
    }
}
```

<span data-ttu-id="30eda-170">Затем следует одновременно выполнить перечисление обоих последовательностей, поочередно помещая элементы в объединенный объект.</span><span class="sxs-lookup"><span data-stu-id="30eda-170">You will be enumerating both sequences at once, interleaving the elements, and creating one object.</span></span>  <span data-ttu-id="30eda-171">Чтобы создать метод LINQ, который работает с двумя последовательностями, важно хорошо понимать принципы работы `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="30eda-171">Writing a LINQ method that works with two sequences requires that you understand how `IEnumerable` works.</span></span>

<span data-ttu-id="30eda-172">Интерфейс `IEnumerable` содержит один метод: `GetEnumerator()`.</span><span class="sxs-lookup"><span data-stu-id="30eda-172">The `IEnumerable` interface has one method: `GetEnumerator()`.</span></span> <span data-ttu-id="30eda-173">Этот метод `GetEnumerator()` возвращает объект, у которого есть метод для перехода к следующему элементу и свойство, которое возвращает текущий элемент в последовательности.</span><span class="sxs-lookup"><span data-stu-id="30eda-173">The object returned by `GetEnumerator()` has a method to move to the next element, and a property that retrieves the current element in the sequence.</span></span> <span data-ttu-id="30eda-174">С помощью этих двух членов вы выполните перебор всей коллекции и получение элементов.</span><span class="sxs-lookup"><span data-stu-id="30eda-174">You will use those two members to enumerate the collection and return the elements.</span></span> <span data-ttu-id="30eda-175">Метод Interleave будет реализован как метод итератора, поэтому вы не будете создавать и возвращать коллекцию, а примените описанный выше синтаксис `yield return`.</span><span class="sxs-lookup"><span data-stu-id="30eda-175">This Interleave method will be an iterator method, so instead of building a collection and returning the collection, you'll use the `yield return` syntax shown above.</span></span> 

<span data-ttu-id="30eda-176">Так выглядит реализация этого метода:</span><span class="sxs-lookup"><span data-stu-id="30eda-176">Here's the implementation of that method:</span></span>

[!CODE-csharp[InterleaveSequenceWith](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

<span data-ttu-id="30eda-177">Теперь, добавив в проект этот метод, вернитесь к методу `Main` и один раз перетасуйте колоду:</span><span class="sxs-lookup"><span data-stu-id="30eda-177">Now that you've written this method, go back to the `Main` method and shuffle the deck once:</span></span>

```csharp
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }
        
    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
    var shuffle = top.InterleaveSequenceWith(bottom);

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }
}
```

## <a name="comparisons"></a><span data-ttu-id="30eda-178">Сравнения</span><span class="sxs-lookup"><span data-stu-id="30eda-178">Comparisons</span></span>

<span data-ttu-id="30eda-179">Давайте посмотрим, через сколько тасовок колода снова соберется в исходном порядке.</span><span class="sxs-lookup"><span data-stu-id="30eda-179">Let's see how many shuffles it takes to set the deck back to its original order.</span></span> <span data-ttu-id="30eda-180">Для этого вам нужен метод, который проверяет равенство двух последовательностей.</span><span class="sxs-lookup"><span data-stu-id="30eda-180">You'll need to write a method that determines if two sequences are equal.</span></span> <span data-ttu-id="30eda-181">Создав такой метод, вы поместите код тасовки колоды в цикл, в котором будете проверять, расположены ли карты в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="30eda-181">After you have that method, you'll need to place the code that shuffles the deck in a loop, and check to see when the deck is back in order.</span></span>

<span data-ttu-id="30eda-182">Метод, который сравнивает две последовательности, будет очень простым.</span><span class="sxs-lookup"><span data-stu-id="30eda-182">Writing a method to determine if the two sequences are equal should be straightforward.</span></span> <span data-ttu-id="30eda-183">По структуре он похож на метод, который мы создали для тасовки колоды.</span><span class="sxs-lookup"><span data-stu-id="30eda-183">It's a similar structure to the method you wrote to shuffle the deck.</span></span> <span data-ttu-id="30eda-184">Но теперь вместо команды yield return, которая возвращает элементы, вы будете сравнивать элементы каждой последовательности.</span><span class="sxs-lookup"><span data-stu-id="30eda-184">Only this time, instead of yield returning each element, you'll compare the matching elements of each sequence.</span></span> <span data-ttu-id="30eda-185">Если перечисление последовательности завершилось и все элементы попарно совпадают, то последовательности считаются одинаковыми:</span><span class="sxs-lookup"><span data-stu-id="30eda-185">When the entire sequence has been enumerated, if every element matches, the sequences are the same:</span></span>

[!CODE-csharp[SequenceEquals](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

<span data-ttu-id="30eda-186">Здесь мы видим в действии второй принцип Linq: терминальные методы.</span><span class="sxs-lookup"><span data-stu-id="30eda-186">This shows a second Linq idiom: terminal methods.</span></span> <span data-ttu-id="30eda-187">Они принимают последовательность в качестве входных данных (или две последовательности, как в нашем примере) и возвращают скалярное значение.</span><span class="sxs-lookup"><span data-stu-id="30eda-187">They take a sequence as input (or in this case, two sequences), and return a single scalar value.</span></span> <span data-ttu-id="30eda-188">Если вы используете такой метод, он должен быть последним методом в запросе.</span><span class="sxs-lookup"><span data-stu-id="30eda-188">These methods, when they are used, are always the final method of a query.</span></span> <span data-ttu-id="30eda-189">(Поэтому они так и называются.)</span><span class="sxs-lookup"><span data-stu-id="30eda-189">(Hence the name).</span></span> 

<span data-ttu-id="30eda-190">Этот принцип мы применяем при определении того, находится ли колода в исходном порядке.</span><span class="sxs-lookup"><span data-stu-id="30eda-190">You can see this in action when you use it to determine when the deck is back in its original order.</span></span> <span data-ttu-id="30eda-191">Поместите код тасовки в цикл, который будет останавливаться в том случае, когда порядок последовательности восстановлен. Для проверки примените метод `SequenceEquals()`.</span><span class="sxs-lookup"><span data-stu-id="30eda-191">Put the shuffle code inside a loop, and stop when the sequence is back in its original order by applying the `SequenceEquals()` method.</span></span> <span data-ttu-id="30eda-192">Как вы уже поняли, этот метод всегда будет последним в любом запросе, поскольку он возвращает одиночное значение, а не последовательность:</span><span class="sxs-lookup"><span data-stu-id="30eda-192">You can see it would always be the final method in any query, because it returns a single value instead of a sequence:</span></span>

```csharp
var times = 0;
var shuffle = startingDeck;

do
{
    shuffle = shuffle.Take(26).InterleaveSequenceWith(shuffle.Skip(26));

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }

    Console.WriteLine();
    times++;
} while (!startingDeck.SequenceEquals(shuffle));

Console.WriteLine(times);
```

<span data-ttu-id="30eda-193">Запустите пример и следите, как изменяется порядок карт при каждой тасовке. Уже после 8 итераций восстанавливается исходный порядок колоды.</span><span class="sxs-lookup"><span data-stu-id="30eda-193">Run the sample, and see how the deck rearranges on each shuffle, until it returns to its original configuration after 8 iterations.</span></span>

## <a name="optimizations"></a><span data-ttu-id="30eda-194">Оптимизация</span><span class="sxs-lookup"><span data-stu-id="30eda-194">Optimizations</span></span>

<span data-ttu-id="30eda-195">Пример, который вы создали к этому моменту, выполняет *внутреннюю тасовку*, то есть первая и последняя карты колоды сохраняют свои позиции после каждой итерации.</span><span class="sxs-lookup"><span data-stu-id="30eda-195">The sample you've built so far executes an *out shuffle*, where the top and bottom cards stay the same on each run.</span></span> <span data-ttu-id="30eda-196">Давайте внесем одно изменение, чтобы реализовать *внешнюю тасовку*, при которой все 52 карты изменяют свои позиции.</span><span class="sxs-lookup"><span data-stu-id="30eda-196">Let's make one change, and run an *in shuffle*, where all 52 cards change position.</span></span> <span data-ttu-id="30eda-197">Для этого колоду нужно собирать так, чтобы первой картой в колоде стала первая карта из нижней половины.</span><span class="sxs-lookup"><span data-stu-id="30eda-197">For an in shuffle, you interleave the deck so that the first card in the bottom half becomes the first card in the deck.</span></span> <span data-ttu-id="30eda-198">Тогда самой нижней картой станет последняя карта из верхней половины колоды.</span><span class="sxs-lookup"><span data-stu-id="30eda-198">That means the last card in the top half becomes the bottom card.</span></span> <span data-ttu-id="30eda-199">Нам нужно изменить всего одну строку.</span><span class="sxs-lookup"><span data-stu-id="30eda-199">That's just a one line change.</span></span> <span data-ttu-id="30eda-200">Измените вызов тасовки, поменяв местами нижнюю и верхнюю половины колоды.</span><span class="sxs-lookup"><span data-stu-id="30eda-200">Update the call to shuffle to change the order of the top and bottom halves of the deck:</span></span>

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

<span data-ttu-id="30eda-201">Снова запустите программу, и вы увидите, что для восстановления исходного порядка теперь требуется 52 итерации.</span><span class="sxs-lookup"><span data-stu-id="30eda-201">Run the program again, and you'll see that it takes 52 iterations for the deck to reorder itself.</span></span> <span data-ttu-id="30eda-202">Также вы могли обратить внимание, что по мере выполнения программы она заметным образом замедляется.</span><span class="sxs-lookup"><span data-stu-id="30eda-202">You'll also start to notice some serious performance degradations as the program continues to run.</span></span>

<span data-ttu-id="30eda-203">Для этого есть сразу несколько причин.</span><span class="sxs-lookup"><span data-stu-id="30eda-203">There are a number of reasons for this.</span></span> <span data-ttu-id="30eda-204">Для начала мы рассмотрим одну из самых существенных — неэффективное использование *отложенного вычисления*.</span><span class="sxs-lookup"><span data-stu-id="30eda-204">Let's tackle one of the major causes: inefficient use of *lazy evaluation*.</span></span>

<span data-ttu-id="30eda-205">LINQ запросы обрабатываются отложенным образом.</span><span class="sxs-lookup"><span data-stu-id="30eda-205">LINQ queries are evaluated lazily.</span></span> <span data-ttu-id="30eda-206">Последовательности создаются только тогда, когда происходит обращение к их элементам.</span><span class="sxs-lookup"><span data-stu-id="30eda-206">The sequences are generated only as the elements are requested.</span></span> <span data-ttu-id="30eda-207">Обычно это дает LINQ огромное преимущество.</span><span class="sxs-lookup"><span data-stu-id="30eda-207">Usually, that's a major benefit of LINQ.</span></span> <span data-ttu-id="30eda-208">Но в некоторых программах, таких как в нашем примере, это приводит к экспоненциальному росту времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="30eda-208">However, in a use such as this program, this causes exponential growth in execution time.</span></span>

<span data-ttu-id="30eda-209">Исходная колода было создана с помощью запроса LINQ.</span><span class="sxs-lookup"><span data-stu-id="30eda-209">The original deck was generated using a LINQ query.</span></span> <span data-ttu-id="30eda-210">Каждая последующая тасовка выполняет три запроса LINQ к колоде, полученной на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="30eda-210">Each shuffle is generated by performing three LINQ queries on the previous deck.</span></span> <span data-ttu-id="30eda-211">И все эти запросы выполняются отложенно.</span><span class="sxs-lookup"><span data-stu-id="30eda-211">All these are performed lazily.</span></span> <span data-ttu-id="30eda-212">В частности, это означает, что запросы выполняются каждый раз при обращении к последовательности.</span><span class="sxs-lookup"><span data-stu-id="30eda-212">That also means they are performed again each time the sequence is requested.</span></span> <span data-ttu-id="30eda-213">Таким образом, пока вы доберетесь до 52-й итерации, исходная колода будет заново создана очень много раз.</span><span class="sxs-lookup"><span data-stu-id="30eda-213">By the time you get to the 52nd iteration, you're regenerating the original deck many, many times.</span></span> <span data-ttu-id="30eda-214">Чтобы наглядно это продемонстрировать, давайте создадим журнал выполнения.</span><span class="sxs-lookup"><span data-stu-id="30eda-214">Let's write a log to demonstrate this behavior.</span></span> <span data-ttu-id="30eda-215">Затем вы исправите эту проблему.</span><span class="sxs-lookup"><span data-stu-id="30eda-215">Then, you'll fix it.</span></span>

<span data-ttu-id="30eda-216">Вот метод ведения журнала, который можно добавить к любому запросу, чтобы зафиксировать его выполнение.</span><span class="sxs-lookup"><span data-stu-id="30eda-216">Here's a log method that can be appended to any query to mark that the query executed.</span></span>

[!CODE-csharp[LogQuery](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

<span data-ttu-id="30eda-217">Теперь давайте дополним определение каждого запроса сообщением для журнала:</span><span class="sxs-lookup"><span data-stu-id="30eda-217">Next, instrument the definition of each query with a log message:</span></span>

```csharp
public static void Main(string[] args)
{
    var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                        from r in Ranks().LogQuery("Rank Generation")
                        select new { Suit = s, Rank = r }).LogQuery("Starting Deck");

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }
        
    Console.WriteLine();
    var times = 0;
    var shuffle = startingDeck;

    do
    {
        /*
        shuffle = shuffle.Take(26)
            .LogQuery("Top Half")
            .InterleaveSequenceWith(shuffle.Skip(26)
            .LogQuery("Bottom Half"))
            .LogQuery("Shuffle");
        */

        shuffle = shuffle.Skip(26)
            .LogQuery("Bottom Half")
            .InterleaveSequenceWith(shuffle.Take(26).LogQuery("Top Half"))
            .LogQuery("Shuffle");

        foreach (var c in shuffle)
        {
            Console.WriteLine(c);
        }

        times++;
        Console.WriteLine(times);
    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

<span data-ttu-id="30eda-218">Обратите внимание, что запись в журнал не нужно выполнять при обращении к запросу.</span><span class="sxs-lookup"><span data-stu-id="30eda-218">Notice that you don't log every time you access a query.</span></span> <span data-ttu-id="30eda-219">Она выполняется только при создании исходного запроса.</span><span class="sxs-lookup"><span data-stu-id="30eda-219">You log only when you create the original query.</span></span> <span data-ttu-id="30eda-220">Программа по-прежнему работает очень долго, но теперь вы хорошо видите, почему.</span><span class="sxs-lookup"><span data-stu-id="30eda-220">The program still takes a long time to run, but now you can see why.</span></span> <span data-ttu-id="30eda-221">Если у вас не хватит терпения выполнять внешнюю тасовку фаро с ведением журнала, переключите программу обратно на внутреннюю тасовку.</span><span class="sxs-lookup"><span data-stu-id="30eda-221">If you run out of patience running the inner shuffle with logging turned on, switch back to the outer shuffle.</span></span> <span data-ttu-id="30eda-222">На ней вы также заметите влияние отложенного вычисления.</span><span class="sxs-lookup"><span data-stu-id="30eda-222">You'll still see the lazy evaluation effects.</span></span> <span data-ttu-id="30eda-223">За один запуск программа выполняет 2592 запроса, если учитывать все создания мастей и достоинств.</span><span class="sxs-lookup"><span data-stu-id="30eda-223">In one run, it executes 2592 queries, including all the value and suit generation.</span></span>

<span data-ttu-id="30eda-224">Есть очень простой способ изменить программу так, чтобы избежать лишних выполнений.</span><span class="sxs-lookup"><span data-stu-id="30eda-224">There is an easy way to update this program to avoid all those executions.</span></span> <span data-ttu-id="30eda-225">Методы LINQ `ToArray()` и `ToList()` позволяют выполнить запрос и сохранить результаты в массив или список, соответственно.</span><span class="sxs-lookup"><span data-stu-id="30eda-225">There are LINQ methods `ToArray()` and `ToList()` that cause the query to run, and store the results in an array or a list, respectively.</span></span> <span data-ttu-id="30eda-226">Используйте эти методы, чтобы результаты запроса кэшировались, а не создавались заново каждый раз.</span><span class="sxs-lookup"><span data-stu-id="30eda-226">You use these methods to cache the data results of a query rather than execute the source query again.</span></span>  <span data-ttu-id="30eda-227">К запросам, которые формируют колоды карт, добавьте вызов `ToArray()` и снова запустите запрос:</span><span class="sxs-lookup"><span data-stu-id="30eda-227">Append the queries that generate the card decks with a call to `ToArray()` and run the query again:</span></span>

[!CODE-csharp[Main](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

<span data-ttu-id="30eda-228">При запуске такой программы с внутренней тасовкой выполняется всего 30 запросов.</span><span class="sxs-lookup"><span data-stu-id="30eda-228">Run again, and the outer shuffle is down to 30 queries.</span></span> <span data-ttu-id="30eda-229">Переключите программу на внешнюю тасовку, и вы заметите аналогичное улучшение.</span><span class="sxs-lookup"><span data-stu-id="30eda-229">Run again with the inner shuffle and you'll see similar improvements.</span></span> <span data-ttu-id="30eda-230">(Теперь она выполняет 162 запроса.)</span><span class="sxs-lookup"><span data-stu-id="30eda-230">(It now executes 162 queries).</span></span>

<span data-ttu-id="30eda-231">Но не стоит на основании этого примера делать вывод, что все запросы должны выполняться упреждающе.</span><span class="sxs-lookup"><span data-stu-id="30eda-231">Don't misinterpret this example by thinking that all queries should run eagerly.</span></span> <span data-ttu-id="30eda-232">Этот пример лишь демонстрирует отдельный случай, в котором отложенное вычисление приводит к проблемам с производительностью.</span><span class="sxs-lookup"><span data-stu-id="30eda-232">This example is designed to highlight the use cases where lazy evaluation can cause performance difficulties.</span></span> <span data-ttu-id="30eda-233">Это связано с тем, что каждое новое расположение карт вычисляется на основе предыдущего расположения.</span><span class="sxs-lookup"><span data-stu-id="30eda-233">That's because each new arrangement of the deck of cards is built from the previous arrangement.</span></span> <span data-ttu-id="30eda-234">Использование отложенного вычисления означает, что каждое расположение колоды строится с самого начала, из исходной колоды, включая вызов кода для создания `startingDeck`.</span><span class="sxs-lookup"><span data-stu-id="30eda-234">Using lazy evaluation means each new deck configuration is built from the original deck, even executing the code that built the `startingDeck`.</span></span> <span data-ttu-id="30eda-235">Это создает огромный объем дополнительной работы.</span><span class="sxs-lookup"><span data-stu-id="30eda-235">That causes a large amount of extra work.</span></span> 

<span data-ttu-id="30eda-236">На практике некоторые алгоритмы работают намного быстрее с упреждающим вычислением, а другие лучше выполняются с отложенным вычислением.</span><span class="sxs-lookup"><span data-stu-id="30eda-236">In practice, some algorithms run much better using eager evaluation, and others run much better using lazy evaluation.</span></span> <span data-ttu-id="30eda-237">(Обычно отложенное вычисление дает более хороший результат, если в качестве источника данных используется отдельный процесс, например база данных.</span><span class="sxs-lookup"><span data-stu-id="30eda-237">(In general, lazy evaluation is a much better choice when the data source is a separate process, like a database engine.</span></span> <span data-ttu-id="30eda-238">Тогда отложенное вычисление позволяет сложным запросам выполнять только один цикл обращения к процессу базы данных.) LINQ поддерживает как упреждающее, так и отложенное вычисление.</span><span class="sxs-lookup"><span data-stu-id="30eda-238">In those cases, lazy evaluation enables more complex queries to execute only one round trip to the database process.) LINQ enables both lazy and eager evaluation.</span></span> <span data-ttu-id="30eda-239">Проведите тесты и выберите тот вариант, который даст лучшие результаты.</span><span class="sxs-lookup"><span data-stu-id="30eda-239">Measure, and pick the best choice.</span></span>

## <a name="preparing-for-new-features"></a><span data-ttu-id="30eda-240">Подготовка новых функций</span><span class="sxs-lookup"><span data-stu-id="30eda-240">Preparing for New Features</span></span>

<span data-ttu-id="30eda-241">Код, который вы написали при изучении этого руководства, служит хорошим примером создания простого прототипа для выполнения работы.</span><span class="sxs-lookup"><span data-stu-id="30eda-241">The code you've written for this sample is an example of creating a simple prototype that does the job.</span></span> <span data-ttu-id="30eda-242">Это отличный способ для изучения проблемы, а для многих задач он предоставит оптимальное долгосрочное решение.</span><span class="sxs-lookup"><span data-stu-id="30eda-242">This is a great way to explore a problem space, and for many features, it may be the best permanent solution.</span></span> <span data-ttu-id="30eda-243">Вы применили *анонимные типы* для карт, каждая из которых была представлена строковым значением.</span><span class="sxs-lookup"><span data-stu-id="30eda-243">You've leveraged *anonymous types* for the cards, and each card is represented by strings.</span></span>

<span data-ttu-id="30eda-244">*Анонимные типы* дают много преимуществ для производительности.</span><span class="sxs-lookup"><span data-stu-id="30eda-244">*Anonymous Types* have many productivity advantages.</span></span> <span data-ttu-id="30eda-245">Вам не нужно самостоятельно определять класс, представляющий хранилище.</span><span class="sxs-lookup"><span data-stu-id="30eda-245">You don't need to define a class yourself to represent the storage.</span></span> <span data-ttu-id="30eda-246">Компилятор создает для вас нужный тип.</span><span class="sxs-lookup"><span data-stu-id="30eda-246">The compiler generates the type for you.</span></span> <span data-ttu-id="30eda-247">Тип, созданный компилятором, использует многие современные рекомендации по работе с простыми объектами данных.</span><span class="sxs-lookup"><span data-stu-id="30eda-247">The compiler generated type utilizes many of the best practices for simple data objects.</span></span> <span data-ttu-id="30eda-248">Он будет *неизменяемым*, то есть ни одно из его свойств нельзя изменить после создания.</span><span class="sxs-lookup"><span data-stu-id="30eda-248">It's *immutable*, meaning that none of its properties can be changed after it has been constructed.</span></span> <span data-ttu-id="30eda-249">Анонимные типы являются внутренними для сборки, поэтому они не считаются частью открытого API для этой сборки.</span><span class="sxs-lookup"><span data-stu-id="30eda-249">Anonymous types are internal to an assembly, so they aren't seen as part of the public API for that assembly.</span></span> <span data-ttu-id="30eda-250">Также анонимные типы переопределяют метод `ToString()`, который возвращает форматированную строку с каждым из значений.</span><span class="sxs-lookup"><span data-stu-id="30eda-250">Anonymous types also contain an override of the `ToString()` method that returns a formatted string with each of the values.</span></span>

<span data-ttu-id="30eda-251">Но у анонимных типов есть и недостатки.</span><span class="sxs-lookup"><span data-stu-id="30eda-251">Anonymous types also have disadvantages.</span></span> <span data-ttu-id="30eda-252">Они не имеют описательных имен, поэтому их нельзя использовать в качестве возвращаемых значений или аргументов.</span><span class="sxs-lookup"><span data-stu-id="30eda-252">They don't have accessible names, so you can't use them as return values or arguments.</span></span> <span data-ttu-id="30eda-253">Возможно, вы обратили внимание, что анонимные типы использовались выше только в универсальных методах.</span><span class="sxs-lookup"><span data-stu-id="30eda-253">You'll notice that any methods above that used these anonymous types are generic methods.</span></span> <span data-ttu-id="30eda-254">По мере роста приложения и добавления новых функций вас перестанет устраивать переопределение метода `ToString()`.</span><span class="sxs-lookup"><span data-stu-id="30eda-254">The override of `ToString()` may not be what you want as the application grows more features.</span></span> 

<span data-ttu-id="30eda-255">Также в этом примере используются строки для представления мастей и достоинств каждой карты.</span><span class="sxs-lookup"><span data-stu-id="30eda-255">The sample also uses strings for the suit and the rank of each card.</span></span> <span data-ttu-id="30eda-256">Это слишком многовариантный формат.</span><span class="sxs-lookup"><span data-stu-id="30eda-256">That's quite open ended.</span></span> <span data-ttu-id="30eda-257">Система типов C# позволяет улучшить код, используя для таких значений типы `enum`.</span><span class="sxs-lookup"><span data-stu-id="30eda-257">The C# type system can help us make better code, by leveraging `enum` types for those values.</span></span>

<span data-ttu-id="30eda-258">Сначала займемся мастями.</span><span class="sxs-lookup"><span data-stu-id="30eda-258">Start with the suits.</span></span> <span data-ttu-id="30eda-259">Самое время применить для них `enum`:</span><span class="sxs-lookup"><span data-stu-id="30eda-259">This is a perfect time to use an `enum`:</span></span>

[!CODE-csharp[Suit enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet2)]

<span data-ttu-id="30eda-260">Для метода `Suits()` также изменится тип и реализация:</span><span class="sxs-lookup"><span data-stu-id="30eda-260">The `Suits()` method also changes type and implementation:</span></span>

[!CODE-csharp[Suit IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet4)]

<span data-ttu-id="30eda-261">Затем выполните те же изменения для достоинства карт:</span><span class="sxs-lookup"><span data-stu-id="30eda-261">Next, do the same change with the Rank of the cards:</span></span>

[!CODE-csharp[Rank enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet3)]

<span data-ttu-id="30eda-262">И для метода, который их создает:</span><span class="sxs-lookup"><span data-stu-id="30eda-262">And the method that generates them:</span></span>

[!CODE-csharp[Rank IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet5)]

<span data-ttu-id="30eda-263">В качестве финального штриха давайте создадим тип для представления карты, не полагаясь на анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="30eda-263">As one final cleanup, let's make a type to represent the card, instead of relying on an anonymous type.</span></span> <span data-ttu-id="30eda-264">Анонимные типы отлично подходят для упрощенных решений и локальных типов, но в нашем примере игральная карта является одним из главных понятий.</span><span class="sxs-lookup"><span data-stu-id="30eda-264">Anonymous types are great for lightweight, local types, but in this example, the playing card is one of the main concepts.</span></span> <span data-ttu-id="30eda-265">Она должно быть представлена конкретным типом.</span><span class="sxs-lookup"><span data-stu-id="30eda-265">It should be a concrete type.</span></span>

[!CODE-csharp[PlayingCard](../../../samples/csharp/getting-started/console-linq/playingcard.cs?name=snippet1)]

<span data-ttu-id="30eda-266">Этот тип использует *автоматически реализуемые свойства только для чтения*, которые устанавливаются в конструкторе и более не могут изменяться.</span><span class="sxs-lookup"><span data-stu-id="30eda-266">This type uses *auto-implemented read-only properties* which are set in the constructor, and then cannot be modified.</span></span> <span data-ttu-id="30eda-267">Также в нем используется функция [интерполяции строк](../language-reference/tokens/interpolated.md), которая упрощает форматирование строкового вывода.</span><span class="sxs-lookup"><span data-stu-id="30eda-267">It also makes use of the [string interpolation](../language-reference/tokens/interpolated.md) feature that makes it easier to format string output.</span></span>

<span data-ttu-id="30eda-268">Измените запрос, который создает начальную колоду, с учетом нового типа:</span><span class="sxs-lookup"><span data-stu-id="30eda-268">Update the query that generates the starting deck to use the new type:</span></span>

```csharp
var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                    from r in Ranks().LogQuery("Value Generation")
                    select new PlayingCard(s, r))
                    .LogQuery("Starting Deck")
                    .ToArray();
```

<span data-ttu-id="30eda-269">Скомпилируйте и запустите программу.</span><span class="sxs-lookup"><span data-stu-id="30eda-269">Compile and run again.</span></span> <span data-ttu-id="30eda-270">Выходные данные стали несколько чище, а код намного лучше читается и хорошо поддается расширению.</span><span class="sxs-lookup"><span data-stu-id="30eda-270">The output is a little cleaner, and the code is a bit more clear and can be extended more easily.</span></span>

## <a name="conclusion"></a><span data-ttu-id="30eda-271">Заключение</span><span class="sxs-lookup"><span data-stu-id="30eda-271">Conclusion</span></span>

<span data-ttu-id="30eda-272">В этом примере мы продемонстрировали вам некоторые методы, используемые в запросах LINQ. Также вы узнали, как создать собственные методы и легко использовать их в коде с поддержкой LINQ.</span><span class="sxs-lookup"><span data-stu-id="30eda-272">This sample showed you some of the methods used in LINQ, how to create your own methods that will be easily used with LINQ enabled code.</span></span> <span data-ttu-id="30eda-273">Мы наглядно продемонстрировали различия между упреждающим и отложенным вычислением, а также потенциальное влияние этого выбора на производительность.</span><span class="sxs-lookup"><span data-stu-id="30eda-273">It also showed you the differences between lazy and eager evaluation, and the effect that decision can have on performance.</span></span>

<span data-ttu-id="30eda-274">И теперь вы знаете чуть больше о приемах иллюзионистов.</span><span class="sxs-lookup"><span data-stu-id="30eda-274">You learned a bit about one magician's technique.</span></span> <span data-ttu-id="30eda-275">Они используют тасовку по методу фаро, потому что она позволяет хорошо контролировать положение каждой карты в колоде.</span><span class="sxs-lookup"><span data-stu-id="30eda-275">Magicians use the faro shuffle because they can control where every card moves in the deck.</span></span> <span data-ttu-id="30eda-276">В некоторых фокусах иллюзионист предлагает зрителю положить карту на верх колоды и спокойно тасует колоду несколько раз, при этом точно зная, где эта карта окажется.</span><span class="sxs-lookup"><span data-stu-id="30eda-276">In some tricks, the magician has an audience member place a card on top of the deck, and shuffles a few times, knowing where that card goes.</span></span> <span data-ttu-id="30eda-277">Для других фокусов может понадобиться колода, сложенная в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="30eda-277">Other illusions require the deck set a certain way.</span></span> <span data-ttu-id="30eda-278">Тогда иллюзионист заранее готовит колоду перед выполнением фокуса.</span><span class="sxs-lookup"><span data-stu-id="30eda-278">A magician will set the deck prior to performing the trick.</span></span> <span data-ttu-id="30eda-279">Затем он выполняет 5 внутренних тасовок фаро.</span><span class="sxs-lookup"><span data-stu-id="30eda-279">Then she will shuffle the deck 5 times using an outer shuffle.</span></span> <span data-ttu-id="30eda-280">После этого на сцене он демонстрирует зрителям колоду, порядок карт в которой выглядит случайным, выполняет еще 3 внешних тасовки фаро, и колода принимает необходимое состояние.</span><span class="sxs-lookup"><span data-stu-id="30eda-280">On stage, she can show what looks like a random deck, shuffle it 3 more times, and have the deck set exactly how she wants.</span></span>
