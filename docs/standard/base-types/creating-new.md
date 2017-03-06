---
title: "Создание новых строк"
description: "Создание новых строк"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 639397c7-e694-43e0-845b-1681c62bd9fd
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 793b5bc4b26967104459fa2559c6127bb82f3a9d
ms.lasthandoff: 03/02/2017

---

# <a name="creating-new-strings"></a>Создание новых строк

. NET позволяет создавать строки с помощью простой операции присваивания, а также перегружать конструктор класса для создания строк с помощью нескольких различных параметров. Кроме того, в классе [System.String](xref:System.String) .NET имеются методы для создания строковых объектов путем объединения нескольких строк, массивов строк или объектов. 

## <a name="creating-strings-using-assignment"></a>Создание строк с помощью присваивания

Самый простой способ создать новый объект [String](xref:System.String) — присвоить строковый литерал объекту [String](xref:System.String). 

## <a name="creating-strings-using-a-class-constructor"></a>Создание строк с помощью конструктора класса

С помощью перегруженного конструктора класса [String](xref:System.String) можно создавать строки из массивов символов. Кроме того, строки можно создавать путем копирования того или иного знака указанное количество раз. 

## <a name="methods-that-return-strings"></a>Методы, возвращающие строки

В следующей таблице перечислено несколько полезных методов, которые возвращают строковые объекты.

Имя метода | Применение
----------- | ---
[String.Format](xref:System.String.Format(System.String,System.Object)) | Создание форматированной строки из набора объектов ввода.
[String.Concat](xref:System.String.Concat(System.String,System.String)) | Создание строк из двух или более строк.
[String.Join](xref:System.String.Join(System.String,System.String[])) |Создание новой строки с помощью объединения массива строк.
[String.Insert](xref:System.String.Insert(System.Int32,System.String)) | Создание новой строки с помощью вставки строки в указанную позицию существующей строки.
[String.CopyTo](xref:System.String.CopyTo(System.Int32,System.Char[],System.Int32,System.Int32)) | Копирование указанных знаков в строке в указанную позицию в массиве символов.

### <a name="format"></a>Формат

Метод `String.Format` используется для создания форматированных строк и соединения строк, представляющих несколько объектов. Этот метод автоматически преобразует в строку любой переданный объект. Например, если приложению необходимо отобразить для пользователя значение [Int32](xref:System.Int32) и значение [DateTime](xref:System.DateTime), с помощью метода `Format` можно легко создать строку для представления этих значений. Сведения о правилах форматирования, используемых в этом методе, см. в разделе [Составное форматирование](composite-format.md).

В следующем примере метод `Format` используется для создания строки, содержащей целочисленную переменную.

```csharp
int numberOfFleas = 12;
string miscInfo = String.Format("Your dog has {0} fleas. " +
                                "It is time to get a flea collar. " + 
                                "The current universal date is: {1:u}.", 
                                numberOfFleas, DateTime.Now);
Console.WriteLine(miscInfo);
// The example displays the following output:
//       Your dog has 12 fleas. It is time to get a flea collar. 
//       The current universal date is: 2008-03-28 13:31:40Z.
```

```vb
Dim numberOfFleas As Integer = 12
Dim miscInfo As String = String.Format("Your dog has {0} fleas. " & _
                                       "It is time to get a flea collar. " & _ 
                                       "The current universal date is: {1:u}.", _ 
                                       numberOfFleas, Date.Now)
Console.WriteLine(miscInfo)
' The example displays the following output:
'       Your dog has 12 fleas. It is time to get a flea collar. 
'       The current universal date is: 2008-03-28 13:31:40Z.
```

В этом примере значение [DateTime.Now](xref:System.DateTime.Now) отображает текущую дату и время в соответствии с языком и региональными параметрами, связанными с текущим потоком.

### <a name="concat"></a>Concat

Метод `String.Concat` используется для простого создания нового объекта строки из двух или более существующих объектов. Он позволяет использовать независимый от языка способ сцепления строк. Этот метод принимает любой класс, производный от `System.Object`. В следующем примере создается строка из двух существующих объектов строки и символа разделителя.

```csharp
string helloString1 = "Hello";
string helloString2 = "World!";
Console.WriteLine(String.Concat(helloString1, ' ', helloString2));
// The example displays the following output:
//      Hello World!
```

```vb
Dim helloString1 As String = "Hello"
Dim helloString2 As String = "World!"
Console.WriteLine(String.Concat(helloString1, " "c, helloString2))
' The example displays the following output:
'      Hello World!
```

### <a name="join"></a>Join

Метод `String.Join` создает новую строку из массива строк и разделительной строки. Этот метод полезен в случае необходимости сцепления нескольких строк и создания списка, отделенного, например, запятой.

В следующем примере используется пробел для привязки массива строк.

```csharp
string[] words = {"Hello", "and", "welcome", "to", "my" , "world!"};
Console.WriteLine(String.Join(" ", words));
// The example displays the following output:
//      Hello and welcome to my world!
```

```vb
Dim words() As String = {"Hello", "and", "welcome", "to", "my" , "world!"}
Console.WriteLine(String.Join(" ", words))
' The example displays the following output:
'      Hello and welcome to my world!
```

### <a name="insert"></a>Insert

Метод `String.Insert` создает новую строку с помощью вставки строки в указанную позицию в другой строке. Этот метод использует отсчитываемый от нуля индекс. В следующем примере строка вставляется в пятую позицию индекса `MyString`, и создается новая строка с этим значением.

```csharp
string sentence = "Once a time.";   
 Console.WriteLine(sentence.Insert(4, " upon"));
 // The example displays the following output:
 //      Once upon a time.
```

```vb
Dim sentence As String = "Once a time."   
 Console.WriteLine(sentence.Insert(4, " upon"))
 ' The example displays the 
```

### <a name="copyto"></a>CopyTo

Метод `String.CopyTo` копирует часть строки в массив символов. Можно указать начальный индекс строки и число копируемых символов. Для копирования этому методу необходимы исходный индекс, массив знаков, индекс назначения и число символов. Все индексы отсчитываются от нуля.

В следующем примере метод `CopyTo` используется для копирования символов слова "Hello" из объекта строки в первую позицию индекса массива символов.

```csharp
string greeting = "Hello World!";
char[] charArray = {'W','h','e','r','e'};
Console.WriteLine("The original character array: {0}", new string(charArray));
greeting.CopyTo(0, charArray,0 ,5);
Console.WriteLine("The new character array: {0}", new string(charArray));
// The example displays the following output:
//       The original character array: Where
//       The new character array: Hello
```

```vb
Dim greeting As String = "Hello World!"
Dim charArray() As Char = {"W"c, "h"c, "e"c, "r"c, "e"c}
Console.WriteLine("The original character array: {0}", New String(charArray))
greeting.CopyTo(0, charArray,0 ,5)
Console.WriteLine("The new character array: {0}", New String(charArray))
' The example displays the following output:
'       The original character array: Where
'       The new character array: Hello
```

## <a name="see-also"></a>См. также

[Базовые операции со строками](basic-string-operations.md)

[Составное форматирование](composite-format.md)


