---
title: Оператор ::. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: c494e8dbb18f44ce5520b21800a21d3feb03da59
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025075"
---
# <a name="-operator-c-reference"></a>Оператор :: (справочник по C#)

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

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [Оператор .](member-access-operators.md#member-access-operator-)
- [Псевдоним extern](../keywords/extern-alias.md)
