---
title: "Передача массивов при помощи параметров ref и out (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7f2d4e613491b26e82523d230398af3ec34b4d0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a>Передача массивов при помощи параметров ref и out (Руководство по программированию на C#)
Как и все параметры [out](../../../csharp/language-reference/keywords/out.md), параметр `out` типа массива перед использованием необходимо присвоить, то есть он должен быть присвоен вызываемым объектом. Пример:  
  
 [!code-csharp[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]  
  
 Как и все параметры [ref](../../../csharp/language-reference/keywords/ref.md), параметр `ref` типа массива должен быть явно присвоен вызывающим объектом. Таким образом, явное присвоение вызываемым объектом не требуется. Параметр `ref` типа массива в результате вызова может быть изменен. Например, массиву можно присвоить значение [null](../../../csharp/language-reference/keywords/null.md), или же его можно инициализировать в другой массив. Пример:  
  
 [!code-csharp[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]  
  
 В следующих двух примерах демонстрируются различия между параметрами `out` и `ref` при их использовании для передачи массивов в методы.  
  
## <a name="example"></a>Пример  
 В следующем примере массив `theArray` объявляется в вызывающем объекте (методе `Main`) и инициализируется в методе `FillArray`. Затем элементы массива возвращаются вызывающему объекту и отображаются.  
  
 [!code-csharp[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере массив `theArray` инициализируется в вызывающем объекте (методе `Main`) и передается в метод `FillArray` с помощью параметра `ref`. Некоторые элементы массива в методе `FillArray` обновляются. Затем элементы массива возвращаются вызывающему объекту и отображаются.  
  
 [!code-csharp[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]  
  
## <a name="see-also"></a>См. также  
 [ref](../../../csharp/language-reference/keywords/ref.md)  
 [модификатор параметра out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Массивы](../../../csharp/programming-guide/arrays/index.md)  
 [Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [Массивы массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md)
