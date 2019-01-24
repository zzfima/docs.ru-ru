---
title: 'Справочник по C#. Оператор ::'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 2618131f27271e7c06cb6d425fc22b5bd9750c49
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333321"
---
# <a name="-operator-c-reference"></a>Справочник по C#. Оператор ::

Квалификатор псевдонима пространства имен (`::`) служит для поиска идентификаторов. Он всегда размещается между двумя идентификаторами, как показано в следующем примере.

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

Оператор `::` также может использоваться с *директивой псевдонима using*:

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a>Примечания

Квалификатор псевдонима пространства имен может быть `global`. Он вызывает поиск в глобальном пространстве имен, а не в пространстве имен с псевдонимом.

## <a name="for-more-information"></a>Дополнительные сведения

Пример использования оператора `::` см. в следующем разделе:

- [Практическое руководство. Использование псевдонима глобального пространства имен](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Ключевые слова, используемые для пространств имен](../keywords/namespace-keywords.md)
- [Оператор .](member-access-operator.md)
- [Псевдоним extern](../keywords/extern-alias.md)