---
title: Оператор false (справочник по C#)
ms.date: 07/20/2015
helpviewer_keywords:
- false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: e73113bd37dbb68590267141ad037f78919520bc
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2018
ms.locfileid: "46578730"
---
# <a name="false-operator-c-reference"></a>Оператор false (справочник по C#)

Возвращает [логическое](bool.md) значение `true`, чтобы указать, что операнд является `false`, и возвращает значение `false` в противном случае.

До версии C# 2.0 операторы `true` и `false` использовались для создания пользовательских типов значений, допускающих значение NULL, которые были совместимы с такими типами, как `SqlBool`. Однако теперь язык предоставляет встроенную поддержку для типов, допускающих значение NULL, и по возможности следует использовать их вместо перегрузки операторов `true` и `false`. Дополнительные сведения см. в разделе [Типы, допускающие значение NULL](../../programming-guide/nullable-types/index.md).

С логическими значениями, допускающими значение NULL, выражение `a != b` не обязательно равно `!(a == b)`, так как одно или оба значений могут иметь значение NULL. Необходимо перегрузить оба оператора `true` и `false` отдельно, чтобы правильно обработать значения NULL в выражении. В следующем примере демонстрируется перегрузка и использование операторов `true` и `false`.

[!code-csharp[csrefKeywordsOperator#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#16)]

Тип, который перегружает операторы `true` и `false`, может использоваться для выражений управления в операторах [if](if-else.md), [do](do.md), [while](while.md) и [for](for.md) и в [условных выражениях](../operators/conditional-operator.md).

Если тип определяет оператор `false`, он должен также определять оператор [true](true.md).

Тип не может непосредственно перегрузить условные логические операторы [&&](../operators/conditional-and-operator.md) и [||](../operators/conditional-or-operator.md), однако такой же результат может быть достигнут путем перегрузки обычных логических операторов и операторов `true` и `false`.

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)  
- [Руководство по программированию на C#](../../programming-guide/index.md)  
- [Ключевые слова в C#](index.md)  
- [Операторы в C#](../operators/index.md)  
- [true](true.md)  