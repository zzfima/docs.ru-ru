---
title: "Массивы массивов (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cb6c0823af37924235dba7daa20e607cb8402a79
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="jagged-arrays-c-programming-guide"></a>Массивы массивов (Руководство по программированию на C#)
Массив массивов — это массив, элементы которого сами являются массивами. Элементы массива массивов могут иметь различные измерения и размеры. Массив массивов иногда называется нерегулярным массивом. В следующих примерах показано, как объявлять и инициализировать массивы массивов, а также получать доступ к ним.  
  
 Ниже объявляется одномерный массив из трех элементов, каждый из которых является одномерным массивом целых чисел:  
  
 [!code-cs[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]  
  
 Прежде чем использовать `jaggedArray`, его элементы необходимо инициализировать. Это можно сделать следующим образом:  
  
 [!code-cs[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]  
  
 Каждый элемент представляет собой одномерный массив целых чисел. Первый из них содержит 5 целых чисел, второй — 4, а третий — 2.  
  
 Кроме того, с помощью инициализаторов можно заполнять элементы массива значениями (при этом вам не потребуется знать размер массива). Пример:  
  
 [!code-cs[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]  
  
 Также массив можно инициализировать при объявлении, как показано ниже:  
  
 [!code-cs[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]  
  
 Можно использовать следующую краткую форму. Обратите внимание, что при инициализации элементов нельзя опускать оператор `new`, поскольку механизм инициализации по умолчанию для них не предусмотрен:  
  
 [!code-cs[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]  
  
 В массиве массивов элементы являются ссылочными типами и инициализируются значением `null`.  
  
 Доступ к отдельным элементам массива можно получить способами, показанными в следующих примерах:  
  
 [!code-cs[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]  
  
 Массивы массивов и многомерные массивы можно смешивать. Ниже показаны объявление и инициализация одномерного массива массивов, элементами которого являются двухмерные массивы разного размера. Дополнительные сведения о двумерных массивах см. в разделе [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).  
  
 [!code-cs[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]  
  
 В этом примере демонстрируется доступ к отдельным элементам, для чего отображается значение элемента `[1,0]` первого массива (`5`):  
  
 [!code-cs[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]  
  
 Метод `Length` возвращает число массивов, содержащихся в массиве массивов. Допустим, предыдущий массив был объявлен с использованием следующей строки:  
  
 [!code-cs[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]  
  
 возвращает значение 3.  
  
## <a name="example"></a>Пример  
 В этом примере создается массив, элементы которого являются массивами. Все элементы массива имеют разный размер.  
  
 [!code-cs[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Array>   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)

