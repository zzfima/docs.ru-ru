---
title: Руководство по программированию на C#. Массивы массивов
ms.date: 07/20/2015
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 56013f0143d5efcb31a476909cb6e92504ff0dbc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705708"
---
# <a name="jagged-arrays-c-programming-guide"></a>Массивы массивов (Руководство по программированию на C#)

Массив массивов — это массив, элементы которого сами являются массивами. Элементы массива массивов могут иметь различные измерения и размеры. Массив массивов иногда называется нерегулярным массивом. В следующих примерах показано, как объявлять и инициализировать массивы массивов, а также получать доступ к ним.  
  
 Ниже объявляется одномерный массив из трех элементов, каждый из которых является одномерным массивом целых чисел:  
  
 [!code-csharp[csProgGuideArrays#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#19)]  
  
 Прежде чем использовать `jaggedArray`, его элементы необходимо инициализировать. Это можно сделать следующим образом:  
  
 [!code-csharp[csProgGuideArrays#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#20)]  
  
 Каждый элемент представляет собой одномерный массив целых чисел. Первый из них содержит 5 целых чисел, второй — 4, а третий — 2.  
  
 Кроме того, с помощью инициализаторов можно заполнять элементы массива значениями (при этом вам не потребуется знать размер массива). Пример:  
  
 [!code-csharp[csProgGuideArrays#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#21)]  
  
 Также массив можно инициализировать при объявлении, как показано ниже:  
  
 [!code-csharp[csProgGuideArrays#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#22)]  
  
 Можно использовать следующую краткую форму. Обратите внимание, что при инициализации элементов нельзя опускать оператор `new`, поскольку механизм инициализации по умолчанию для них не предусмотрен:  
  
 [!code-csharp[csProgGuideArrays#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#23)]  
  
 В массиве массивов элементы являются ссылочными типами и инициализируются значением `null`.  
  
 Доступ к отдельным элементам массива можно получить способами, показанными в следующих примерах:  
  
 [!code-csharp[csProgGuideArrays#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#24)]  
  
 Массивы массивов и многомерные массивы можно смешивать. Ниже показаны объявление и инициализация одномерного массива массивов, элементами которого являются двухмерные массивы разного размера. Дополнительные сведения о двумерных массивах см. в разделе [Многомерные массивы](./multidimensional-arrays.md).  
  
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
- [Руководство по программированию на C#](../index.md)
- [Массивы](./index.md)
- [Одномерные массивы](./single-dimensional-arrays.md)
- [Многомерные массивы](./multidimensional-arrays.md)
