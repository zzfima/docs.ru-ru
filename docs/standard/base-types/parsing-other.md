---
title: "Анализ других строк в .NET"
description: "Анализ других строк в .NET"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 67670b10-3df4-45ea-8908-5ba3f056887c
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 3f26670dc9f4c6b6608599793352445d5665cf64

---

# <a name="parsing-other-strings-in-net"></a>Анализ других строк в .NET

Кроме числовых строк и строк [DateTime](xref:System.DateTime) можно также разбирать строки, представляющие типы [Char](xref:System.Char), [Boolean](xref:System.Boolean) и [Enum](xref:System.Enum), в типы данных.

## <a name="char"></a>Char

Метод статического анализа, связанный с типом данных[Char](xref:System.Char), полезен для преобразования строки, содержащей один символ, в его значение в кодировке Юникод. В следующем примере кода выполняется разбор строки в символ Юникода.

```csharp
string MyString1 = "A";
char MyChar = Char.Parse(MyString1);
// MyChar now contains a Unicode "A" character.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="boolean"></a>Boolean

Тип данных [Boolean](xref:System.Boolean) содержит метод [Parse](xref:System.Boolean.Parse(System.String)), который можно использовать для преобразования строки, представляющей значение `Boolean`, в реальный тип `Boolean`. Этот метод не учитывает регистр и может успешно анализировать строку, содержащую значения "True" или "False". Метод `Parse`, связанный с типом `Boolean`, может также анализировать строки, окруженные пробелами. Если передается любая другая строка, создается исключение [FormatException](xref:System.FormatException).

В следующем примере кода показано использование метода `Parse` для преобразования строки в значение `Boolean`.

```csharp
string MyString2 = "True";
bool MyBool = bool.Parse(MyString2);
// MyBool now contains a True Boolean value.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="enumeration"></a>Перечисление

Статический метод [Parse](xref:System.Enum.Parse(System.Type,System.String)) можно использовать, чтобы инициализировать значение строки типом перечисления. Этот метод принимает тип перечисления для разбора, анализируемую строку и необязательный флаг `Boolean`, указывающий, будет ли при анализе учитываться регистр. Анализируемая строка может содержать несколько значений, разделенных запятыми; перед этими значениями или после них могут быть один или несколько пробелов. Если строка содержит несколько значений, то возвращаемый объект будет содержать сочетание заданных значений, полученное с использованием побитовой операции OR.

В следующем примере показано использование метода `Parse` для преобразования строкового представления в значение перечисления. Перечислению [DayOfWeek](xref:System.DayOfWeek) присваивается значение Thursday из строки.

```csharp
string MyString3 = "Thursday";
DayOfWeek MyDays = (DayOfWeek)Enum.Parse(typeof(DayOfWeek), MyString3);
Console.WriteLine(MyDays);
// The result is Thursday.
```

```vb
Dim MyString3 As String = "Thursday"
Dim MyDays As DayOfWeek = CType([Enum].Parse(GetType(DayOfWeek), MyString3), DayOfWeek)
Console.WriteLine("{0:G}", MyDays)
' The result is Thursday.
```

## <a name="see-also"></a>См. также

[Анализ строк в .NET](parsing-strings.md)

[Типы форматирования в .NET](formatting-types.md)

[Преобразование типов в .NET](type-conversion.md)




<!--HONumber=Nov16_HO1-->


