---
title: Встроенный язык запросов LINQ
description: Сведения о том, как LINQ предоставляет возможности выполнения запросов на уровне языка и API в C# и VB для написания выразительного и декларативного кода.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: c00939e1-59e3-4e61-8fe9-08ad6b3f1295
ms.openlocfilehash: 31b0a7b9e11d46e6453d9fcad87e7beadba9a1e3
ms.sourcegitcommit: 6c480773ae896f45af4671fb3e26611a50e4dd81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2018
ms.locfileid: "35251094"
---
# <a name="linq-language-integrated-query"></a><span data-ttu-id="f9c3b-103">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="f9c3b-103">LINQ (Language Integrated Query)</span></span>

## <a name="what-is-it"></a><span data-ttu-id="f9c3b-104">Что это такое?</span><span class="sxs-lookup"><span data-stu-id="f9c3b-104">What is it?</span></span>

<span data-ttu-id="f9c3b-105">LINQ предоставляет возможности выполнения запросов на уровне языка и API [функции высшего порядка](https://en.wikipedia.org/wiki/Higher-order_function) в C# и VB для написания выразительного и декларативного кода.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-105">LINQ provides language-level querying capabilities and a [higher-order function](https://en.wikipedia.org/wiki/Higher-order_function) API to C# and VB as a way to write expressive, declarative code.</span></span>

<span data-ttu-id="f9c3b-106">Синтаксис запросов на основе языка</span><span class="sxs-lookup"><span data-stu-id="f9c3b-106">Language-level query syntax:</span></span>

```csharp
var linqExperts = from p in programmers
                  where p.IsNewToLINQ
                  select new LINQExpert(p);
```

<span data-ttu-id="f9c3b-107">Пример использования API `IEnumerable<T>`</span><span class="sxs-lookup"><span data-stu-id="f9c3b-107">Same example using the `IEnumerable<T>` API:</span></span>

```csharp
var linqExperts = programmers.Where(p => p.IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

## <a name="linq-is-expressive"></a><span data-ttu-id="f9c3b-108">LINQ является выразительной методикой</span><span class="sxs-lookup"><span data-stu-id="f9c3b-108">LINQ is Expressive</span></span>

<span data-ttu-id="f9c3b-109">Предположим, что имеющийся список домашних животных нужно преобразовать в словарь, чтобы находить питомца напрямую по его значению `RFID`.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-109">Imagine you have a list of pets, but want to convert it into a dictionary where you can access a pet directly by its `RFID` value.</span></span>

<span data-ttu-id="f9c3b-110">Традиционный императивный код</span><span class="sxs-lookup"><span data-stu-id="f9c3b-110">Traditional imperative code:</span></span>

```csharp
var petLookup = new Dictionary<int, Pet>();

foreach (var pet in pets)
{
    petLookup.Add(pet.RFID, pet);
}
```

<span data-ttu-id="f9c3b-111">Цель написания кода заключается не только в создании нового `Dictionary<int, Pet>` и его добавления с помощью цикла, но также в преобразовании существующего списка в словарь!</span><span class="sxs-lookup"><span data-stu-id="f9c3b-111">The intention behind the code is not to create a new `Dictionary<int, Pet>` and add to it via a loop, it is to convert an existing list into a dictionary!</span></span> <span data-ttu-id="f9c3b-112">LINQ позволяет выполнить эту задачу, тогда как принудительный код — нет.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-112">LINQ preserves the intention whereas the imperative code does not.</span></span>

<span data-ttu-id="f9c3b-113">Эквивалентное выражение LINQ:</span><span class="sxs-lookup"><span data-stu-id="f9c3b-113">Equivalent LINQ expression:</span></span>

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

<span data-ttu-id="f9c3b-114">Код, использующий LINQ, является весьма удобным, так как он создает равные условия как для достижения цели, как и для написания кода, сохраняя при этом логику.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-114">The code using LINQ is valuable because it evens the playing field between intent and code when reasoning as a programmer.</span></span> <span data-ttu-id="f9c3b-115">Еще одним преимуществом является краткость кода.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-115">Another bonus is code brevity.</span></span> <span data-ttu-id="f9c3b-116">Большие части базы кода можно сократить на треть, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-116">Imagine reducing large portions of a codebase by 1/3 as done above.</span></span> <span data-ttu-id="f9c3b-117">Это замечательно!</span><span class="sxs-lookup"><span data-stu-id="f9c3b-117">Pretty sweet deal, right?</span></span>

## <a name="linq-providers-simplify-data-access"></a><span data-ttu-id="f9c3b-118">Поставщики LINQ упрощают доступ к данным</span><span class="sxs-lookup"><span data-stu-id="f9c3b-118">LINQ Providers Simplify Data Access</span></span>

<span data-ttu-id="f9c3b-119">Использование значительной части существующего ПО связано с обработкой данных из определенного источника (баз данных, JSON, XML и т. д.).</span><span class="sxs-lookup"><span data-stu-id="f9c3b-119">For a significant chunk of software out in the wild, everything revolves around dealing with data from some source (Databases, JSON, XML, etc).</span></span> <span data-ttu-id="f9c3b-120">Часто для этого требуется изучать новый API по каждому источнику данных, что может оказаться раздражающим фактором.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-120">Often this involves learning a new API for each data source, which can be annoying.</span></span> <span data-ttu-id="f9c3b-121">LINQ упрощает эту задачу путем абстрагирования общих элементов доступа к данным в синтаксис запросов, который имеет один и тот же вид независимо от выбираемого источника данных.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-121">LINQ simplifies this by abstracting common elements of data access into a query syntax which looks the same no matter which data source you pick.</span></span>

<span data-ttu-id="f9c3b-122">Представьте ситуацию: необходимо найти все элементы XML с конкретным значением атрибута.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-122">Consider the following: finding all XML elements with a specific attribute value.</span></span>

```csharp
public static IEnumerable<XElement> FindAllElementsWithAttribute(XElement documentRoot, string elementName,
                                           string attributeName, string value)
{
    return from el in documentRoot.Elements(elementName)
           where (string)el.Element(attributeName) == value
           select el;
}
```

<span data-ttu-id="f9c3b-123">Написать код для просмотра XML-документа вручную будет намного сложнее.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-123">Writing code to manually traverse the XML document to perform this task would be far more challenging.</span></span>

<span data-ttu-id="f9c3b-124">Поставщики LINQ можно использовать для реализации целого ряда задач, не ограничиваясь только взаимодействием с XML.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-124">Interacting with XML isn’t the only thing you can do with LINQ Providers.</span></span> <span data-ttu-id="f9c3b-125">[LINQ to SQL](../../docs/framework/data/adonet/sql/linq/index.md) является довольно минималистичным инструментом объектно-реляционного сопоставления (ORM) для базы данных сервера MSSQL.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-125">[Linq to SQL](../../docs/framework/data/adonet/sql/linq/index.md) is a fairly bare-bones Object-Relational Mapper (ORM) for an MSSQL Server Database.</span></span> <span data-ttu-id="f9c3b-126">Библиотека [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) предоставляет эффективные возможности просмотра документов JSON с помощью LINQ.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-126">The [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) library provides efficient JSON Document traversal via LINQ.</span></span> <span data-ttu-id="f9c3b-127">Кроме того, если библиотека с необходимыми вам функциями отсутствует, можно [написать собственный поставщик LINQ](https://msdn.microsoft.com/library/Bb546158.aspx)!</span><span class="sxs-lookup"><span data-stu-id="f9c3b-127">Furthermore, if there isn’t a library which does what you need, you can also [write your own LINQ Provider](https://msdn.microsoft.com/library/Bb546158.aspx)!</span></span>

## <a name="why-use-the-query-syntax"></a><span data-ttu-id="f9c3b-128">Зачем нужно использовать синтаксис запроса?</span><span class="sxs-lookup"><span data-stu-id="f9c3b-128">Why Use the Query Syntax?</span></span>

<span data-ttu-id="f9c3b-129">Этот вопрос возникает довольно часто.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-129">This is a question which often comes up.</span></span> <span data-ttu-id="f9c3b-130">В конце концов, этот вариант</span><span class="sxs-lookup"><span data-stu-id="f9c3b-130">After all, this,</span></span>

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

<span data-ttu-id="f9c3b-131">гораздо более лаконичен, чем этот:</span><span class="sxs-lookup"><span data-stu-id="f9c3b-131">is a lot more concise than this:</span></span>

```csharp
var filteredItems = from item in myItems
                    where item.Foo
                    select item;
```

<span data-ttu-id="f9c3b-132">Может быть, синтаксис API просто является самым кратким способом формирования синтаксиса запроса?</span><span class="sxs-lookup"><span data-stu-id="f9c3b-132">Isn’t the API syntax just a more concise way to do the query syntax?</span></span>

<span data-ttu-id="f9c3b-133">Номер</span><span class="sxs-lookup"><span data-stu-id="f9c3b-133">No.</span></span> <span data-ttu-id="f9c3b-134">Синтаксис запроса позволяет использовать предложение **let**, которое дает возможность ввести и привязать переменную в области выражения и применять ее в последующих частях выражения.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-134">The query syntax allows for the use the **let** clause, which allows you to introduce and bind a variable within the scope of the expression, using it in subsequent pieces of the expression.</span></span> <span data-ttu-id="f9c3b-135">Можно воспроизвести тот же код только с помощью синтаксиса API, но, скорее всего, этот код будет трудночитаемым.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-135">Reproducing the same code with only the API syntax can be done, but will most likely lead to code which is hard to read.</span></span>

<span data-ttu-id="f9c3b-136">Поэтому возникает вопрос о том, **можно ли просто использовать синтаксис запросов?**</span><span class="sxs-lookup"><span data-stu-id="f9c3b-136">So this begs the question, **should you just use the query syntax?**</span></span>

<span data-ttu-id="f9c3b-137">Ответом будет **Да**, если...</span><span class="sxs-lookup"><span data-stu-id="f9c3b-137">The answer to this question is **yes** if...</span></span>

*   <span data-ttu-id="f9c3b-138">в существующей базе кода уже используется синтаксис запроса;</span><span class="sxs-lookup"><span data-stu-id="f9c3b-138">Your existing codebase already uses the query syntax</span></span>
*   <span data-ttu-id="f9c3b-139">необходимо ограничить переменные в запросах из-за сложности;</span><span class="sxs-lookup"><span data-stu-id="f9c3b-139">You need to scope variables within your queries due to complexity</span></span>
*   <span data-ttu-id="f9c3b-140">вы предпочитаете синтаксис запросов, который не отвлекает внимание от базы кода.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-140">You prefer the query syntax and it won’t distract from your codebase</span></span>

<span data-ttu-id="f9c3b-141">Ответом будет **Нет**, если...</span><span class="sxs-lookup"><span data-stu-id="f9c3b-141">The answer to this question is **no** if...</span></span>

*   <span data-ttu-id="f9c3b-142">в существующей базе кода уже используется синтаксис API;</span><span class="sxs-lookup"><span data-stu-id="f9c3b-142">Your existing codebase already uses the API syntax</span></span>
*   <span data-ttu-id="f9c3b-143">нет необходимости ограничивать переменные в запросах;</span><span class="sxs-lookup"><span data-stu-id="f9c3b-143">You have no need to scope variables within your queries</span></span>
*   <span data-ttu-id="f9c3b-144">вы предпочитаете использовать синтаксис API, который не отвлекает внимание от базы кода.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-144">You prefer the API syntax and it won’t distract from your codebase</span></span>

## <a name="essential-samples"></a><span data-ttu-id="f9c3b-145">Основные примеры</span><span class="sxs-lookup"><span data-stu-id="f9c3b-145">Essential Samples</span></span>

<span data-ttu-id="f9c3b-146">Полный список примеров LINQ см. на странице [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b) (101 пример LINQ).</span><span class="sxs-lookup"><span data-stu-id="f9c3b-146">For a truly comprehensive list of LINQ samples, visit [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b).</span></span>

<span data-ttu-id="f9c3b-147">Далее приводится краткая демонстрация некоторых важных частей LINQ.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-147">The following is a quick demonstration of some of the essential pieces of LINQ.</span></span> <span data-ttu-id="f9c3b-148">Она не является исчерпывающий, так как LINQ предоставляет гораздо больше возможностей, чем показано здесь.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-148">This is in no way comprehensive, as LINQ provides significantly more functionality than what is showcased here.</span></span>

*   <span data-ttu-id="f9c3b-149">Совершенно необходимые компоненты — `Where`, `Select` и `Aggregate`:</span><span class="sxs-lookup"><span data-stu-id="f9c3b-149">The bread and butter - `Where`, `Select`, and `Aggregate`:</span></span>

```csharp
// Filtering a list
var germanShepards = dogs.Where(dog => dog.Breed == DogBreed.GermanShepard);

// Using the query syntax
var queryGermanShepards = from dog in dogs
                          where dog.Breed == DogBreed.GermanShepard
                          select dog;

// Mapping a list from type A to type B
var cats = dogs.Select(dog => dog.TurnIntoACat());

// Using the query syntax
var queryCats = from dog in dogs
                select dog.TurnIntoACat();

// Summing the lengths of a set of strings
int seed = 0;
int sumOfStrings = strings.Aggregate(seed, (s1, s2) => s1.Length + s2.Length);
```

*   <span data-ttu-id="f9c3b-150">Спрямление списка списков:</span><span class="sxs-lookup"><span data-stu-id="f9c3b-150">Flattening a list of lists:</span></span>

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

*   <span data-ttu-id="f9c3b-151">Объединение двух наборов (с пользовательским блоком сравнения):</span><span class="sxs-lookup"><span data-stu-id="f9c3b-151">Union between two sets (with custom comparator):</span></span>

```csharp
public class DogHairLengthComparer : IEqualityComparer<Dog>
{
    public bool Equals(Dog a, Dog b)
    {
        if (a == null && b == null)
        {
            return true;
        }
        else if ((a == null && b != null) ||
                 (a != null && b == null))
        {
            return false;
        }
        else
        {
            return a.HairLengthType == b.HairLengthType;
        }
    }

    public int GetHashCode(Dog d)
    {
        // default hashcode is enough here, as these are simple objects.
        return b.GetHashCode();
    }
}

...

// Gets all the short-haired dogs between two different kennels
var allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, new DogHairLengthComparer());
```

*   <span data-ttu-id="f9c3b-152">Пересечение двух наборов:</span><span class="sxs-lookup"><span data-stu-id="f9c3b-152">Intersection between two sets:</span></span>

```csharp
// Gets the volunteers who spend share time with two humane societies.
var volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     new VolunteerTimeComparer());
```

*   <span data-ttu-id="f9c3b-153">Упорядочение:</span><span class="sxs-lookup"><span data-stu-id="f9c3b-153">Ordering:</span></span>

```csharp
// Get driving directions, ordering by if it's toll-free before estimated driving time.
var results = DirectionsProcessor.GetDirections(start, end)
              .OrderBy(direction => direction.HasNoTolls)
              .ThenBy(direction => direction.EstimatedTime);
```

*   <span data-ttu-id="f9c3b-154">И, наконец, расширенный пример: определение равенства значений свойств двух экземпляров одного типа (взят и изменен на основе [этой записи на сайте StackOverflow](http://stackoverflow.com/a/844855)):</span><span class="sxs-lookup"><span data-stu-id="f9c3b-154">Finally, a more advanced sample: determining if the values of the properties of two instances of the same type are equal (Borrowed and modified from [this StackOverflow post](http://stackoverflow.com/a/844855)):</span></span>

```csharp
public static bool PublicInstancePropertiesEqual<T>(this T self, T to, params string[] ignore) where T : class
{
    if (self != null && to != null)
    {
        var type = typeof(T);
        var ignoreList = new List<string>(ignore);

        // Selects the properties which have unequal values into a sequence of those properties.
        var unequalProperties = from pi in type.GetProperties(BindingFlags.Public | BindingFlags.Instance)
                                where !ignoreList.Contains(pi.Name)
                                let selfValue = type.GetProperty(pi.Name).GetValue(self, null)
                                let toValue = type.GetProperty(pi.Name).GetValue(to, null)
                                where selfValue != toValue && (selfValue == null || !selfValue.Equals(toValue))
                                select new { Prop = pi.Name, selfValue, toValue };
        return !unequalProperties.Any();
    }

    return self == to;
}
```

## <a name="plinq"></a><span data-ttu-id="f9c3b-155">PLINQ</span><span class="sxs-lookup"><span data-stu-id="f9c3b-155">PLINQ</span></span>

<span data-ttu-id="f9c3b-156">PLINQ или параллельный LINQ — это механизм параллельного выполнения выражений LINQ.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-156">PLINQ, or Parallel LINQ, is a parallel execution engine for LINQ expressions.</span></span> <span data-ttu-id="f9c3b-157">Другими словами, регулярные выражения LINQ можно просто распараллелить между любым количеством потоков.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-157">In other words, a regular LINQ expressions can be trivially parallelized across any number of threads.</span></span> <span data-ttu-id="f9c3b-158">Это выполняется путем вызова `AsParallel()`, предшествующего выражению.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-158">This is accomplished via a call to `AsParallel()` preceding the expression.</span></span>

<span data-ttu-id="f9c3b-159">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-159">Consider the following:</span></span>

```csharp
public static string GetAllFacebookUserLikesMessage(IEnumerable<FacebookUser> facebookUsers)
{
    var seed = default(UInt64);

    Func<UInt64, UInt64, UInt64> threadAccumulator = (t1, t2) => t1 + t2;
    Func<UInt64, UInt64, UInt64> threadResultAccumulator = (t1, t2) => t1 + t2;
    Func<Uint64, string> resultSelector = total => $"Facebook has {total} likes!";

    return facebookUsers.AsParallel()
                        .Aggregate(seed, threadAccumulator, threadResultAccumulator, resultSelector);
}
```

<span data-ttu-id="f9c3b-160">Этот код будет секционировать `facebookUsers` по потокам системы, суммировать общие лайки в каждом параллельном потоке, суммировать результаты, вычисленные каждым потоком, и выводить результат в виде понятной строки.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-160">This code will partition `facebookUsers` across system threads as necessary, sum up the total likes on each thread in parallel, sum the results computed by each thread, and project that result into a nice string.</span></span>

<span data-ttu-id="f9c3b-161">В виде схемы:</span><span class="sxs-lookup"><span data-stu-id="f9c3b-161">In diagram form:</span></span>

![Схема PLINQ](./media/using-linq/plinq-diagram.png)

<span data-ttu-id="f9c3b-163">Параллелизуемые задания, использующие ресурсы ЦП, которые можно легко выразить через LINQ (другими словами, чистые функции без побочных эффектов) являются отличным кандидатом для PLINQ.</span><span class="sxs-lookup"><span data-stu-id="f9c3b-163">Parallelizable CPU-bound jobs which can be easily expressed via LINQ (in other words, are pure functions and have no side effects) are a great candidate for PLINQ.</span></span> <span data-ttu-id="f9c3b-164">Для работы с заданиями, которые _имеют_ побочный эффект, рекомендуется рассмотреть возможность использования [библиотеки параллельных задач](./parallel-programming/task-parallel-library-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="f9c3b-164">For jobs which _do_ have a side effect, consider using the [Task Parallel Library](./parallel-programming/task-parallel-library-tpl.md).</span></span>

## <a name="further-resources"></a><span data-ttu-id="f9c3b-165">Дополнительные ресурсы:</span><span class="sxs-lookup"><span data-stu-id="f9c3b-165">Further Resources:</span></span>

*   [<span data-ttu-id="f9c3b-166">101 пример по LINQ</span><span class="sxs-lookup"><span data-stu-id="f9c3b-166">101 LINQ Samples</span></span>](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b)
*   <span data-ttu-id="f9c3b-167">[LINQPad](https://www.linqpad.net/) — среда и механизм запросов к базе данных для C#/F#/VB</span><span class="sxs-lookup"><span data-stu-id="f9c3b-167">[Linqpad](https://www.linqpad.net/), a playground environment and Database querying engine for C#/F#/VB</span></span>
*   <span data-ttu-id="f9c3b-168">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/) — электронная книга с информацией по реализации LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="f9c3b-168">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), an e-book for learning how LINQ-to-objects is implemented</span></span>
