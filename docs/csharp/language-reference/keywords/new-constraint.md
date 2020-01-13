---
title: Ограничение new. Справочник по C#
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: cd67aeb82d736b8941b0637494089723e7815505
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713356"
---
# <a name="new-constraint-c-reference"></a>Ограничение new (справочник по C#)

Ограничение `new` указывает, что аргумент типа в объявлении универсального класса должен иметь открытый конструктор без параметров. Использовать ограничение `new` можно только в том случае, если тип не является абстрактным.

Примените ограничение `new` к параметру типа, когда общий класс создает новые экземпляры этого типа, как показано в следующем примере:

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

При использовании ограничения `new()` с другими ограничениями его необходимо указывать последним:

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

Дополнительные сведения см. в разделе [Ограничения параметров типа](../../programming-guide/generics/constraints-on-type-parameters.md).

Ключевое слово `new` можно также использовать для [создания экземпляра типа](../operators/new-operator.md) или как [модификатор объявления члена](new-modifier.md).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Ограничения параметров типа](~/_csharplang/spec/classes.md#type-parameter-constraints) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../../language-reference/index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Универсальные шаблоны](../../programming-guide/generics/index.md)
