---
title: "Использование операторов преобразования (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "операторы преобразования [C#]"
  - "преобразования [C#], операторы"
  - "операторы явного преобразования [C#]"
  - "операторы неявного преобразования [C#]"
  - "операторы [C#], преобразование"
  - "заданные пользователем преобразования [C#]"
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# Использование операторов преобразования (Руководство по программированию в C#)
Операторы преобразования `implicit`, которые удобно использовать для использования или операторы преобразования `explicit`, которые указывают, чтения на любой код, а преобразование типа.  В этом разделе показаны оба типа оператора преобразования.  
  
> [!NOTE]
>  Дополнительные сведения о преобразовании простого типа см. в разделе [Практическое руководство. Преобразование строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [Практическое руководство. Преобразование массива байтов в значение типа int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) или <xref:System.Convert>.  
  
## Пример  
 В этом примере используется оператор явного преобразования.  Этот оператор преобразует тип значения <xref:System.Byte> в тип значения `Digit`.  Поскольку в тип Digit могут быть преобразованы не все значения типа byte, преобразование выполняется явным образом, что означает использование операции приведения, как показано в методе `Main`.  
  
 [!code-cs[csProgGuideStatements#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/using-conversion-operators_1.cs)]  
  
## Пример  
 В этом примере демонстрируется неявное преобразование, в котором определяется оператор преобразования, выполняющий операцию, обратную описанной в предыдущем примере: преобразование значения типа `Digit` к целочисленному типу <xref:System.Byte>.  Поскольку к типу <xref:System.Byte> можно преобразовать любое значение типа Digit, нет нужды делать преобразование явным для пользователя.  
  
 [!code-cs[csProgGuideStatements#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/using-conversion-operators_2.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)   
 [is](../../../csharp/language-reference/keywords/is.md)