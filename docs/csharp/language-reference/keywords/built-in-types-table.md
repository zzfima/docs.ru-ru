---
title: "Таблица встроенных типов (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "встроенные типы C#"
  - "типы [C#], встроенные"
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Таблица встроенных типов (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В приведенной ниже таблице представлены ключевые слова для встроенных типов C\#, которые являются псевдонимами предопределенных типов в пространстве имен <xref:System>.  
  
|Тип C\#|Тип .NET Framework|  
|-------------|------------------------|  
|[bool](../../../csharp/language-reference/keywords/bool.md)|`System.Boolean`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`System.Byte`|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`System.SByte`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`System.Char`|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|`System.Decimal`|  
|[double](../../../csharp/language-reference/keywords/double.md)|`System.Double`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`System.Single`|  
|[Целочисленное значение.](../../../csharp/language-reference/keywords/int.md)|`System.Int32`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`System.UInt32`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`System.Int64`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`System.UInt64`|  
|[Объект.](../../../csharp/language-reference/keywords/object.md)|`System.Object`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`System.Int16`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`System.UInt16`|  
|[string](../../../csharp/language-reference/keywords/string.md)|`System.String`|  
  
## Заметки  
 Все типы в таблице, за исключением типов `object` и `string`, относятся к простым типам.  
  
 Ключевые слова типов C\# и их псевдонимы являются взаимозаменяемыми.  Например, можно объявить целочисленную переменную при помощи одного из следующих объявлений.  
  
```  
int x = 123;  
System.Int32 x = 123;  
```  
  
 Для отображения фактического типа для любого типа C\# используется системный метод `GetType()`.  Например, следующий оператор отображает системный псевдоним, который представляет тип `myVariable`:  
  
```  
Console.WriteLine(myVariable.GetType());  
```  
  
 Также можно использовать оператор [typeof](../../../csharp/language-reference/keywords/typeof.md).  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Типы значений](../../../csharp/language-reference/keywords/value-types.md)   
 [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md)   
 [Таблица форматирования числовых результатов](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [Справочные таблицы по типам](../../../csharp/language-reference/keywords/reference-tables-for-types.md)