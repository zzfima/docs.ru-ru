---
title: Встроенный язык запросов LINQ
description: Узнайте о том, как LINQ позволяет выполнять запросы на уровне и API в C# и Visual Basic для написания выразительного декларативного кода.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
dev_langs:
- csharp
- vb
ms.technology: dotnet-standard
ms.assetid: c00939e1-59e3-4e61-8fe9-08ad6b3f1295
ms.openlocfilehash: eafd8f78c3d8de1ba064021111f869571d5a570f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160330"
---
# <a name="linq-language-integrated-query"></a><span data-ttu-id="f7c84-103">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="f7c84-103">LINQ (Language Integrated Query)</span></span>

## <a name="what-is-it"></a><span data-ttu-id="f7c84-104">Что это такое?</span><span class="sxs-lookup"><span data-stu-id="f7c84-104">What is it?</span></span>

<span data-ttu-id="f7c84-105">LINQ предоставляет возможности выполнения запросов на уровне языка и API [функции высшего порядка](https://en.wikipedia.org/wiki/Higher-order_function) в C# и Visual Basic для написания выразительного декларативного кода.</span><span class="sxs-lookup"><span data-stu-id="f7c84-105">LINQ provides language-level querying capabilities and a [higher-order function](https://en.wikipedia.org/wiki/Higher-order_function) API to C# and Visual Basic as a way to write expressive, declarative code.</span></span>

<span data-ttu-id="f7c84-106">Синтаксис запросов на основе языка</span><span class="sxs-lookup"><span data-stu-id="f7c84-106">Language-level query syntax:</span></span>

```csharp
var linqExperts = from p in programmers
                  where p.IsNewToLINQ
                  select new LINQExpert(p);
```

```vb
Dim linqExperts = From p in programmers
                  Where p.IsNewToLINQ
                  Select New LINQExpert(p)
```

<span data-ttu-id="f7c84-107">Пример использования API `IEnumerable<T>`</span><span class="sxs-lookup"><span data-stu-id="f7c84-107">Same example using the `IEnumerable<T>` API:</span></span>

```csharp
var linqExperts = programmers.Where(p => p.IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

```vb
Dim linqExperts = programmers.Where(Function(p) p.IsNewToLINQ).
                             Select(Function(p) New LINQExpert(p))
```

## <a name="linq-is-expressive"></a><span data-ttu-id="f7c84-108">LINQ является выразительной методикой</span><span class="sxs-lookup"><span data-stu-id="f7c84-108">LINQ is Expressive</span></span>

<span data-ttu-id="f7c84-109">Предположим, что имеющийся список домашних животных нужно преобразовать в словарь, чтобы находить питомца напрямую по его значению `RFID`.</span><span class="sxs-lookup"><span data-stu-id="f7c84-109">Imagine you have a list of pets, but want to convert it into a dictionary where you can access a pet directly by its `RFID` value.</span></span>

<span data-ttu-id="f7c84-110">Традиционный императивный код</span><span class="sxs-lookup"><span data-stu-id="f7c84-110">Traditional imperative code:</span></span>

```csharp
var petLookup = new Dictionary<int, Pet>();

foreach (var pet in pets)
{
    petLookup.Add(pet.RFID, pet);
}
```

```vb
Dim petLookup = New Dictionary(Of Integer, Pet)()

For Each pet in pets
    petLookup.Add(pet.RFID, pet)
Next
```

<span data-ttu-id="f7c84-111">Цель написания кода заключается не только в создании нового `Dictionary<int, Pet>` и его добавления с помощью цикла, но также в преобразовании существующего списка в словарь!</span><span class="sxs-lookup"><span data-stu-id="f7c84-111">The intention behind the code is not to create a new `Dictionary<int, Pet>` and add to it via a loop, it is to convert an existing list into a dictionary!</span></span> <span data-ttu-id="f7c84-112">LINQ позволяет выполнить эту задачу, тогда как принудительный код — нет.</span><span class="sxs-lookup"><span data-stu-id="f7c84-112">LINQ preserves the intention whereas the imperative code does not.</span></span>

<span data-ttu-id="f7c84-113">Эквивалентное выражение LINQ:</span><span class="sxs-lookup"><span data-stu-id="f7c84-113">Equivalent LINQ expression:</span></span>

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

```vb
Dim petLookup = pets.ToDictionary(Function(pet) pet.RFID)
```

<span data-ttu-id="f7c84-114">Код, использующий LINQ, является весьма удобным, так как он создает равные условия как для достижения цели, как и для написания кода, сохраняя при этом логику.</span><span class="sxs-lookup"><span data-stu-id="f7c84-114">The code using LINQ is valuable because it evens the playing field between intent and code when reasoning as a programmer.</span></span> <span data-ttu-id="f7c84-115">Еще одним преимуществом является краткость кода.</span><span class="sxs-lookup"><span data-stu-id="f7c84-115">Another bonus is code brevity.</span></span> <span data-ttu-id="f7c84-116">Большие части базы кода можно сократить на треть, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="f7c84-116">Imagine reducing large portions of a codebase by 1/3 as done above.</span></span> <span data-ttu-id="f7c84-117">Это замечательно!</span><span class="sxs-lookup"><span data-stu-id="f7c84-117">Pretty sweet deal, right?</span></span>

## <a name="linq-providers-simplify-data-access"></a><span data-ttu-id="f7c84-118">Поставщики LINQ упрощают доступ к данным</span><span class="sxs-lookup"><span data-stu-id="f7c84-118">LINQ Providers Simplify Data Access</span></span>

<span data-ttu-id="f7c84-119">Использование значительной части существующего ПО связано с обработкой данных из определенного источника (баз данных, JSON, XML и т. д.).</span><span class="sxs-lookup"><span data-stu-id="f7c84-119">For a significant chunk of software out in the wild, everything revolves around dealing with data from some source (Databases, JSON, XML, etc).</span></span> <span data-ttu-id="f7c84-120">Часто для этого требуется изучать новый API по каждому источнику данных, что может оказаться раздражающим фактором.</span><span class="sxs-lookup"><span data-stu-id="f7c84-120">Often this involves learning a new API for each data source, which can be annoying.</span></span> <span data-ttu-id="f7c84-121">LINQ упрощает эту задачу путем абстрагирования общих элементов доступа к данным в синтаксис запросов, который имеет один и тот же вид независимо от выбираемого источника данных.</span><span class="sxs-lookup"><span data-stu-id="f7c84-121">LINQ simplifies this by abstracting common elements of data access into a query syntax which looks the same no matter which data source you pick.</span></span>

<span data-ttu-id="f7c84-122">Представьте ситуацию: необходимо найти все элементы XML с конкретным значением атрибута.</span><span class="sxs-lookup"><span data-stu-id="f7c84-122">Consider the following: finding all XML elements with a specific attribute value.</span></span>

```csharp
public static IEnumerable<XElement> FindAllElementsWithAttribute(XElement documentRoot, string elementName,
                                           string attributeName, string value)
{
    return from el in documentRoot.Elements(elementName)
           where (string)el.Element(attributeName) == value
           select el;
}
```

```vb
Public Shared Function FindAllElementsWithAttribute(documentRoot As XElement, elementName As String,
                                           attributeName As String, value As String) As IEnumerable(Of XElement)
    Return From el In documentRoot.Elements(elementName)
           Where el.Element(attributeName).ToString() = value
           Select el
End Function

```

<span data-ttu-id="f7c84-123">Написать код для просмотра XML-документа вручную будет намного сложнее.</span><span class="sxs-lookup"><span data-stu-id="f7c84-123">Writing code to manually traverse the XML document to perform this task would be far more challenging.</span></span>

<span data-ttu-id="f7c84-124">Поставщики LINQ можно использовать для реализации целого ряда задач, не ограничиваясь только взаимодействием с XML.</span><span class="sxs-lookup"><span data-stu-id="f7c84-124">Interacting with XML isn’t the only thing you can do with LINQ Providers.</span></span> <span data-ttu-id="f7c84-125">[LINQ to SQL](../../docs/framework/data/adonet/sql/linq/index.md) является довольно минималистичным инструментом объектно-реляционного сопоставления (ORM) для базы данных сервера MSSQL.</span><span class="sxs-lookup"><span data-stu-id="f7c84-125">[Linq to SQL](../../docs/framework/data/adonet/sql/linq/index.md) is a fairly bare-bones Object-Relational Mapper (ORM) for an MSSQL Server Database.</span></span> <span data-ttu-id="f7c84-126">Библиотека [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) предоставляет эффективные возможности просмотра документов JSON с помощью LINQ.</span><span class="sxs-lookup"><span data-stu-id="f7c84-126">The [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) library provides efficient JSON Document traversal via LINQ.</span></span> <span data-ttu-id="f7c84-127">Кроме того, если библиотека с необходимыми вам функциями отсутствует, можно [написать собственный поставщик LINQ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110))!</span><span class="sxs-lookup"><span data-stu-id="f7c84-127">Furthermore, if there isn’t a library which does what you need, you can also [write your own LINQ Provider](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110))!</span></span>

## <a name="why-use-the-query-syntax"></a><span data-ttu-id="f7c84-128">Зачем нужно использовать синтаксис запроса?</span><span class="sxs-lookup"><span data-stu-id="f7c84-128">Why Use the Query Syntax?</span></span>

<span data-ttu-id="f7c84-129">Этот вопрос возникает довольно часто.</span><span class="sxs-lookup"><span data-stu-id="f7c84-129">This is a question which often comes up.</span></span> <span data-ttu-id="f7c84-130">В конце концов, этот вариант</span><span class="sxs-lookup"><span data-stu-id="f7c84-130">After all, this,</span></span>

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

```vb
Dim filteredItems = myItems.Where(Function(item) item.Foo)
```

<span data-ttu-id="f7c84-131">гораздо более лаконичен, чем этот:</span><span class="sxs-lookup"><span data-stu-id="f7c84-131">is a lot more concise than this:</span></span>

```csharp
var filteredItems = from item in myItems
                    where item.Foo
                    select item;
```

```vb
Dim filteredItems = From item In myItems
                    Where item.Foo
                    Select item
```

<span data-ttu-id="f7c84-132">Может быть, синтаксис API просто является самым кратким способом формирования синтаксиса запроса?</span><span class="sxs-lookup"><span data-stu-id="f7c84-132">Isn’t the API syntax just a more concise way to do the query syntax?</span></span>

<span data-ttu-id="f7c84-133">Нет.</span><span class="sxs-lookup"><span data-stu-id="f7c84-133">No.</span></span> <span data-ttu-id="f7c84-134">Синтаксис запроса позволяет использовать предложение **let**, которое дает возможность ввести и привязать переменную в области выражения и применять ее в последующих частях выражения.</span><span class="sxs-lookup"><span data-stu-id="f7c84-134">The query syntax allows for the use of the **let** clause, which allows you to introduce and bind a variable within the scope of the expression, using it in subsequent pieces of the expression.</span></span> <span data-ttu-id="f7c84-135">Можно воспроизвести тот же код только с помощью синтаксиса API, но, скорее всего, этот код будет трудночитаемым.</span><span class="sxs-lookup"><span data-stu-id="f7c84-135">Reproducing the same code with only the API syntax can be done, but will most likely lead to code which is hard to read.</span></span>

<span data-ttu-id="f7c84-136">Поэтому возникает вопрос о том, **можно ли просто использовать синтаксис запросов?**</span><span class="sxs-lookup"><span data-stu-id="f7c84-136">So this begs the question, **should you just use the query syntax?**</span></span>

<span data-ttu-id="f7c84-137">Ответом будет **Да**, если...</span><span class="sxs-lookup"><span data-stu-id="f7c84-137">The answer to this question is **yes** if...</span></span>

* <span data-ttu-id="f7c84-138">в существующей базе кода уже используется синтаксис запроса;</span><span class="sxs-lookup"><span data-stu-id="f7c84-138">Your existing codebase already uses the query syntax</span></span>
* <span data-ttu-id="f7c84-139">необходимо ограничить переменные в запросах из-за сложности;</span><span class="sxs-lookup"><span data-stu-id="f7c84-139">You need to scope variables within your queries due to complexity</span></span>
* <span data-ttu-id="f7c84-140">вы предпочитаете синтаксис запросов, который не отвлекает внимание от базы кода.</span><span class="sxs-lookup"><span data-stu-id="f7c84-140">You prefer the query syntax and it won’t distract from your codebase</span></span>

<span data-ttu-id="f7c84-141">Ответом будет **Нет**, если...</span><span class="sxs-lookup"><span data-stu-id="f7c84-141">The answer to this question is **no** if...</span></span>

* <span data-ttu-id="f7c84-142">в существующей базе кода уже используется синтаксис API;</span><span class="sxs-lookup"><span data-stu-id="f7c84-142">Your existing codebase already uses the API syntax</span></span>
* <span data-ttu-id="f7c84-143">нет необходимости ограничивать переменные в запросах;</span><span class="sxs-lookup"><span data-stu-id="f7c84-143">You have no need to scope variables within your queries</span></span>
* <span data-ttu-id="f7c84-144">вы предпочитаете использовать синтаксис API, который не отвлекает внимание от базы кода.</span><span class="sxs-lookup"><span data-stu-id="f7c84-144">You prefer the API syntax and it won’t distract from your codebase</span></span>

## <a name="essential-samples"></a><span data-ttu-id="f7c84-145">Основные примеры</span><span class="sxs-lookup"><span data-stu-id="f7c84-145">Essential Samples</span></span>

<span data-ttu-id="f7c84-146">Полный список примеров LINQ см. на странице [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b) (101 пример LINQ).</span><span class="sxs-lookup"><span data-stu-id="f7c84-146">For a truly comprehensive list of LINQ samples, visit [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b).</span></span>

<span data-ttu-id="f7c84-147">Далее приводится краткая демонстрация некоторых важных частей LINQ.</span><span class="sxs-lookup"><span data-stu-id="f7c84-147">The following is a quick demonstration of some of the essential pieces of LINQ.</span></span> <span data-ttu-id="f7c84-148">Она не является исчерпывающий, так как LINQ предоставляет гораздо больше возможностей, чем показано здесь.</span><span class="sxs-lookup"><span data-stu-id="f7c84-148">This is in no way comprehensive, as LINQ provides significantly more functionality than what is showcased here.</span></span>

* <span data-ttu-id="f7c84-149">Совершенно необходимые компоненты — `Where`, `Select` и `Aggregate`:</span><span class="sxs-lookup"><span data-stu-id="f7c84-149">The bread and butter - `Where`, `Select`, and `Aggregate`:</span></span>

```csharp
// Filtering a list.
var germanShepards = dogs.Where(dog => dog.Breed == DogBreed.GermanShepard);

// Using the query syntax.
var queryGermanShepards = from dog in dogs
                          where dog.Breed == DogBreed.GermanShepard
                          select dog;

// Mapping a list from type A to type B.
var cats = dogs.Select(dog => dog.TurnIntoACat());

// Using the query syntax.
var queryCats = from dog in dogs
                select dog.TurnIntoACat();

// Summing the lengths of a set of strings.
int seed = 0;
int sumOfStrings = strings.Aggregate(seed, (s1, s2) => s1.Length + s2.Length);
```

```vb
' Filtering a list.
Dim germanShepards = dogs.Where(Function(dog) dog.Breed = DogBreed.GermanShepard)

' Using the query syntax.
Dim queryGermanShepards = From dog In dogs
                          Where dog.Breed = DogBreed.GermanShepard
                          Select dog

' Mapping a list from type A to type B.
Dim cats = dogs.Select(Function(dog) dog.TurnIntoACat())

' Using the query syntax.
Dim queryCats = From dog In dogs
                Select dog.TurnIntoACat()

' Summing the lengths of a set of strings.
Dim seed As Integer = 0
Dim sumOfStrings As Integer = strings.Aggregate(seed, Function(s1, s2) s1.Length + s2.Length)
```

* <span data-ttu-id="f7c84-150">Спрямление списка списков:</span><span class="sxs-lookup"><span data-stu-id="f7c84-150">Flattening a list of lists:</span></span>

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

```vb
' Transforms the list of kennels into a list of all their dogs.
Dim allDogsFromKennels = kennels.SelectMany(Function(kennel) kennel.Dogs)
```

* <span data-ttu-id="f7c84-151">Объединение двух наборов (с пользовательским блоком сравнения):</span><span class="sxs-lookup"><span data-stu-id="f7c84-151">Union between two sets (with custom comparator):</span></span>

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
        // Default hashcode is enough here, as these are simple objects.
        return d.GetHashCode();
    }
}

...

// Gets all the short-haired dogs between two different kennels.
var allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, new DogHairLengthComparer());
```

```vb
Public Class DogHairLengthComparer
  Inherits IEqualityComparer(Of Dog)

  Public Function Equals(a As Dog,b As Dog) As Boolean
      If a Is Nothing AndAlso b Is Nothing Then
          Return True
      ElseIf (a Is Nothing AndAlso b IsNot Nothing) OrElse (a IsNot Nothing AndAlso b Is Nothing) Then
          Return False
      Else
          Return a.HairLengthType = b.HairLengthType
      End If
  End Function

  Public Function GetHashCode(d As Dog) As Integer
      ' Default hashcode is enough here, as these are simple objects.
      Return d.GetHashCode()
  End Function
End Class

...

' Gets all the short-haired dogs between two different kennels.
Dim allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, New DogHairLengthComparer())
```

* <span data-ttu-id="f7c84-152">Пересечение двух наборов:</span><span class="sxs-lookup"><span data-stu-id="f7c84-152">Intersection between two sets:</span></span>

```csharp
// Gets the volunteers who spend share time with two humane societies.
var volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     new VolunteerTimeComparer());
```

```vb
' Gets the volunteers who spend share time with two humane societies.
Dim volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     New VolunteerTimeComparer())
```

* <span data-ttu-id="f7c84-153">Упорядочение:</span><span class="sxs-lookup"><span data-stu-id="f7c84-153">Ordering:</span></span>

```csharp
// Get driving directions, ordering by if it's toll-free before estimated driving time.
var results = DirectionsProcessor.GetDirections(start, end)
              .OrderBy(direction => direction.HasNoTolls)
              .ThenBy(direction => direction.EstimatedTime);
```

```vb
' Get driving directions, ordering by if it's toll-free before estimated driving time.
Dim results = DirectionsProcessor.GetDirections(start, end).
                OrderBy(Function(direction) direction.HasNoTolls).
                ThenBy(Function(direction) direction.EstimatedTime)
```

* <span data-ttu-id="f7c84-154">И, наконец, расширенный пример: определение равенства значений свойств двух экземпляров одного типа (взят и изменен на основе [этой записи на сайте StackOverflow](https://stackoverflow.com/a/844855)):</span><span class="sxs-lookup"><span data-stu-id="f7c84-154">Finally, a more advanced sample: determining if the values of the properties of two instances of the same type are equal (Borrowed and modified from [this StackOverflow post](https://stackoverflow.com/a/844855)):</span></span>

```csharp
public static bool PublicInstancePropertiesEqual<T>(this T self, T to, params string[] ignore) where T : class
{
    if (self == null || to == null)
    {
        return self == to;
    }

    // Selects the properties which have unequal values into a sequence of those properties.
    var unequalProperties = from property in typeof(T).GetProperties(BindingFlags.Public | BindingFlags.Instance)
                            where !ignore.Contains(property.Name)
                            let selfValue = property.GetValue(self, null)
                            let toValue = property.GetValue(to, null)
                            where !Equals(selfValue, toValue)
                            select property;
    return !unequalProperties.Any();
}
```

```vb
<System.Runtime.CompilerServices.Extension()>
Public Function PublicInstancePropertiesEqual(Of T As Class)(self As T, [to] As T, ParamArray ignore As String()) As Boolean
    If self Is Nothing OrElse [to] Is Nothing Then
        Return self Is [to]
    End If

    ' Selects the properties which have unequal values into a sequence of those properties.
    Dim unequalProperties = From [property] In GetType(T).GetProperties(BindingFlags.Public Or BindingFlags.Instance)
                            Where Not ignore.Contains([property].Name)
                            Let selfValue = [property].GetValue(self, Nothing)
                            Let toValue = [property].GetValue([to], Nothing)
                            Where Not Equals(selfValue, toValue) Select [property]
    Return Not unequalProperties.Any()
End Function
```

## <a name="plinq"></a><span data-ttu-id="f7c84-155">PLINQ</span><span class="sxs-lookup"><span data-stu-id="f7c84-155">PLINQ</span></span>

<span data-ttu-id="f7c84-156">PLINQ или параллельный LINQ — это механизм параллельного выполнения выражений LINQ.</span><span class="sxs-lookup"><span data-stu-id="f7c84-156">PLINQ, or Parallel LINQ, is a parallel execution engine for LINQ expressions.</span></span> <span data-ttu-id="f7c84-157">Другими словами, обычное выражение LINQ можно легко распараллелить между любым количеством потоков.</span><span class="sxs-lookup"><span data-stu-id="f7c84-157">In other words, a regular LINQ expression can be trivially parallelized across any number of threads.</span></span> <span data-ttu-id="f7c84-158">Это выполняется путем вызова `AsParallel()`, предшествующего выражению.</span><span class="sxs-lookup"><span data-stu-id="f7c84-158">This is accomplished via a call to `AsParallel()` preceding the expression.</span></span>

<span data-ttu-id="f7c84-159">Рекомендуется учесть следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="f7c84-159">Consider the following:</span></span>

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

```vb
Public Shared GetAllFacebookUserLikesMessage(facebookUsers As IEnumerable(Of FacebookUser)) As String
{
    Dim seed As UInt64 = 0

    Dim threadAccumulator As Func(Of UInt64, UInt64, UInt64) = Function(t1, t2) t1 + t2
    Dim threadResultAccumulator As Func(Of UInt64, UInt64, UInt64) = Function(t1, t2) t1 + t2
    Dim resultSelector As Func(Of Uint64, string) = Function(total) $"Facebook has {total} likes!"

    Return facebookUsers.AsParallel().
                        Aggregate(seed, threadAccumulator, threadResultAccumulator, resultSelector)
}
```

<span data-ttu-id="f7c84-160">Этот код будет секционировать `facebookUsers` по потокам системы, суммировать общие лайки в каждом параллельном потоке, суммировать результаты, вычисленные каждым потоком, и выводить результат в виде понятной строки.</span><span class="sxs-lookup"><span data-stu-id="f7c84-160">This code will partition `facebookUsers` across system threads as necessary, sum up the total likes on each thread in parallel, sum the results computed by each thread, and project that result into a nice string.</span></span>

<span data-ttu-id="f7c84-161">В виде схемы:</span><span class="sxs-lookup"><span data-stu-id="f7c84-161">In diagram form:</span></span>

![Схема PLINQ](./media/using-linq/plinq-diagram.png)

<span data-ttu-id="f7c84-163">Параллелизуемые задания, использующие ресурсы ЦП, которые можно легко выразить через LINQ (другими словами, чистые функции без побочных эффектов) являются отличным кандидатом для PLINQ.</span><span class="sxs-lookup"><span data-stu-id="f7c84-163">Parallelizable CPU-bound jobs which can be easily expressed via LINQ (in other words, are pure functions and have no side effects) are a great candidate for PLINQ.</span></span> <span data-ttu-id="f7c84-164">Для работы с заданиями, которые _имеют_ побочный эффект, рекомендуется рассмотреть возможность использования [библиотеки параллельных задач](./parallel-programming/task-parallel-library-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="f7c84-164">For jobs which _do_ have a side effect, consider using the [Task Parallel Library](./parallel-programming/task-parallel-library-tpl.md).</span></span>

## <a name="further-resources"></a><span data-ttu-id="f7c84-165">Дополнительные ресурсы:</span><span class="sxs-lookup"><span data-stu-id="f7c84-165">Further Resources:</span></span>

* [<span data-ttu-id="f7c84-166">101 пример по LINQ</span><span class="sxs-lookup"><span data-stu-id="f7c84-166">101 LINQ Samples</span></span>](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b)
* <span data-ttu-id="f7c84-167">[LINQPad](https://www.linqpad.net/) — среда и механизм запросов к базе данных для C#/F#/Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7c84-167">[Linqpad](https://www.linqpad.net/), a playground environment and Database querying engine for C#/F#/Visual Basic</span></span>
* <span data-ttu-id="f7c84-168">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/) — электронная книга с информацией по реализации LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="f7c84-168">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), an e-book for learning how LINQ-to-objects is implemented</span></span>
