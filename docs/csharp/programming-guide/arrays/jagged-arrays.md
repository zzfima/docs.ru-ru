---
title: Руководство по программированию на C#. Массивы массивов
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 9fc05c8bdebf9c1c6b613db0b6a121e06765ac00
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200680"
---
# <a name="jagged-arrays-c-programming-guide"></a>Массивы массивов (Руководство по программированию на C#)

Массив массивов — это массив, элементы которого сами являются массивами. Элементы массива массивов могут иметь различные измерения и размеры. Массив массивов иногда называется нерегулярным массивом. В следующих примерах показано, как объявлять и инициализировать массивы массивов, а также получать доступ к ним.  
  
 Ниже объявляется одномерный массив из трех элементов, каждый из которых является одномерным массивом целых чисел:  
  
 [!code-csharp[csProgGuideArrays#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#19)]  
  
 Прежде чем использовать `jaggedArray`, его элементы необходимо инициализировать. Это можно сделать следующим образом:  
  
 [!code-csharp[csProgGuideArrays#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#20)]  
  
 Каждый элемент представляет собой одномерный массив целых чисел. Первый из них содержит 5 целых чисел, второй — 4, а третий — 2.  
  
 Кроме того, с помощью инициализаторов можно заполнять элементы массива значениями (при этом вам не потребуется знать размер массива). Например:  
  
 [!code-csharp[csProgGuideArrays#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#21)]  
  
 Также массив можно инициализировать при объявлении, как показано ниже:  
  
 [!code-csharp[csProgGuideArrays#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#22)]  
  
 Можно использовать следующую краткую форму. Обратите внимание, что при инициализации элементов нельзя опускать оператор `new`, поскольку механизм инициализации по умолчанию для них не предусмотрен:  
  
 [!code-csharp[csProgGuideArrays#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#23)]  
  
 В массиве массивов элементы являются ссылочными типами и инициализируются значением `null`.  
  
 Доступ к отдельным элементам массива можно получить способами, показанными в следующих примерах:  
  
 [!code-csharp[csProgGuideArrays#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#24)]  
  
 Массивы массивов и многомерные массивы можно смешивать. Ниже показаны объявление и инициализация одномерного массива массивов, элементами которого являются двухмерные массивы разного размера. Дополнительные сведения о двумерных массивах см. в разделе [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).  
  
 [!code-csharp[csProgGuideArrays#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#25)]  
  
 В этом примере демонстрируется доступ к отдельным элементам, для чего отображается значение элемента `[1,0]` первого массива (`5`):  
  
 [!code-csharp[csProgGuideArrays#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#26)]  
  
 Метод `Length` возвращает число массивов, содержащихся в массиве массивов. Допустим, предыдущий массив был объявлен с использованием следующей строки:  
  
 [!code-csharp[csProgGuideArrays#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#27)]  
  
 возвращает значение 3.  
  
## <a name="example"></a>Пример

 В этом примере создается массив, элементы которого являются массивами. Все элементы массива имеют разный размер.  
  
 [!code-csharp[csProgGuideArrays#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#18)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Array>
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Массивы](../../../csharp/programming-guide/arrays/index.md)
- [Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)
- [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)
