---
title: Справочник по C#. Оператор delegate
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1dd27fe5fdfdc1bc8a63e1298da00d252e800a72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847343"
---
# <a name="delegate-operator-c-reference"></a>Справочник по C#. Оператор delegate

Оператор `delegate` создает анонимный метод, который можно преобразовать в тип делегата:

[!code-csharp-interactive[anonymous method](snippets/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> Начиная с C# 3, лямбда-выражения позволяют быстрее и проще создавать анонимные функции. С помощью [оператора =>](lambda-operator.md) создайте лямбда-выражение:
>
> [!code-csharp-interactive[lambda expression](snippets/DelegateOperator.cs#Lambda)]
>
> См. подробнее о возможностях [лямбда-выражений](../../programming-guide/statements-expressions-operators/lambda-expressions.md) (например, об использовании внешних переменных).

При использовании оператора `delegate` вам, возможно, нужно будет пропустить список параметров. В таком случае созданный анонимный метод можно будет преобразовать в тип делегата с любым списком параметров, как показано в примере ниже:

[!code-csharp-interactive[no parameter list](snippets/DelegateOperator.cs#WithoutParameterList)]

Это единственная функция анонимных методов, которая не поддерживается лямбда-выражениями. Во всех остальных случаях лямбда-выражение является предпочтительным способом написания встроенного кода.

Вы также можете использовать ключевое слово `delegate` для объявления [типа делегата](../builtin-types/reference-types.md#the-delegate-type).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также раздел

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [=> оператор](lambda-operator.md)
