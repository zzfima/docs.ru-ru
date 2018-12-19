---
title: Руководство по программированию на C#. Перегружаемые операторы
ms.custom: seodec18
ms.date: 08/27/2018
helpviewer_keywords:
- C# language, operator overloading
- operator overloading [C#]
ms.assetid: 390d9d01-79fc-40ab-9ed3-0bf448da1b6a
ms.openlocfilehash: b993c7873cdce60ae03e872b842f8265900442fd
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238984"
---
# <a name="overloadable-operators-c-programming-guide"></a>Перегружаемые операторы (руководство по программированию в C#)

C# позволяет пользовательским типам перегружать операторы путем определения статических функций-членов с помощью ключевого слова [operator](../../language-reference/keywords/operator.md). Не все операторы могут быть перегружены; кроме того, некоторые операторы имеют ограничения, как указано в следующей таблице.

| Операторы | Возможность перегрузки |
| --------- | --------------- |
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [!](../../language-reference/operators/logical-negation-operator.md), [~](../../language-reference/operators/bitwise-complement-operator.md), [++](../../language-reference/operators/increment-operator.md), [--](../../language-reference/operators/decrement-operator.md), [true](../../language-reference/keywords/true.md), [false](../../language-reference/keywords/false.md)|Эти унарные операторы могут быть перегружены.|
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [\*](../../language-reference/operators/multiplication-operator.md), [/](../../language-reference/operators/division-operator.md), [%](../../language-reference/operators/modulus-operator.md), [&](../../language-reference/operators/and-operator.md), [&#124;](../../language-reference/operators/or-operator.md), [^](../../language-reference/operators/xor-operator.md), [\<\<](../../language-reference/operators/left-shift-operator.md), [>>](../../language-reference/operators/right-shift-operator.md)|Эти бинарные операторы могут быть перегружены.|
|[==](../../language-reference/operators/equality-comparison-operator.md), [!=](../../language-reference/operators/not-equal-operator.md), [\<](../../language-reference/operators/less-than-operator.md), [>](../../language-reference/operators/greater-than-operator.md), [\<=](../../language-reference/operators/less-than-equal-operator.md), [>=](../../language-reference/operators/greater-than-equal-operator.md)|Операторы сравнения могут быть перегружены (но см. примечание после этой таблицы).|
|[&&](../../language-reference/operators/conditional-and-operator.md), [&#124;&#124;](../../language-reference/operators/conditional-or-operator.md)|Условные логические операторы не могут быть перегружены, но они оцениваются с помощью `&` и <code>&#124;</code>, которые могут быть перегружены.|
|[&#91;&#93;](../../language-reference/operators/index-operator.md)|Оператор индексирования массива не может быть перегружен, но можно определить [индексаторы](../indexers/index.md).|
|[(T)x](../../language-reference/operators/invocation-operator.md)|Оператор приведения типов не может быть перегружен, но можно определить новые операторы преобразования (см. [explicit](../../language-reference/keywords/explicit.md) и [implicit](../../language-reference/keywords/implicit.md)).|
|[+=](../../language-reference/operators/addition-assignment-operator.md), [-=](../../language-reference/operators/subtraction-assignment-operator.md), [\*=](../../language-reference/operators/multiplication-assignment-operator.md), [/=](../../language-reference/operators/division-assignment-operator.md), [%=](../../language-reference/operators/modulus-assignment-operator.md), [&=](../../language-reference/operators/and-assignment-operator.md), [&#124;=](../../language-reference/operators/or-assignment-operator.md), [^=](../../language-reference/operators/xor-assignment-operator.md), [\<\<=](../../language-reference/operators/left-shift-assignment-operator.md), [>>=](../../language-reference/operators/right-shift-assignment-operator.md)|Операторы присваивания не могут быть перегружены явным образом. Однако при перегрузке бинарного оператора соответствующий оператор присваивания (если таковой имеется) также неявно перегружается. Например, `+=` вычисляется с помощью `+`, который может быть перегружен.|
|[=](../../language-reference/operators/assignment-operator.md), [.](../../language-reference/operators/member-access-operator.md), [?:](../../language-reference/operators/conditional-operator.md), [??](../../language-reference/operators/null-coalescing-operator.md), [->](../../language-reference/operators/dereference-operator.md), [=>](../../language-reference/operators/lambda-operator.md), [f(x)](../../language-reference/operators/invocation-operator.md), [as](../../language-reference/keywords/as.md), [checked](../../language-reference/keywords/checked.md), [unchecked](../../language-reference/keywords/unchecked.md), [default](../../programming-guide/statements-expressions-operators/default-value-expressions.md), [delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md), [is](../../language-reference/keywords/is.md), [new](../../language-reference/keywords/new.md), [sizeof](../../language-reference/keywords/sizeof.md), [typeof](../../language-reference/keywords/typeof.md)|Эти операторы не могут быть перегружены.|

> [!NOTE]
> При перегрузке операторов сравнения они должны перегружаться парами; то есть если оператор `==` перегружается, оператор `!=` тоже должен перегружаться. Обратное также верно, если для перегрузки оператора `!=` требуется перегрузка оператора `==`. То же справедливо для операторов сравнения `<` и `>`, а также `<=` и `>=`.

Сведения о перегрузке операторов см. в разделе о ключевом слове [operator](../../language-reference/keywords/operator.md).

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Инструкции, выражения и операторы](index.md)
- [Инструкции](operators.md)
- [Операторы в C#](../../language-reference/operators/index.md)  
- [Почему перегруженные операторы всегда являются статическими в C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/)
