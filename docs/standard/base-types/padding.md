---
title: "Заполнение строк"
description: "Заполнение строк"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 1c8b3b44-d370-49e1-90b5-64ac81c02ae91c8b3b44-d370-49e1-90b5-64ac81c02ae9
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: b6c5d4c8a35aebdfca88801118cdeba25c0a7e65

---

# <a name="padding-strings"></a>Заполнение строк

Для создания новой строки, состоящей из исходной строки, дополненной знаками до указанной общей длины с начала или с конца, следует использовать один из следующих методов класса [System.String](xref:System.String). В качестве заполняющего знака, который, соответственно, будет повторяться либо справа, либо слева, может использоваться пробел или знак, заданный в явной форме.

Имя метода | Применение
----------- | ---
[String.PadLeft](xref:System.String.PadLeft(System.Int32)) | Дополняет строку до указанной общей длины знаками с начала.
[String.PadRight](xref:System.String.PadRight(System.Int32)) | Дополняет строку до указанной общей длины знаками с конца.

## <a name="padleft"></a>PadLeft

Метод [String.PadLeft](xref:System.String.PadLeft(System.Int32)) создает новую строку, присоединяя к исходной строке знаки с начала в количестве, необходимом для достижения указанной общей длины. В методе [String.PadLeft(Int32)](xref:System.String.PadLeft(System.Int32)) в качестве заполняющих знаков используются пробелы, а метод [String.PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) позволяет задать заполняющий знак в явной форме.

В следующем примере кода метод [PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) используется для создания новой строки длиной в двадцать знаков. Этот пример выводит на консоль значение "`--------Hello World!`".

```csharp
string MyString = "Hello World!";
Console.WriteLine(MyString.PadLeft(20, '-'));
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.PadLeft(20, "-"c))
```

## <a name="padright"></a>PadRight

Метод [String.PadRight](xref:System.String.PadRight(System.Int32)) создает новую строку, присоединяя к исходной строке знаки с конца в количестве, необходимом для достижения указанной общей длины. В методе [String.PadRight(Int32)](xref:System.String.PadRight(System.Int32)) в качестве заполняющих знаков используются пробелы, а метод [String.PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) позволяет задать заполняющий знак в явной форме.

В следующем примере кода метод [PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) используется для создания новой строки длиной в двадцать знаков. Этот пример выводит на консоль значение "`Hello World!--------`".

```csharp
string MyString = "Hello World!";
Console.WriteLine(MyString.PadRight(20, '-'));
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.PadRight(20, "-"c))
```

## <a name="see-also"></a>См. также

[Базовые операции со строками](basic-string-operations.md)




<!--HONumber=Nov16_HO3-->


