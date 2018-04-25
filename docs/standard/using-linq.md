---
title: Встроенный язык запросов LINQ
description: Сведения о том, как LINQ предоставляет возможности выполнения запросов на уровне языка и API в C# и VB для написания выразительного и декларативного кода.
keywords: .NET, .NET Core
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c00939e1-59e3-4e61-8fe9-08ad6b3f1295
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5ce6819abee90ceccc52a79f8bda794f2fd345fb
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="linq-language-integrated-query"></a>Встроенный язык запросов LINQ

## <a name="what-is-it"></a>Что это такое?

LINQ предоставляет возможности выполнения запросов на уровне языка и API [функции высшего порядка](https://en.wikipedia.org/wiki/Higher-order_function) в C# и VB для написания выразительного и декларативного кода.

Синтаксис запросов на основе языка

```csharp
var linqExperts = from p in programmers
                  where p.IsNewToLINQ
                  select new LINQExpert(p);
```

Пример использования API `IEnumerable<T>`

```csharp
var linqExperts = programmers.Where(p => IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

## <a name="linq-is-expressive"></a>LINQ является выразительной методикой

Предположим, что имеющийся список домашних животных нужно преобразовать в словарь, чтобы находить питомца напрямую по его значению `RFID`.

Традиционный императивный код

```csharp
var petLookup = new Dictionary<int, Pet>();

foreach (var pet in pets)
{
    petLookup.Add(pet.RFID, pet);
}
```

Цель написания кода заключается не только в создании нового `Dictionary<int, Pet>` и его добавления с помощью цикла, но также в преобразовании существующего списка в словарь! LINQ позволяет выполнить эту задачу, тогда как принудительный код — нет.

Эквивалентное выражение LINQ:

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

Код, использующий LINQ, является весьма удобным, так как он создает равные условия как для достижения цели, как и для написания кода, сохраняя при этом логику. Еще одним преимуществом является краткость кода. Большие части базы кода можно сократить на треть, как показано выше. Это замечательно!

## <a name="linq-providers-simplify-data-access"></a>Поставщики LINQ упрощают доступ к данным

Использование значительной части существующего ПО связано с обработкой данных из определенного источника (баз данных, JSON, XML и т. д.). Часто для этого требуется изучать новый API по каждому источнику данных, что может оказаться раздражающим фактором. LINQ упрощает эту задачу путем абстрагирования общих элементов доступа к данным в синтаксис запросов, который имеет один и тот же вид независимо от выбираемого источника данных.

Представьте ситуацию: необходимо найти все элементы XML с конкретным значением атрибута.

```csharp
public static IEnumerable<XElement> FindAllElementsWithAttribute(XElement documentRoot, string elementName,
                                           string attributeName, string value)
{
    return from el in documentRoot.Elements(elementName)
           where (string)el.Element(attributeName) == value
           select el;
}
```

Написать код для просмотра XML-документа вручную будет намного сложнее.

Поставщики LINQ можно использовать для реализации целого ряда задач, не ограничиваясь только взаимодействием с XML. [LINQ to SQL](../../docs/framework/data/adonet/sql/linq/index.md) является довольно минималистичным инструментом объектно-реляционного сопоставления (ORM) для базы данных сервера MSSQL. Библиотека [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) предоставляет эффективные возможности просмотра документов JSON с помощью LINQ. Кроме того, если библиотека с необходимыми вам функциями отсутствует, можно [написать собственный поставщик LINQ](https://msdn.microsoft.com/library/Bb546158.aspx)!

## <a name="why-use-the-query-syntax"></a>Зачем нужно использовать синтаксис запроса?

Этот вопрос возникает довольно часто. В конце концов, этот вариант

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

гораздо более лаконичен, чем этот:

```csharp
var filteredItems = from item in myItems
                    where item.Foo
                    select item;
```

Может быть, синтаксис API просто является самым кратким способом формирования синтаксиса запроса?

Номер Синтаксис запроса позволяет использовать предложение **let**, которое дает возможность ввести и привязать переменную в области выражения и применять ее в последующих частях выражения. Можно воспроизвести тот же код только с помощью синтаксиса API, но, скорее всего, этот код будет трудночитаемым.

Поэтому возникает вопрос о том, **можно ли просто использовать синтаксис запросов?**

Ответом будет **Да**, если...

*   в существующей базе кода уже используется синтаксис запроса;
*   необходимо ограничить переменные в запросах из-за сложности;
*   вы предпочитаете синтаксис запросов, который не отвлекает внимание от базы кода.

Ответом будет **Нет**, если...

*   в существующей базе кода уже используется синтаксис API;
*   нет необходимости ограничивать переменные в запросах;
*   вы предпочитаете использовать синтаксис API, который не отвлекает внимание от базы кода.

## <a name="essential-samples"></a>Основные примеры

Полный список примеров LINQ см. на странице [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b) (101 пример LINQ).

Далее приводится краткая демонстрация некоторых важных частей LINQ. Она не является исчерпывающий, так как LINQ предоставляет гораздо больше возможностей, чем показано здесь.

*   Совершенно необходимые компоненты — `Where`, `Select` и `Aggregate`:

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

*   Спрямление списка списков:

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

*   Объединение двух наборов (с пользовательским блоком сравнения):

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

*   Пересечение двух наборов:

```csharp
// Gets the volunteers who spend share time with two humane societies.
var volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     new VolunteerTimeComparer());
```

*   Упорядочение:

```csharp
// Get driving directions, ordering by if it's toll-free before estimated driving time.
var results = DirectionsProcessor.GetDirections(start, end)
              .OrderBy(direction => direction.HasNoTolls)
              .ThenBy(direction => direction.EstimatedTime);
```

*   И, наконец, расширенный пример: определение равенства значений свойств двух экземпляров одного типа (взят и изменен на основе [этой записи на сайте StackOverflow](http://stackoverflow.com/a/844855)):

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

## <a name="plinq"></a>PLINQ

PLINQ или параллельный LINQ — это механизм параллельного выполнения выражений LINQ. Другими словами, регулярные выражения LINQ можно просто распараллелить между любым количеством потоков. Это выполняется путем вызова `AsParallel()`, предшествующего выражению.

Рассмотрим следующий пример.

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

Этот код будет секционировать `facebookUsers` по потокам системы, суммировать общие лайки в каждом параллельном потоке, суммировать результаты, вычисленные каждым потоком, и выводить результат в виде понятной строки.

В виде схемы:

![Схема PLINQ](./media/using-linq/plinq-diagram.png)

Параллелизуемые задания, использующие ресурсы ЦП, которые можно легко выразить через LINQ (другими словами, чистые функции без побочных эффектов) являются отличным кандидатом для PLINQ. Для работы с заданиями, которые _имеют_ побочный эффект, рекомендуется рассмотреть возможность использования [библиотеки параллельных задач](./parallel-programming/task-parallel-library-tpl.md).

## <a name="further-resources"></a>Дополнительные ресурсы:

*   [101 пример по LINQ](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b)
*   [LINQPad](https://www.linqpad.net/) — среда и механизм запросов к базе данных для C#/F#/VB
*   [EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/) — электронная книга с информацией по реализации LINQ to Objects
