---
title: Справочник по C#. Оператор delegate
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 9a78faaccffa9e7d4bf2829d8dfa0fa62a788bba
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039041"
---
# <a name="delegate-operator-c-reference"></a>Справочник по C#. Оператор delegate

Оператор `delegate` создает анонимный метод, который можно преобразовать в тип делегата:

[!code-csharp-interactive[anonymous method](~/samples/csharp/language-reference/operators/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> Начиная с C# 3, лямбда-выражения позволяют быстрее и проще создавать анонимные функции. С помощью [оператора =>](lambda-operator.md) создайте лямбда-выражение:
>
> [!code-csharp-interactive[lambda expression](~/samples/csharp/language-reference/operators/DelegateOperator.cs#Lambda)]
>
> См. подробнее о возможностях [лямбда-выражений](../../programming-guide/statements-expressions-operators/lambda-expressions.md) (например, об использовании внешних переменных).

При использовании оператора `delegate` вам, возможно, нужно будет пропустить список параметров. В таком случае созданный анонимный метод можно будет преобразовать в тип делегата с любым списком параметров, как показано в примере ниже:

[!code-csharp-interactive[no parameter list](~/samples/csharp/language-reference/operators/DelegateOperator.cs#WithoutParameterList)]

Это единственная функция анонимных методов, которая не поддерживается лямбда-выражениями. Во всех остальных случаях лямбда-выражение является предпочтительным способом написания встроенного кода.

Вы также можете использовать ключевое слово `delegate` для объявления [типа делегата](../builtin-types/reference-types.md#the-delegate-type).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [=> оператор](lambda-operator.md)
