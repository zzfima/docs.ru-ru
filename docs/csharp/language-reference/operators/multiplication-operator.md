---
title: '* Справочник по C#. Оператор -'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: a5e120d26614f1e38cc2f2db02949552140b594e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977348"
---
# <a name="-operator-c-reference"></a>Справочник по C#. Оператор *

Оператор `*` поддерживается в двух формах: унарный оператор косвенного обращения к указателю или бинарный оператор умножения.

## <a name="pointer-indirection-operator"></a>Оператор косвенного обращения к указателю

Используйте унарный оператор `*` для получения переменной, на который указывает операнд типа указателя. Дополнительные сведения см. в [практическом руководстве по получению значения переменной указателя](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md).

Для оператора косвенного обращения к указателю `*` требуется контекст [unsafe](../keywords/unsafe.md).

## <a name="multiplication-operator"></a>Оператор умножения

Для числовых типов оператор `*` вычисляет результат двух операндов:

[!code-csharp-interactive[multiplication](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#Multiply)]

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемые пользователем типы могут вызвать [перегрузку](../keywords/operator.md) бинарного оператора `*`. При перегрузке бинарного оператора `*` неявно перегружается и соответствующий [оператор присваивания умножения](multiplication-assignment-operator.md) `*=`.

## <a name="c-language-specification"></a>Спецификация языка C#

См. дополнительные сведения об [операторе косвенного обращения к указателю](~/_csharplang/spec/unsafe-code.md#pointer-indirection) и [операторе умножения](~/_csharplang/spec/expressions.md#multiplication-operator) в [спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Типы указателей](../../programming-guide/unsafe-code-pointers/pointer-types.md)