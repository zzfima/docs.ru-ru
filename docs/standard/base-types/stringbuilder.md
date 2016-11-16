---
title: "Использование класса StringBuilder"
description: "Использование класса StringBuilder"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: f4f5d1c7-d84d-4867-810f-2708cd6de0da
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 1e8453b78827d8c02f29135ddfb832956ab40f3c

---

# <a name="using-the-stringbuilder-class"></a>Использование класса StringBuilder

Объект [String](xref:System.String) является неизменяемым. Каждый раз при использовании одного из методов в классе [System.String](xref:System.String) вы создаете новый объект строки в памяти. При этом для нового объекта требуется новое выделение пространства. В тех случаях, когда необходимо выполнять повторяющиеся модификации строки, издержки, связанные с созданием нового объекта [String](xref:System.String), могут оказаться значительными. Чтобы изменять строку без создания нового объекта, можно использовать класс [System.Text.StringBuilder](xref:System.Text.StringBuilder). Например, использование класса [StringBuilder](xref:System.Text.StringBuilder) может повысить производительность при соединении большого количества строк в цикле.

## <a name="importing-the-systemtext-namespace"></a>Импорт пространства имен System.Text

Класс [StringBuilder](xref:System.Text.StringBuilder) находится в пространстве имен [System.Text](xref:System.Text). Чтобы избежать необходимости предоставления полного имени типа в коде, вы можете импортировать пространство имен [System.Text](xref:System.Text), как показано ниже. 

```csharp
using System;
using System.Text;
```

```vb
Imports System.Text
```

## <a name="instantiating-a-stringbuilder-object"></a>Создание экземпляров объекта StringBuilder

Вы можете создать новый экземпляр класса [StringBuilder](xref:System.Text.StringBuilder) путем инициализации переменной с помощью одного из перегруженных методов конструктора, как показано в следующем примере.

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
```

## <a name="setting-the-capacity-and-length"></a>Настройка емкости и длины

Хотя [StringBuilder](xref:System.Text.StringBuilder) является динамическим объектом, который позволяет вам развернуть ряд символов в строке, которые она инкапсулирует, можно указать максимальное число содержащихся в ней символов. Это значение называется емкостью объекта, и его не следует путать с длиной строки, которую содержит текущий объект [StringBuilder](xref:System.Text.StringBuilder). Например, вы можете создать новый экземпляр класса [StringBuilder](xref:System.Text.StringBuilder) со строкой Hello, длина которой составляет 5 символов, или указать, что максимальная емкость объекта — 25. При изменении [StringBuilder](xref:System.Text.StringBuilder) размер не перераспределяется, пока не будет достигнута граница емкости. Когда это происходит, новое пространство выделяется автоматически, а емкость удваивается. Емкость класса [StringBuilder](xref:System.Text.StringBuilder) можно указать с помощью одного из перегруженных конструкторов. В следующем примере показано, что объект `MyStringBuilder` можно развернуть максимум на 25 позиций.

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!", 25);
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!", 25) 
```

Кроме того, вы можете использовать свойство [Capacity](xref:System.Text.StringBuilder.Capacity) для чтения или записи, чтобы задать максимальную длину объекта. В следующем примере используется свойство [Capacity](xref:System.Text.StringBuilder.Capacity) для определения максимальной длины объекта.

```csharp
MyStringBuilder.Capacity = 25;
```

```vb
MyStringBuilder.Capacity = 25
```

Для проверки емкости текущего объекта [StringBuilder](xref:System.Text.StringBuilder) можно использовать метод [EnsureCapacity](xref:System.Text.StringBuilder.EnsureCapacity(System.Int32)). Если емкость больше переданного значения, изменения не вносятся; однако если емкость меньше переданного значения, текущая емкость изменяется для соответствия переданному значению.

Можно также просмотреть или задать свойство [Length](xref:System.Text.StringBuilder.Length). Если вы задали для свойства [Length](xref:System.Text.StringBuilder.Length) значение больше значения свойства [Capacity](xref:System.Text.StringBuilder.Capacity), значение свойства [Capacity](xref:System.Text.StringBuilder.Capacity) будет автоматически изменено на то же самое значение, что и у свойства [Length](xref:System.Text.StringBuilder.Length). Если задать для свойства [Length](xref:System.Text.StringBuilder.Length) значение меньше длины строки в текущем объекте [StringBuilder](xref:System.Text.StringBuilder), строка будет укорочена.

## <a name="modifying-the-stringbuilder-string"></a>Изменение строки StringBuilder

В следующей таблице перечислены методы, которые можно использовать для изменения содержимого объекта [StringBuilder](xref:System.Text.StringBuilder).

Имя метода | Применение
----------- | ---
[StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char)) | Добавляет сведения в конец текущего объекта [StringBuilder](xref:System.Text.StringBuilder).
[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) | Заменяет отформатированным текстом описатель формата, переданный в строке.
[StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char)) | Вставляет строку или объект в указанный индекс текущего объекта [StringBuilder](xref:System.Text.StringBuilder).
[StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) | Удаляет указанное количество символов из текущего объекта [StringBuilder](xref:System.Text.StringBuilder).
[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Заменяет указанный символ в указанном индексе.

### <a name="append"></a>Добавить

Метод [StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char)) можно использовать для добавления текста или представления строки объекта к концу строки, представленной текущим объектом [StringBuilder](xref:System.Text.StringBuilder). Следующий пример инициализирует [StringBuilder](xref:System.Text.StringBuilder) с текстом Hello World, а затем добавляет текст в конец объекта. Пространство выделяется автоматически при необходимости.

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Append(" What a beautiful day.");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World! What a beautiful day.
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Append(" What a beautiful day.")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World! What a beautiful day.
```

### <a name="appendformat"></a>AppendFormat

Метод [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) добавляет текст в конец объекта [StringBuilder](xref:System.Text.StringBuilder). Он поддерживает возможность составного форматирования (дополнительные сведения см. в разделе [Составное форматирование](composite-format.md)) путем вызова реализации [IFormattable](xref:System.IFormattable) форматируемого объекта или объектов. Следовательно, он принимает строки стандартного формата для числовых значений, значений даты и времени, значений перечисления, строки пользовательского формата для чисел и дат и строки формата, определенные для пользовательских типов. (Дополнительные сведения о форматировании см. в разделе [Типы форматирования](formatting-types.md).) Вы можете использовать этот метод для настройки формата переменных и добавления этих значений в объект [StringBuilder](xref:System.Text.StringBuilder). В следующем примере используется метод AppendFormat для размещения целочисленного значения, отформатированного в качестве значения валюты в конце объекта [StringBuilder](xref:System.Text.StringBuilder).

```csharp
int MyInt = 25; 
StringBuilder MyStringBuilder = new StringBuilder("Your total is ");
MyStringBuilder.AppendFormat("{0:C} ", MyInt);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Your total is $25.00
```

```vb
Dim MyInt As Integer = 25
Dim MyStringBuilder As New StringBuilder("Your total is ")
MyStringBuilder.AppendFormat("{0:C} ", MyInt)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'     Your total is $25.00 
```

### <a name="insert"></a>Insert

Метод [StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char)) добавляет строку или объект в указанную позицию в текущем объекте [StringBuilder](xref:System.Text.StringBuilder). В следующем примере этот метод используется для вставки слова в шестую позицию объекта [StringBuilder](xref:System.Text.StringBuilder).

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Insert(6,"Beautiful ");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello Beautiful World!
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Insert(6, "Beautiful ")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'      Hello Beautiful World!
```

### <a name="remove"></a>Удалить

Вы можете использовать метод [StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)), чтобы удалить указанное количество символов из текущего объекта [StringBuilder](xref:System.Text.StringBuilder), начиная с указанного индекса (с отсчетом с нуля). В следующем примере используется метод [Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) для сокращения объекта [StringBuilder](xref:System.Text.StringBuilder).

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Remove(5,7);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Remove(5, 7)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello
```

### <a name="replace"></a>Заменить

[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) |Заменяет указанный символ в указанном индексе.
можно использовать для замены символов в объекте [StringBuilder](xref:System.Text.StringBuilder) другими указанными символами. В следующем примере метод [Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) |Заменяет указанный символ в указанном индексе.
используется для поиска объекта [StringBuilder](xref:System.Text.StringBuilder) для всех экземпляров восклицательного знака (!) и замены их знаком вопроса (?).
 
 ```csharp
 StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Replace('!', '?');
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World?
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Replace("!"c, "?"c)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World?
```

## <a name="converting-a-stringbuilder-object-to-a-string"></a>Преобразование объекта StringBuilder в строку

Необходимо преобразовать объект [StringBuilder](xref:System.Text.StringBuilder) в объект [String](xref:System.String) перед тем, как вы сможете передать строку, представленную объектом [StringBuilder](xref:System.Text.StringBuilder), методу, который содержит параметр [String](xref:System.String), или отобразить ее в пользовательском интерфейсе. Это преобразование можно выполнить, вызвав метод [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString). В следующем примере вызывается ряд методов [StringBuilder](xref:System.Text.StringBuilder), а затем вызывается метод [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) для отображения строки.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      StringBuilder sb = new StringBuilder();
      bool flag = true;
      string[] spellings = { "recieve", "receeve", "receive" };
      sb.AppendFormat("Which of the following spellings is {0}:", flag);
      sb.AppendLine();
      for (int ctr = 0; ctr <= spellings.GetUpperBound(0); ctr++) {
         sb.AppendFormat("   {0}. {1}", ctr, spellings[ctr]);
         sb.AppendLine();
      }
      sb.AppendLine();
      Console.WriteLine(sb.ToString());
   }
}
// The example displays the following output:
//       Which of the following spellings is True:
//          0. recieve
//          1. receeve
//          2. receive
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim sb As New StringBuilder()
      Dim flag As Boolean = True
      Dim spellings() As String = { "recieve", "receeve", "receive" }
      sb.AppendFormat("Which of the following spellings is {0}:", flag)
      sb.AppendLine()
      For ctr As Integer = 0 To spellings.GetUpperBound(0)
         sb.AppendFormat("   {0}. {1}", ctr, spellings(ctr))
         sb.AppendLine()
      Next
      sb.AppendLine()
      Console.WriteLine(sb.ToString())
   End Sub
End Module
' The example displays the following output:
'       Which of the following spellings is True:
'          0. recieve
'          1. receeve
'          2. receive
```

## <a name="see-also"></a>См. также

[System.Text.StringBuilder](xref:System.Text.StringBuilder)

[Базовые операции со строками](basic-string-operations.md)

[Типы форматирования](formatting-types.md)



<!--HONumber=Nov16_HO1-->


