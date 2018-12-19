---
title: delegate. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
ms.openlocfilehash: 233b0255121cf6e7a5283041d594e2d843f105fb
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286472"
---
# <a name="delegate-c-reference"></a>delegate (Справочник по C#)

Объявление типа делегата аналогично сигнатуре метода. Оно имеет возвращаемое значение и любое число параметров любого типа:

```csharp
public delegate void TestDelegate(string message);
public delegate int TestDelegate(MyType m, long num);
```

Ключевое слово `delegate` имеет ссылочный тип, который можно использовать для инкапсуляции именованного или анонимного метода. Делегаты аналогичны используемым в языке C++ указателям функций, но являются типобезопасными и безопасными. Сведения о применении делегатов см. в разделах [Делегаты](../../../csharp/programming-guide/delegates/index.md) и [Универсальные делегаты](../../../csharp/programming-guide/generics/generic-delegates.md).

## <a name="remarks"></a>Примечания

Делегаты являются основой [событий](../../../csharp/programming-guide/events/index.md).

Экземпляры делегата могут создаваться путем его связывания с именованным или анонимным методом. Дополнительные сведения см. в разделах [Именованные методы](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) и [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).

Делегат должен быть создан при помощи метода или лямбда-выражения, имеющего совместимые возвращаемый тип и входные параметры. Дополнительные сведения о допустимой степени вариации сигнатур методов см. в разделе [Вариативность в делегатах](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md). Для использования с анонимными методами делегат и код, который должен быть связан с ним, должны быть объявлены вместе. В этом разделе рассматриваются оба способа создания экземпляров делегатов.

## <a name="example"></a>Пример

[!code-csharp[csrefKeywordsTypes#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#8)]

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
- [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)  
- [Делегаты](../../../csharp/programming-guide/delegates/index.md)  
- [События](../../../csharp/programming-guide/events/index.md)  
- [Делегаты с именованными методами и делегаты с анонимными методами](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) 
- [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
- [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
