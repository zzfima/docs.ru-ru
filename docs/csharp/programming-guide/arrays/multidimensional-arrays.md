---
title: "Многомерные массивы (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
caps.latest.revision: 16
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
ms.openlocfilehash: 0203046e2038e97cf791141f6863fd8940b22ea4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="multidimensional-arrays-c-programming-guide"></a>Многомерные массивы (Руководство по программированию на C#)
Массивы могут иметь несколько измерений. Например, следующее объявление создает двухмерный массив из четырех строк и двух столбцов.  
  
 [!code-cs[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]  
  
 Следующее объявление создает массив из трех измерений: 4, 2 и 3.  
  
 [!code-cs[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a>Инициализация массива  
 Массив можно инициализировать при объявлении, как показано в следующем примере.  
  
 [!code-cs[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]  
  
 Также можно инициализировать массив без указания ранга.  
  
 [!code-cs[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]  
  
 Чтобы объявить переменную массива без инициализации, используйте оператор `new` для присвоения массива переменной. Использование оператора `new` показано в следующем примере.  
  
 [!code-cs[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]  
  
 В следующем примере присваивается значение конкретному элементу массива.  
  
 [!code-cs[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]  
  
 Аналогичным образом, в следующем примере получается значение конкретного элемента массива, которое присваивается переменной `elementValue`.  
  
 [!code-cs[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]  
  
 В следующем примере кода элементы массива инициализируются с использованием значений по умолчанию (кроме массивов массивов).  
  
 [!code-cs[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Массивы массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md)

