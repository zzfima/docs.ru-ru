---
title: "Сокращение и удаление символов из строк"
description: "Сокращение и удаление символов из строк"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 95d818bc-2661-43f6-adb8-13b53abf9682
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 96cf08c0de8ba73d931d561187369ccf8b091651

---

# <a name="trimming-and-removing-characters-from-strings"></a>Сокращение и удаление символов из строк

При разборе предложения на отдельные слова может оказаться, что в начале или в конце некоторых слов стоят пробелы. В этом случае можно воспользоваться методами сокращения в классе [System.String](https://docs.microsoft.com/dotnet/core/api/System.String), чтобы удалить любое количество пробелов или других символов из указанной позиции в строке. В таблице ниже описаны доступны методы сокращения.

Имя метода | Применение
----------- | ---
[String.Trim](https://docs.microsoft.com/dotnet/core/api/System.String.Trim) | Удаление пробелов или знаков, указанных в массиве знаков, из начала и конца строки.
[String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) | Удаление символов, указанных в массиве символов, в конце строки.
[String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) | Удаление символов, указанных в массиве символов, в начале строки.
[String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32)) | Удаление указанного количества символов в указанной позиции индекса в строке.


## <a name="trim"></a>Trim

Простой способ удалить пробелы с обоих концов строки — метод [String.Trim](https://docs.microsoft.com/dotnet/core/api/System.String.Trim), пример использования которого приведен ниже.

```csharp
string MyString = " Big   ";
Console.WriteLine("Hello{0}World!", MyString);
string TrimString = MyString.Trim();
Console.WriteLine("Hello{0}World!", TrimString);
//       The example displays the following output:
//             Hello Big   World!
//             HelloBigWorld!
```

```vb
Dim MyString As String = " Big   "
Console.WriteLine("Hello{0}World!", MyString)
Dim TrimString As String = MyString.Trim()
Console.WriteLine("Hello{0}World!", TrimString)
' The example displays the following output:
'       Hello Big   World!
'       HelloBigWorld!
```

Кроме того, можно удалить символы, указанные в массиве знаков, из начала и конца строки. В следующем примере удаляются символы пробелов, точки и звездочки.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String header = "* A Short String. *";
      Console.WriteLine(header);
      Console.WriteLine(header.Trim( new Char[] { ' ', '*', '.' } ));
   }
}
// The example displays the following output:
//       * A Short String. *
//       A Short String
```

```vb
Module Example
   Public Sub Main()
      Dim header As String = "* A Short String. *"
      Console.WriteLine(header)
      Console.WriteLine(header.Trim( { " "c, "*"c, "."c } ))
   End Sub
End Module
' The example displays the following output:
'       * A Short String. *
'       A Short String
```

## <a name="trimend"></a>TrimEnd

Метод [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) удаляет символы в конце строки, создавая новый строковый объект. Для указания символов, которые следует удалять, в этот метод передается массив символов. Порядок элементов в массиве символов не влияет на выполнение операции сокращения. В случае обнаружения символа, который отсутствует в массиве, операция останавливается.

Ниже приведен пример удаления последних букв строки с помощью метода TrimEnd. В этом примере положение символов `'r'` и `'W'` изменено для иллюстрации того, что порядок символов в массиве не имеет значения. Обратите внимание, что этот код удаляет последнее слово `MyString` и часть первого.

```csharp
string MyString = "Hello World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

Этот код выводит на консоль значение `He`.

Ниже приведен пример удаления последнего слова строки с помощью метода [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])). В этом коде после слова `Hello` следует запятая, а поскольку запятая не указана в массиве символов для сокращения, то выполнение операции прекращается на запятой.

```csharp
string MyString = "Hello, World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello, World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

Этот код выводит на консоль значение `Hello,`.

## <a name="trimstart"></a>TrimStart

Метод [String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) аналогичен методу [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) за исключением того, что он создает новую строку путем удаления знаков в начале существующего строкового объекта. Для указания символов, которые следует удалять, в метод [TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) передается массив символов. Как и в случае с методом [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])), порядок элементов в массиве символов не влияет на выполнение операции сокращения. В случае обнаружения символа, который отсутствует в массиве, операция останавливается.

В следующем примере удаляется первое слово в строке. В этом примере положение символов `'l'` и `'H'` изменено для иллюстрации того, что порядок символов в массиве не имеет значения.

```csharp
string MyString = "Hello World!";
char[] MyChar = {'e', 'H','l','o',' ' };
string NewString = MyString.TrimStart(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"e","H","l","o"," " }
Dim NewString As String = MyString.TrimStart(MyChar)
Console.WriteLine(NewString)
```

Этот код выводит на консоль значение `World!`.

## <a name="remove"></a>Удалить

Метод [String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32)) удаляет указанное количество символов, начиная с указанного места в существующей строке. Этот метод подразумевает, что отсчет индекса начинается с нуля.

В следующем примере из строки удаляется десять символов, начиная с пятой позиции отсчитываемого от нуля индекса строки.

```csharp
string MyString = "Hello Beautiful World!";
Console.WriteLine(MyString.Remove(5,10));
// The example displays the following output:
//         Hello World!  
```

```vb
Dim MyString As String = "Hello Beautiful World!"
Console.WriteLine(MyString.Remove(5,10))
' The example displays the following output:
'         Hello World!
```

Чтобы удалить из строки указанный символ или подстроку, можно вызвать метод [String.Replace(String, String)](https://docs.microsoft.com/dotnet/core/api/System.String.Replace(System.String,System.String)) и указать пустую строку ([String.Empty](https://docs.microsoft.com/dotnet/core/api/System.String.Empty)) в качестве замены. В следующем примере удаляются все запятые из строки.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String phrase = "a cold, dark night";
      Console.WriteLine("Before: {0}", phrase);
      phrase = phrase.Replace(",", "");
      Console.WriteLine("After: {0}", phrase);
   }
}
// The example displays the following output:
//       Before: a cold, dark night
//       After: a cold dark night
```

```vb
Module Example
   Public Sub Main()
      Dim phrase As String = "a cold, dark night"
      Console.WriteLine("Before: {0}", phrase)
      phrase = phrase.Replace(",", "")
      Console.WriteLine("After: {0}", phrase)
   End Sub
End Module
' The example displays the following output:
'       Before: a cold, dark night
'       After: a cold dark night
```

## <a name="see-also"></a>См. также

[Базовые операции со строками](basic-string-operations.md)




<!--HONumber=Nov16_HO1-->


