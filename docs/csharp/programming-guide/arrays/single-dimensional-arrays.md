---
title: Руководство по программированию на C#. Одномерные массивы
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: 719e4463806c9c7e8b5407f2494c3b548ffa43e8
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200784"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a>Одномерные массивы (Руководство по программированию на C#)

Вы можете объявить одномерный массив, содержащий пять целых чисел, как показано в следующем примере:  
  
 [!code-csharp[csProgGuideArrays#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#4)]  
  
 Этот массив содержит элементы с `array[0]` по `array[4]`. С помощью оператора [new](../../../csharp/language-reference/keywords/new.md) можно создать массив и инициализировать его элементы, используя значения по умолчанию. В этом примере при инициализации всем элементам массива присваиваются нулевые значения.  
  
 Таким же образом можно объявить массив, в котором хранятся строковые элементы. Например:  
  
 [!code-csharp[csProgGuideArrays#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#5)]  
  
## <a name="array-initialization"></a>Инициализация массива

 Массив можно инициализировать при объявлении. В этом случае не требуется спецификатор длины, поскольку он уже задан по числу элементов в списке инициализации. Например:  
  
 [!code-csharp[csProgGuideArrays#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#6)]  
  
 Массив строк можно инициализировать таким же образом. Ниже приведено объявление массива строк, где каждый элемент массива инициализируется с использованием названия дня:  
 
 ```csharp
 string[] weekDays = new string[] { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };
 ```
  
 Если массив инициализируется при объявлении, вы можете использовать следующие сочетания клавиш:  
  
 [!code-csharp[csProgGuideArrays#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#8)]  
  
 Переменную массива можно объявить без инициализации, однако при присвоении массива этой переменной необходимо использовать оператор `new`. Например:  
  
 [!code-csharp[csProgGuideArrays#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#9)]  
  
 В C# 3.0 представлены неявно типизированные массивы. Дополнительные сведения см. в разделе [Неявно типизированные массивы](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## <a name="value-type-and-reference-type-arrays"></a>Массивы типов значений и ссылочных типов

 Рассмотрим следующее объявление массива:  
  
 [!code-csharp[csProgGuideArrays#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#10)]  
  
 Результат этого оператора зависит от того, является ли `SomeType` типом значения или ссылочным типом. Если это тип значения, оператор создает массив из 10 элементов, каждый из которых имеет тип `SomeType`. Если `SomeType` является ссылочным типом, этот оператор создает массив из 10 элементов, каждый из которых инициализируется с использованием ссылки NULL.  
  
 Дополнительные сведения о типах значений и ссылочных типах см. в разделе [Типы](../../../csharp/language-reference/keywords/types.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Array>
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Массивы](../../../csharp/programming-guide/arrays/index.md)
- [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)
- [Массивы массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md)
