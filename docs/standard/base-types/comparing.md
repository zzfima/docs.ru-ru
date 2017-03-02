---
title: "Сравнение строк"
description: "Сравнение строк"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 920ee5e8-3d61-4941-b5af-fc50eaee427c
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 47ee37886fa2662a89730e9d52ee04987e37da2f
ms.lasthandoff: 03/02/2017

---

# <a name="comparing-strings"></a>Сравнение строк

Платформа .NET обеспечивает несколько методов для сравнения значений строк. В таблице ниже перечислены и описаны методы сравнения значений.

Имя метода | Применение
----------- | ---
[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) | Сравнивает значения двух строк. Возвращает целочисленное значение.
[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) | Сравнивает две строки без учета локального языка и региональных параметров. Возвращает целочисленное значение.
[String.CompareTo](xref:System.String.CompareTo(System.String)) | Сравнивает текущий строковый объект с другой строкой. Возвращает целочисленное значение.
[String.StartsWith](xref:System.String.StartsWith(System.String)) | Определяет, начинается ли строка с переданной строки. Возвращает логическое значение.
[String.EndsWith](xref:System.String.CompareTo(System.String)) | Определяет, заканчивается ли строка переданной строкой. Возвращает логическое значение.
[String.Equals](xref:System.String.CompareTo(System.String)) | Определяет, совпадают ли две строки. Возвращает логическое значение.
[String.IndexOf](xref:System.String.IndexOf(System.Char)) | Возвращает индекс позиции символа или строки начиная с начала проверяемой строки. Возвращает целочисленное значение.
[String.LastIndexOf](xref:System.String.LastIndexOf(System.Char)) | Возвращает индекс позиции символа или строки начиная с конца проверяемой строки. Возвращает целочисленное значение.

## <a name="compare"></a>Сравнение

Статический метод [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) позволяет тщательно сравнивать две строки. Этот метод учитывает язык и региональные параметры. Эту функцию можно использовать для сравнения двух строк или подстрок двух строк. Кроме того, имеются перегруженные методы, которые учитывают или не учитывают регистр и вариативность языка и региональных параметров. В таблице ниже приведены три целочисленных значения, которые может возвращать этот метод. 

Возвращаемое значение | Условие
------------ | ---------
Отрицательное целое число | Первая строка предшествует второй в порядке сортировки или первая строка имеет значение `null`.
0 | Первая и вторая строка равны или обе строки имеют значения `null`.
Положительное целое число или 1 | Первая строка следует за второй в порядке сортировки или вторая строка имеет значение NULL.
 
> [!IMPORTANT]
> Метод [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) в основном предназначен для использования при упорядочивании или сортировке строк. Не следует использовать метод [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) для проверки на равенство (то есть для явного поиска возвращаемого значения 0 без учета того, является ли одна строка меньше или больше другой). Для определения равенства двух строк используйте метод [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)).

В примере ниже метод [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) используется для определения относительных значений двух строк.

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.Compare(string1, "Hello World?"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.Compare(string1, "Hello World?"))
```

Этот пример выводит на консоль значение `-1`.

## <a name="compareordinal"></a>CompareOrdinal

Метод [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) сравнивает два строковых объекта без учета локального языка и региональных параметров. Возвращаемые этим методом значения идентичны значениям, возвращаемым методом `Compare` в предыдущей таблице.

> [!IMPORTANT]
> Метод [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) в основном предназначен для использования при упорядочивании или сортировке строк. Не следует использовать метод [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) для проверки на равенство (то есть для явного поиска возвращаемого значения 0 без учета того, является ли одна строка меньше или больше другой). Для определения равенства двух строк используйте метод [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)).

В примере ниже метод `CompareOrdinal` используется для сравнения значений двух строк.

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"))
```

Этот пример выводит на консоль значение `-32`.

## <a name="compareto"></a>CompareTo

Метод [String.CompareTo](xref:System.String.CompareTo(System.String)) сравнивает строку, которую инкапсулирует текущий строковый объект, с другой строкой или объектом. Возвращаемые этим методом значения идентичны значениям, возвращаемым методом `String.Compare` в предыдущей таблице.

> [!IMPORTANT]
> Метод [String.CompareTo](xref:System.String.CompareTo(System.String)) в основном предназначен для использования при упорядочивании или сортировке строк. Не следует использовать метод [String.CompareTo](xref:System.String.CompareTo(System.String)) для проверки на равенство (то есть для явного поиска возвращаемого значения 0 без учета того, является ли одна строка меньше или больше другой). Для определения равенства двух строк используйте метод [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)).

В примере ниже метод `String.CompareTo` используется для сравнения объекта `string1` с объектом `string2`.

```csharp
string string1 = "Hello World";
string string2 = "Hello World!";
int MyInt = string1.CompareTo(string2);
Console.WriteLine( MyInt );
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World!"
Dim MyInt As Integer = string1.CompareTo(string2)
Console.WriteLine(MyInt)
```

Этот пример выводит на консоль значение `-1`.

## <a name="equals"></a>Равно

С помощью метода [String.Equals](xref:System.String.CompareTo(System.String)) можно легко определить идентичность двух строк. Этот метод учитывает регистр и возвращает логическое значение `true` или `false`. Метод можно вызывать из существующего класса, как показано в следующем примере. В примере ниже метод `Equals` используется для определения того, содержит ли строковый объект фразу "Hello World".

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.Equals("Hello World"));
```

```vb
Dim string1 As String = "Hello World"
Console.WriteLine(string1.Equals("Hello World"))
```

Этот пример выводит на консоль значение `true`.

Этот метод также можно использовать как статический. В примере ниже два строковых объекта сравниваются с помощью статического метода.

```csharp
string string1 = "Hello World";
string string2 = "Hello World";
Console.WriteLine(String.Equals(string1, string2));
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World"
Console.WriteLine(String.Equals(string1, string2))
```

Этот пример выводит на консоль значение `true`.

## <a name="startswith-and-endswith"></a>StartsWith и EndsWith

Метод [String.StartsWith](xref:System.String.StartsWith(System.String)) можно использовать для определения того, начинается ли строковый объект с тех же символов, которые включает другая строка. Этот метод учитывает регистр и возвращает значение `true`, если текущий строковый объект начинается с переданной строки, и значение `false` в противном случае. В примере ниже этот метод используется для определения того, начинается ли строковый объект со слова "Hello".

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.StartsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.StartsWith("Hello"))
```

Этот пример выводит на консоль значение `true`.

Метод [String.EndsWith](xref:System.String.CompareTo(System.String)) сравнивает переданную строку с символами, находящимися в конце текущего строкового объекта. Он также возвращает логическое значение. В примере ниже конец строки проверяется с помощью метода `EndsWith`.

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.EndsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.EndsWith("Hello"))
```

Этот пример выводит на консоль значение `false`.

## <a name="indexof-and-lastindexof"></a>IndexOf и LastIndexOf

С помощью метода [String.IndexOf](xref:System.String.IndexOf(System.Char)) можно определить позицию первого вхождения конкретного символа в строку. Этот метод учитывает регистр и начинает отсчет с начала строки. Он возвращает позицию переданного символа, используя отсчитываемый от нуля индекс. Если символ не удается найти, возвращается значение –1.

В примере ниже метод `IndexOf` используется для поиска первого вхождения символа "`l`" в строку.

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.IndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.IndexOf("l"))
```

Этот пример выводит на консоль значение `2`.

Метод [String.LastIndexOf](xref:System.String.LastIndexOf(System.Char)) аналогичен методу `String.IndexOf` за исключением того, что он возвращает позицию последнего вхождения конкретного символа в строку. Он учитывает регистр и использует отсчитываемый от нуля индекс. 

В примере ниже метод `LastIndexOf` используется для поиска последнего вхождения символа "`l`" в строку.

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.LastIndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.LastIndexOf("l"))
```

Этот пример выводит на консоль значение `9`.

Оба метода полезно использовать в сочетании с методом [String.Remove](xref:System.String.Remove(System.Int32)). Для получения позиции символа используется метод `IndexOf` или `LastIndexOf`, после чего эта позиция передается методу `Remove method` для удаления символа или начинающегося с него слова.

## <a name="see-also"></a>См. также

[Базовые операции со строками](basic-string-operations.md)













