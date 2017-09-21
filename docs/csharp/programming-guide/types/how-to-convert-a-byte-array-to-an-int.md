---
title: "Практическое руководство. Преобразование массива байтов в значение типа int (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], byte array to int
- byte arrays [C#], converting to int
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 86ecfe95ab6fb5ce60e7568050cdf974d0dc3d88
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-a-byte-array-to-an-int-c-programming-guide"></a>Практическое руководство. Преобразование массива байтов в значение типа int (Руководство по программированию на C#)
В этом примере демонстрируется использование класса <xref:System.BitConverter> для преобразования массива байтов в значение типа [int](../../../csharp/language-reference/keywords/int.md) и обратно в массив байтов. Например, может потребоваться преобразование из байтов во встроенный тип данных после чтения байтов из сети. В дополнение к методу [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)), показанному в примере, для преобразования байтов (из массива байтов) в другие встроенные типы данных можно использовать и другие методы класса <xref:System.BitConverter>, представленные в таблице ниже.  
  
|Возвращаемый тип|Метод|  
|-------------------|------------|  
|`bool`|[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))|  
|`char`|[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))|  
|`double`|[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))|  
|`short`|[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))|  
|`int`|[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))|  
|`long`|[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))|  
|`float`|[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))|  
|`ushort`|[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))|  
|`uint`|[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))|  
|`ulong`|[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))|  
  
## <a name="example"></a>Пример  
 Этот пример инициализирует массив байтов, обращает порядок расположения элементов в массиве, если в архитектуре компьютера используется прямой порядок байтов (т. е. первым сохраняется наименее значащий байт), и затем вызывает метод [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) для преобразования четырех байтов массива в значение типа `int`. Второй аргумент [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) указывает начальный индекс массива байтов.  
  
> [!NOTE]
>  Результат может отличаться в зависимости от порядка следования байтов в архитектуре компьютера.  
  
 [!code-cs[csProgGuideTypes#22](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_1.cs)]  
  
## <a name="example"></a>Пример  
 В этом примере вызывается метод <xref:System.BitConverter.GetBytes%28System.Int32%29> класса <xref:System.BitConverter> для преобразования значения `int` в массив байтов.  
  
> [!NOTE]
>  Результат может отличаться в зависимости от порядка следования байтов в архитектуре компьютера.  
  
 [!code-cs[csProgGuideTypes#23](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_2.cs)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.BitConverter>   
 <xref:System.BitConverter.IsLittleEndian>   
 [Типы](../../../csharp/programming-guide/types/index.md)

