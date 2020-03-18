---
title: Руководство по программированию на C#. Массивы как объекты
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: d8b929eccf9be259874d03dd93f49a49798bb349
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715090"
---
# <a name="arrays-as-objects-c-programming-guide"></a>Массивы как объекты (Руководство по программированию на C#)

В C# массивы представляют собой реальные объекты, а не просто адресуемые области непрерывной памяти, как в C и C++. <xref:System.Array> — это абстрактный базовый тип для всех типов массивов. Вы можете использовать свойства и другие члены класса, входящие в <xref:System.Array>. Например, с помощью свойства <xref:System.Array.Length%2A> можно получить длину массива. В следующем коде значение длины массива `numbers` (`5`) присваивается переменной с именем `lengthOfNumbers`:

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

В классе <xref:System.Array> представлено множество других полезных методов и свойств для сортировки, поиска и копирования массивов.

## <a name="example"></a>Пример

В этом примере используется свойство <xref:System.Array.Rank%2A>, позволяющее отобразить число измерений массива.

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a>См. также раздел

- [Руководство по программированию на C#](../index.md)
- [Массивы](./index.md)
- [Одномерные массивы](./single-dimensional-arrays.md)
- [Многомерные массивы](./multidimensional-arrays.md)
- [Массивы массивов](./jagged-arrays.md)
