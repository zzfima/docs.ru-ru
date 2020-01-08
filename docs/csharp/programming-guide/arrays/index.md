---
title: Руководство по программированию на C#. Массивы
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: bbabc84c144e5b3415c19f346b890782e251662c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715053"
---
# <a name="arrays-c-programming-guide"></a>Массивы (Руководство по программированию на C#)

В структуре данных массива можно хранить несколько переменных одного типа. Чтобы объявить массив, следует указать тип его элементов. Если требуется, чтобы массив мог хранить элементы любого типа, можно указать `object` в качестве его типа. В унифицированной системе типов C# все типы, стандартные и определяемые пользователем, ссылочные типы и типы значений напрямую или косвенно наследуются из <xref:System.Object>.

```csharp
type[] arrayName;
```

## <a name="example"></a>Пример

В следующих примерах создаются одномерные массивы, многомерные массивы и массивы массивов:

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a>Общие сведения о массивах

Массив имеет следующие свойства:

- Массив может быть [одномерным](single-dimensional-arrays.md), [многомерным](multidimensional-arrays.md) или [массивом массивов](jagged-arrays.md).
- Количество измерений и длина каждого из измерений задаются, когда создается экземпляр массива. Эти значения нельзя изменить во время существования экземпляра.
- Используемые по умолчанию значения числовых элементов массива равны нулю, и элементам ссылки присвоено значение NULL.
- В массиве массивов элементы являются ссылочными типами и инициализируются значением `null`.
- Массивы индексируются от нуля: массив с `n` элементами индексируется от `0` до `n-1`.
- Элементы массива могут иметь любой тип, в том числе тип массива.
- Типы массивов — это [ссылочные типы](../../language-reference/keywords/reference-types.md), производные от абстрактного базового типа <xref:System.Array>. Поскольку этот тип реализует <xref:System.Collections.IEnumerable> и <xref:System.Collections.Generic.IEnumerable%601>, вы можете просматривать в цикле [foreach](../../language-reference/keywords/foreach-in.md) любые массивы C#.

## <a name="related-sections"></a>Связанные разделы

- [Массивы как объекты](arrays-as-objects.md)
- [Использование оператора foreach с массивами](using-foreach-with-arrays.md)
- [Передача массивов в качестве аргументов](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Коллекции](../concepts/collections.md)
