---
title: Руководство по программированию на C#. Массивы как объекты
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: fd4496e0f84953204ad8c3f40db699e911c3f477
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597364"
---
# <a name="arrays-as-objects-c-programming-guide"></a>Массивы как объекты (Руководство по программированию на C#)

В C# массивы представляют собой реальные объекты, а не просто адресуемые области непрерывной памяти, как в C и C++. <xref:System.Array> — это абстрактный базовый тип для всех типов массивов. Вы можете использовать свойства и другие члены класса, входящие в <xref:System.Array>. Например, с помощью свойства <xref:System.Array.Length%2A> можно получить длину массива. В следующем коде значение длины массива `numbers` (`5`) присваивается переменной с именем `lengthOfNumbers`:  
  
 [!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]  
  
 В классе <xref:System.Array> представлено множество других полезных методов и свойств для сортировки, поиска и копирования массивов.  
  
## <a name="example"></a>Пример

 В этом примере используется свойство <xref:System.Array.Rank%2A>, позволяющее отобразить число измерений массива.  
  
 [!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Массивы](./index.md)
- [Одномерные массивы](./single-dimensional-arrays.md)
- [Многомерные массивы](./multidimensional-arrays.md)
- [Массивы массивов](./jagged-arrays.md)
