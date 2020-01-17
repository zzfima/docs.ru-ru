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
ms.openlocfilehash: 6ec86b7e728eef2cb4937662fd013d7fe951904d
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347275"
---
# <a name="linq-language-integrated-query"></a>Встроенный язык запросов LINQ

## <a name="what-is-it"></a>Что это такое?

LINQ предоставляет возможности выполнения запросов на уровне языка и API [функции высшего порядка](https://en.wikipedia.org/wiki/Higher-order_function) в C# и Visual Basic для написания выразительного декларативного кода.

Синтаксис запросов на основе языка

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

Пример использования API `IEnumerable<T>`

```csharp
var linqExperts = programmers.Where(p => p.IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

```vb
Dim linqExperts = programmers.Where(Function(p) p.IsNewToLINQ).
                             Select(Function(p) New LINQExpert(p))
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

```vb
Dim petLookup = New Dictionary(Of Integer, Pet)()

For Each pet in pets
    petLookup.Add(pet.RFID, pet)
Next
```

Цель написания кода заключается не только в создании нового `Dictionary<int, Pet>` и его добавления с помощью цикла, но также в преобразовании существующего списка в словарь! LINQ позволяет выполнить эту задачу, тогда как принудительный код — нет.

Эквивалентное выражение LINQ:

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

```vb
Dim petLookup = pets.ToDictionary(Function(pet) pet.RFID)
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

```vb
Public Shared Function FindAllElementsWithAttribute(documentRoot As XElement, elementName As String,
                                           attributeName As String, value As String) As IEnumerable(Of XElement)
    Return From el In documentRoot.Elements(elementName)
           Where el.Element(attributeName).ToString() = value
           Select el
End Function

```

Написать код для просмотра XML-документа вручную будет намного сложнее.

Поставщики LINQ можно использовать для реализации целого ряда задач, не ограничиваясь только взаимодействием с XML. [LINQ to SQL](../../docs/framework/data/adonet/sql/linq/index.md) является довольно минималистичным инструментом объектно-реляционного сопоставления (ORM) для базы данных сервера MSSQL. Библиотека [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) предоставляет эффективные возможности просмотра документов JSON с помощью LINQ. Кроме того, если библиотека с необходимыми вам функциями отсутствует, можно [написать собственный поставщик LINQ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110))!

## <a name="why-use-the-query-syntax"></a>Зачем нужно использовать синтаксис запроса?

Этот вопрос возникает довольно часто. В конце концов, этот вариант

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

```vb
Dim filteredItems = myItems.Where(Function(item) item.Foo)
```

гораздо более лаконичен, чем этот:

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

Может быть, синтаксис API просто является самым кратким способом формирования синтаксиса запроса?

Нет. Синтаксис запроса позволяет использовать предложение **let**, которое дает возможность ввести и привязать переменную в области выражения и применять ее в последующих частях выражения. Можно воспроизвести тот же код только с помощью синтаксиса API, но, скорее всего, этот код будет трудночитаемым.

Поэтому возникает вопрос о том, **можно ли просто использовать синтаксис запросов?**

Ответом будет **Да**, если...

* в существующей базе кода уже используется синтаксис запроса;
* необходимо ограничить переменные в запросах из-за сложности;
* вы предпочитаете синтаксис запросов, который не отвлекает внимание от базы кода.

Ответом будет **Нет**, если...

* в существующей базе кода уже используется синтаксис API;
* нет необходимости ограничивать переменные в запросах;
* вы предпочитаете использовать синтаксис API, который не отвлекает внимание от базы кода.

## <a name="essential-samples"></a>Основные примеры

Полный список примеров LINQ см. на странице [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b) (101 пример LINQ).

Далее приводится краткая демонстрация некоторых важных частей LINQ. Она не является исчерпывающий, так как LINQ предоставляет гораздо больше возможностей, чем показано здесь.

* Совершенно необходимые компоненты — `Where`, `Select` и `Aggregate`:

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

* Спрямление списка списков:

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

```vb
' Transforms the list of kennels into a list of all their dogs.
Dim allDogsFromKennels = kennels.SelectMany(Function(kennel) kennel.Dogs)
```

* Объединение двух наборов (с пользовательским блоком сравнения):

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

* Пересечение двух наборов:

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

* Упорядочение:

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

* И, наконец, расширенный пример: определение равенства значений свойств двух экземпляров одного типа (взят и изменен на основе [этой записи на сайте StackOverflow](https://stackoverflow.com/a/844855)):

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

## <a name="plinq"></a>PLINQ

PLINQ или параллельный LINQ — это механизм параллельного выполнения выражений LINQ. Другими словами, обычное выражение LINQ можно легко распараллелить между любым количеством потоков. Это выполняется путем вызова `AsParallel()`, предшествующего выражению.

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

Этот код будет секционировать `facebookUsers` по потокам системы, суммировать общие лайки в каждом параллельном потоке, суммировать результаты, вычисленные каждым потоком, и выводить результат в виде понятной строки.

В виде схемы:

![Схема PLINQ](./media/using-linq/plinq-diagram.png)

Параллелизуемые задания, использующие ресурсы ЦП, которые можно легко выразить через LINQ (другими словами, чистые функции без побочных эффектов) являются отличным кандидатом для PLINQ. Для работы с заданиями, которые _имеют_ побочный эффект, рекомендуется рассмотреть возможность использования [библиотеки параллельных задач](./parallel-programming/task-parallel-library-tpl.md).

## <a name="further-resources"></a>Дополнительные ресурсы:

* [101 пример по LINQ](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b)
* [LINQPad](https://www.linqpad.net/) — среда и механизм запросов к базе данных для C#/F#/Visual Basic
* [EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/) — электронная книга с информацией по реализации LINQ to Objects
