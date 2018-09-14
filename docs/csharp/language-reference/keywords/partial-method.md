---
title: Метод partial (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: f859506ef59f4fc709e9942d86130fc222c14faf
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516373"
---
# <a name="partial-method-c-reference"></a>Метод partial (Справочник по C#)

Сигнатура разделяемого метода определяется в одной части разделяемого типа, а его реализация — в другой части этого типа. С помощью разделяемых методов разработчики классов могут при необходимости реализовывать ловушки методов, которые схожи с обработчиками событий. Если реализация не предоставлена, компилятор удаляет сигнатуру во время компиляции. В отношении разделяемых методов применяются следующие условия:

- Сигнатуры в обеих частях разделяемого типа должны совпадать.

- Метод должен возвращать значение void.

- Модификаторы доступа не допускаются. Разделяемые методы являются неявно частными.

В следующем примере показан разделяемый метод, определенный в двух частях разделяемого класса:

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

Дополнительные сведения см. в разделе [Разделяемые классы и методы](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Тип partial](partial-type.md)