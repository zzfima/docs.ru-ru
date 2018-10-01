---
title: Одномерные массивы (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: c2f26fd74a596ada21eef578e58c9cd8e0305d6c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2018
ms.locfileid: "47399389"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a>Одномерные массивы (Руководство по программированию на C#)

Вы можете объявить одномерный массив, содержащий пять целых чисел, как показано в следующем примере:  
  
 [!code-csharp[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]  
  
 Этот массив содержит элементы с `array[0]` по `array[4]`. С помощью оператора [new](../../../csharp/language-reference/keywords/new.md) можно создать массив и инициализировать его элементы, используя значения по умолчанию. В этом примере при инициализации всем элементам массива присваиваются нулевые значения.  
  
 Таким же образом можно объявить массив, в котором хранятся строковые элементы. Пример:  
  
 [!code-csharp[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a>Инициализация массива

 Массив можно инициализировать при объявлении. В этом случае не требуется спецификатор ранга, поскольку он уже задается по числу элементов в списке инициализации. Пример:  
  
 [!code-csharp[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]  
  
 Массив строк можно инициализировать таким же образом. Ниже приведено объявление массива строк, где каждый элемент массива инициализируется с использованием названия дня:  
  
 [!code-csharp[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]  
  
 Если массив инициализируется при объявлении, вы можете использовать следующие сочетания клавиш:  
  
 [!code-csharp[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]  
  
 Переменную массива можно объявить без инициализации, однако при присвоении массива этой переменной необходимо использовать оператор `new`. Пример:  
  
 [!code-csharp[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]  
  
 В C# 3.0 представлены неявно типизированные массивы. Дополнительные сведения см. в разделе [Неявно типизированные массивы](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## <a name="value-type-and-reference-type-arrays"></a>Массивы типов значений и ссылочных типов

 Рассмотрим следующее объявление массива:  
  
 [!code-csharp[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]  
  
 Результат этого оператора зависит от того, является ли `SomeType` типом значения или ссылочным типом. Если это тип значения, оператор создает массив из 10 элементов, каждый из которых имеет тип `SomeType`. Если `SomeType` является ссылочным типом, этот оператор создает массив из 10 элементов, каждый из которых инициализируется с использованием ссылки NULL.  
  
 Дополнительные сведения о типах значений и ссылочных типах см. в разделе [Типы](../../../csharp/language-reference/keywords/types.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Array>  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Массивы](../../../csharp/programming-guide/arrays/index.md)  
- [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
- [Массивы массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md)
