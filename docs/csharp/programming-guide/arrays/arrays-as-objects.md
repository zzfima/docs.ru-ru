---
title: Массивы как объекты (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: f1abe10839c30d48f56ac6044d75d290a59b4cce
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505563"
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
