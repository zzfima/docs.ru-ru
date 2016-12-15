---
title: "ulong (справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ulong_CSharpKeyword"
  - "ulong"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "ulong - ключевое слово [C#]"
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# ulong (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `ulong` обозначает целочисленный тип, в котором хранятся значения, размер и диапазон которых приведены в следующей таблице.  
  
|Тип|Диапазон|Размер|Тип платформы .NET Framework|  
|---------|--------------|------------|----------------------------------|  
|`ulong`|От 0 до 18,446,744,073,709,551,615|64\-разрядное целое число без знака|<xref:System.UInt64?displayProperty=fullName>|  
  
## Литералы  
 Переменную типа `ulong` можно объявить и инициализировать, как показано в этом примере:  
  
```  
  
ulong uLong = 9223372036854775808;  
```  
  
 Если целочисленный литерал не имеет суффикса, его тип — первый из этих типов, в котором может быть представлено его значение: [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), `ulong`.  В приведенном выше примере таким типом является `ulong`.  
  
 Суффиксы можно также использовать для задания типа литерала в соответствии со следующими правилами:  
  
-   Если используется L или l, то в зависимости от размера литерал будет иметь целочисленный тип [long](../../../csharp/language-reference/keywords/long.md) или `ulong`.  
  
    > [!NOTE]
    >  Букву "l" в нижнем регистре можно использовать в качестве суффикса.  Однако при этом выдается предупреждение компилятора, так как букву "l" легко перепутать с цифрой "1". Для ясности используйте "L".  
  
-   Если используется `U` или `u`, то в зависимости от размера литерал будет иметь целочисленный тип [uint](../../../csharp/language-reference/keywords/uint.md) или `ulong`.  
  
-   Если используется UL, ul, Ul, uL, LU, lu, Lu или lU, то в зависимости от размера литерал будет иметь целочисленный тип `ulong`.  
  
     Например, результатом использования трех следующих операторов будет системный тип `UInt64`, соответствующий псевдониму `ulong`:  
  
    ```  
    Console.WriteLine(9223372036854775808L.GetType());  
    Console.WriteLine(123UL.GetType());  
    Console.WriteLine((123UL + 456).GetType());  
    ```  
  
 Обычно суффикс используется для вызова перегруженных методов.  Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `ulong` и [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 Использование суффикса с параметром `ulong` гарантирует вызов метода правильного типа, например:  
  
```  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## Преобразования  
 Существует предопределенное неявное преобразование типа `ulong` в тип [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Неявного преобразования типа `ulong` в любой целочисленный тип не существует.  Например, следующий оператор вызывает ошибку компиляции без явного приведения:  
  
```  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 Существует предопределенное неявное преобразование типа [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md) или [char](../../../csharp/language-reference/keywords/char.md) в тип `ulong`.  
  
 Кроме того, неявного преобразования типов с плавающей запятой в тип `ulong` не существует.  Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:  
  
```  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделе [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).  
  
 Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 <xref:System.UInt64>   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)