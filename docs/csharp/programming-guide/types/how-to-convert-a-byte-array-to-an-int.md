---
title: "Практическое руководство. Преобразование массива байтов в значение типа int (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "массивы байтов [C#], преобразование в int"
  - "преобразования [C#], массив байтов в int"
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Практическое руководство. Преобразование массива байтов в значение типа int (Руководство по программированию на C#)
В этом примере демонстрируется использование класса <xref:System.BitConverter> для преобразования массива байтов в значение типа [int](../../../csharp/language-reference/keywords/int.md) и обратно в массив байтов.  Например, может потребоваться преобразование из байтов во встроенный тип данных после чтения байтов из сети.  В дополнение к методу [ToInt32\(Byte\<xref:System.BitConverter.ToInt32%28System.Byte%5B%5D%2CSystem.Int32%29>, показанному в примере, для преобразования байтов \(из массива байтов\) в другие встроенные типы данных могут использоваться и другие методы класса <xref:System.BitConverter>, представленные в следующей таблице.  
  
|Возвращаемый тип|Метод|  
|----------------------|-----------|  
|`bool`|[ToBoolean\(Byte\<xref:System.BitConverter.ToBoolean%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`char`|[ToChar\(Byte\<xref:System.BitConverter.ToChar%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`double`|[ToDouble\(Byte\<xref:System.BitConverter.ToDouble%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`short`|[ToInt16\(Byte\<xref:System.BitConverter.ToInt16%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`int`|[ToInt32\(Byte\<xref:System.BitConverter.ToInt32%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`long`|[ToInt64\(Byte\<xref:System.BitConverter.ToInt64%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`float`|[ToSingle\(Byte\<xref:System.BitConverter.ToSingle%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`ushort`|[ToUInt16\(Byte\<xref:System.BitConverter.ToUInt16%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`uint`|[ToUInt32\(Byte\<xref:System.BitConverter.ToUInt32%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`ulong`|[ToUInt64\(Byte\<xref:System.BitConverter.ToUInt64%28System.Byte%5B%5D%2CSystem.Int32%29>|  
  
## Пример  
 Этот пример инициализирует массив байтов, обращает порядок расположения элементов в массиве, если в архитектуре компьютера используется прямой порядок байтов \(т. е. первым сохраняется наименее значащий байт\), и затем вызывает метод [ToInt32\(Byte\<xref:System.BitConverter.ToInt32%28System.Byte%5B%5D%2CSystem.Int32%29> для преобразования четырех байтов массива в значение типа `int`.  Второй аргумент [ToInt32\(Byte\<xref:System.BitConverter.ToInt32%28System.Byte%5B%5D%2CSystem.Int32%29> указывает начальный индекс массива байтов.  
  
> [!NOTE]
>  Результат может отличаться в зависимости от порядка следования байтов в архитектуре компьютера.  
  
 [!code-cs[csProgGuideTypes#22](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-a-byte-ar_1.cs)]  
  
## Пример  
 В этом примере метод <xref:System.BitConverter.GetBytes%28System.Int32%29> класса <xref:System.BitConverter> вызывается для преобразования значения типа `int` в массив байтов.  
  
> [!NOTE]
>  Результат может отличаться в зависимости от порядка следования байтов в архитектуре компьютера.  
  
 [!code-cs[csProgGuideTypes#23](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-a-byte-ar_2.cs)]  
  
## См. также  
 <xref:System.BitConverter>   
 <xref:System.BitConverter.IsLittleEndian>   
 [Типы](../../../csharp/programming-guide/types/index.md)