---
title: Руководство по программированию на C#. Массивы как объекты
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: 0c4b5dcbd9e227e4edd5f549b687e3ded90ee9bc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740493"
---
# <a name="arrays-as-objects-c-programming-guide"></a>Массивы как объекты (Руководство по программированию на C#)

В C# массивы представляют собой реальные объекты, а не просто адресуемые области непрерывной памяти, как в C и C++. <xref:System.Array> — это абстрактный базовый тип для всех типов массивов. Вы можете использовать свойства и другие члены класса, входящие в <xref:System.Array>. Например, с помощью свойства <xref:System.Array.Length%2A> можно получить длину массива. В следующем коде значение длины массива `numbers` (`5`) присваивается переменной с именем `lengthOfNumbers`:  
  
 [!code-csharp[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]  
  
 В классе <xref:System.Array> представлено множество других полезных методов и свойств для сортировки, поиска и копирования массивов.  
  
## <a name="example"></a>Пример

 В этом примере используется свойство <xref:System.Array.Rank%2A>, позволяющее отобразить число измерений массива.  
  
 [!code-csharp[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Массивы](../../../csharp/programming-guide/arrays/index.md)
- [Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)
- [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)
- [Массивы массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md)
