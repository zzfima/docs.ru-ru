---
title: "Практическое руководство. Преобразование массива байтов в значение типа int (Руководство по программированию на C#) | Microsoft Docs"
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
  - "массивы байтов [C#], преобразование в int"
  - "преобразования [C#], массив байтов в int"
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Преобразование массива байтов в значение типа int (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В этом примере демонстрируется использование класса <xref:System.BitConverter> для преобразования массива байтов в значение типа [int](../../../csharp/language-reference/keywords/int.md) и обратно в массив байтов.  Например, может потребоваться преобразование из байтов во встроенный тип данных после чтения байтов из сети.  В дополнение к методу [ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False), показанному в примере, для преобразования байтов \(из массива байтов\) в другие встроенные типы данных могут использоваться и другие методы класса <xref:System.BitConverter>, представленные в следующей таблице.  
  
|Возвращаемый тип|Метод|  
|----------------------|-----------|  
|`bool`|[ToBoolean\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToBoolean(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`char`|[ToChar\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToChar(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`double`|[ToDouble\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToDouble(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`short`|[ToInt16\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt16(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`int`|[ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`long`|[ToInt64\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt64(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`float`|[ToSingle\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToSingle(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`ushort`|[ToUInt16\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToUInt16(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`uint`|[ToUInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToUInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`ulong`|[ToUInt64\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToUInt64(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
  
## Пример  
 Этот пример инициализирует массив байтов, обращает порядок расположения элементов в массиве, если в архитектуре компьютера используется прямой порядок байтов \(т. е. первым сохраняется наименее значащий байт\), и затем вызывает метод [ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False) для преобразования четырех байтов массива в значение типа `int`.  Второй аргумент [ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False) указывает начальный индекс массива байтов.  
  
> [!NOTE]
>  Результат может отличаться в зависимости от порядка следования байтов в архитектуре компьютера.  
  
 [!code-cs[csProgGuideTypes#22](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_1.cs)]  
  
## Пример  
 В этом примере метод <xref:System.BitConverter.GetBytes%28System.Int32%29> класса <xref:System.BitConverter> вызывается для преобразования значения типа `int` в массив байтов.  
  
> [!NOTE]
>  Результат может отличаться в зависимости от порядка следования байтов в архитектуре компьютера.  
  
 [!code-cs[csProgGuideTypes#23](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_2.cs)]  
  
## См. также  
 <xref:System.BitConverter>   
 <xref:System.BitConverter.IsLittleEndian>   
 [Типы](../../../csharp/programming-guide/types/index.md)