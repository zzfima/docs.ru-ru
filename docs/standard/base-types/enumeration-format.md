---
title: "Строки форматов перечисления"
description: "Строки форматов перечисления"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 4d581898-99bc-42c3-816c-d8238f45096f
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 8cb811636ca2c7b207f7661e990567b5785bc994

---

# <a name="enumeration-format-strings"></a>Строки форматов перечисления

Метод [Enum.ToString](xref:System.Enum.ToString) можно использовать для создания новой строки, представляющей числовое, шестнадцатеричное или строковое значение элемента перечисления. Этот метод принимает строку формата перечисления, чтобы задать возвращаемое значение.

В следующей таблице приведены строки форматов перечисления и возвращаемые методом значения. Описатели формата не учитывают регистр.

## <a name="the-g-or-g-format-strings"></a>Строки формата G или g

Строки формата G или g отображают перечисление в виде строкового значения, если это возможно. В противном случае отображают целочисленное значение текущего экземпляра. Если для перечисления задан атрибут `Flags`, строковые значения всех допустимых записей соединяются (в качестве разделителя используется запятая). Если атрибут `Flags` не задан, недопустимое значение отображается в виде числовых записей. В следующем примере показан описатель формата G.

```csharp
Console.WriteLine(ConsoleColor.Red.ToString("G"));         // Displays Red
FileAttributes attributes = FileAttributes.Hidden |
                            FileAttributes.Archive;
Console.WriteLine(attributes.ToString("G"));   // Displays Hidden, Archive
```

```vb
Console.WriteLine(ConsoleColor.Red.ToString("G"))           ' Displays Red
Dim attributes As FileAttributes = FileAttributes.Hidden Or _
                                   FileAttributes.Archive
Console.WriteLine(attributes.ToString("G"))     ' Displays Hidden, Archive
```

## <a name="the-f-or-f-format-strings"></a>Строки формата F или f

Строки формата F или f отображают перечисление в виде строкового значения, если это возможно. Если перечисление полностью можно отобразить в виде строки как совокупность всех элементов перечисления (даже если атрибут `Flags` не задан), то строковые значения всех действительных записей соединяются (в качестве разделителя используется запятая). Если значение не может быть определено по записям перечисления, то значение форматируется аналогично целому типу. В следующем примере показан описатель формата F.

```csharp
Console.WriteLine(ConsoleColor.Blue.ToString("F"));       // Displays Blue
FileAttributes attributes = FileAttributes.Hidden | 
                            FileAttributes.Archive;
Console.WriteLine(attributes.ToString("F"));   // Displays Hidden, Archive
```

```vb
Console.WriteLine(ConsoleColor.Blue.ToString("F"))         ' Displays Blue
Dim attributes As FileAttributes = FileAttributes.Hidden Or _
                                   FileAttributes.Archive
Console.WriteLine(attributes.ToString("F"))     ' Displays Hidden, Archive
```

## <a name="the-d-or-d-format-strings"></a>Строки формата D или d

Строки формата D или d отображают запись перечисления в кратчайшем целочисленном представлении. В следующем примере показан описатель формата D.

```csharp
Console.WriteLine(ConsoleColor.Cyan.ToString("D"));         // Displays 11
FileAttributes attributes = FileAttributes.Hidden |
                            FileAttributes.Archive;
Console.WriteLine(attributes.ToString("D"));                // Displays 34
````

```vb
Console.WriteLine(ConsoleColor.Cyan.ToString("D"))           ' Displays 11
Dim attributes As FileAttributes = FileAttributes.Hidden Or _
                                   FileAttributes.Archive
Console.WriteLine(attributes.ToString("D"))                  ' Displays 34 
```

## <a name="the-x-or-x-format-strings"></a>Строки формата X или x

Строки формата X или x отображают перечисление в виде шестнадцатеричного значения. При необходимости значение дополняется начальными нулями, чтобы оно состояло как минимум из восьми знаков. В следующем примере показан описатель формата X.

```csharp
Console.WriteLine(ConsoleColor.Cyan.ToString("X"));   // Displays 0000000B
FileAttributes attributes = FileAttributes.Hidden |
                            FileAttributes.Archive;
Console.WriteLine(attributes.ToString("X"));          // Displays 00000022
```

```vb
Console.WriteLine(ConsoleColor.Cyan.ToString("X"))     ' Displays 0000000B
Dim attributes As FileAttributes = FileAttributes.Hidden Or _
                                   FileAttributes.Archive
Console.WriteLine(attributes.ToString("X"))            ' Displays 00000022 
```

## <a name="example"></a>Пример

В следующем примере определяется перечисление с именем `Colors`, состоящее из трех элементов: `Red`, `Blue` и `Green`.

 ```csharp
 public enum Color {Red = 1, Blue = 2, Green = 3}
```

```vb
Public Enum Color
   Red = 1
   Blue = 2
   Green = 3
End Enum
```

После определения перечисления может быть объявлен, как показано далее.

```csharp
Color myColor = Color.Green;
```

```vb
Dim myColor As Color = Color.Green
```

Затем метод `Color.ToString(System.String)` можно использовать для отображения значений перечисления различными способами в зависимости от переданного описателя формата.

```csharp
Console.WriteLine("The value of myColor is {0}.", 
                  myColor.ToString("G"));
Console.WriteLine("The value of myColor is {0}.", 
                  myColor.ToString("F"));
Console.WriteLine("The value of myColor is {0}.", 
                  myColor.ToString("D"));
Console.WriteLine("The value of myColor is 0x{0}.", 
                  myColor.ToString("X"));
// The example displays the following output to the console:
//       The value of myColor is Green.
//       The value of myColor is Green.
//       The value of myColor is 3.
//       The value of myColor is 0x00000003.
```

```vb
Console.WriteLine("The value of myColor is {0}.", _
                  myColor.ToString("G"))
Console.WriteLine("The value of myColor is {0}.", _
                  myColor.ToString("F"))
Console.WriteLine("The value of myColor is {0}.", _
                  myColor.ToString("D"))
Console.WriteLine("The value of myColor is 0x{0}.", _
                  myColor.ToString("X"))
' The example displays the following output to the console:
'       The value of myColor is Green.
'       The value of myColor is Green.
'       The value of myColor is 3.
'       The value of myColor is 0x00000003. 
```

## <a name="see-also"></a>См. также

[Типы форматирования](formatting-types.md)




<!--HONumber=Nov16_HO1-->


