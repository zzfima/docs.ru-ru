---
title: Справочник по C#. Оператор default
ms.custom: seodec18
description: Использование оператора default для создания значения по умолчанию для типа
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 5623cb9dc3790b5bb99635c41cb3f122f4c71d8e
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796943"
---
# <a name="default-operator-c-reference"></a>Оператор default (справочник по C#)

Оператор `default` создает значение [по умолчанию](../keywords/default-values-table.md) для типа. Оператор `default` принимает в качестве аргумента имя типа или параметр типа.

В следующем примере показано применение оператора `default`.

[!code-csharp-interactive[default of T](~/samples/csharp/language-reference/operators/DefaultOperator.cs#WithOperand)]

Также используется ключевое слово `default` в качестве метки варианта по умолчанию в [инструкции `switch`](../keywords/switch.md).

## <a name="default-literal"></a>Литерал default

Начиная с C# 7.1, можно использовать литерал `default` для создания значения по умолчанию для типа, если компилятор может вывести тип выражения. Литеральное выражение `default` создает то же значение, что и выражение `default(T)`, где `T` является выведенным типом. Литерал `default` можно использовать в любом из следующих случаев:

- при назначении или инициализации переменной;
- в объявлении значения по умолчанию для необязательного параметра метода;
- в вызове метода для предоставления значения аргумента;
- в инструкции `return` или в качестве выражения в элементе в тексте выражения.

Ниже приведен пример применения литерала `default`.

[!code-csharp-interactive[default literal](~/samples/csharp/language-reference/operators/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе о [выражениях значения по умолчанию](~/_csharplang/spec/expressions.md#default-value-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

Дополнительные сведения о литерале `default` см. в [примечании к предлагаемой функции](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [Таблица значений по умолчанию](../keywords/default-values-table.md)
