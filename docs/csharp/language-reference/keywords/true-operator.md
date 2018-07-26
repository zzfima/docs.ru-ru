---
title: Оператор true (Справочник по C#)
ms.date: 07/20/2015
helpviewer_keywords:
- true operator [C#]
ms.assetid: acaba817-5da5-4364-b3b2-2e5c75ec1839
ms.openlocfilehash: 71f522b3860f7461f5c52dd77bb424f7ba0f9bf5
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37960120"
---
# <a name="true-operator-c-reference"></a>Оператор true (Справочник по C#)
Возвращает [логическое](../../../csharp/language-reference/keywords/bool.md) значение `true`, чтобы указать, что операнд имеет значение true, и возвращает значение `false` в противном случае.  
  
 До версии C# 2.0 операторы `true` и `false` использовались для создания пользовательских типов значений, допускающих значение NULL, которые были совместимы с такими типами, как `SqlBool`. Однако теперь язык предоставляет встроенную поддержку для типов, допускающих значение NULL, и по возможности следует использовать их вместо перегрузки операторов `true` и `false`. Дополнительные сведения см. в разделе [Типы, допускающие значение NULL](../../../csharp/programming-guide/nullable-types/index.md).  
  
 С логическими значениями, допускающими значение NULL, выражение `a != b` не обязательно равно `!(a == b)`, так как одно или оба значений могут иметь значение NULL. Необходимо перегрузить оба оператора `true` и `false` отдельно, чтобы правильно определить значения NULL в выражении. В следующем примере демонстрируется перегрузка и использование операторов `true` и `false`.  
  
 [!code-csharp[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/true-operator_1.cs)]  
  
 Тип, который перегружает операторы `true` и `false`, может использоваться для выражений управления в операторах [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) и [for](../../../csharp/language-reference/keywords/for.md) и в [условных выражениях](../../../csharp/language-reference/operators/conditional-operator.md).  
  
 Если тип определяет оператор `true`, он должен также определять оператор [false](../../../csharp/language-reference/keywords/false.md).  
  
 Тип не может непосредственно перегрузить условные логические операторы ([&&](../../../csharp/language-reference/operators/conditional-and-operator.md) и [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)), однако такой же результат может быть достигнут путем перегрузки обычных логических операторов и операторов `true` и `false`.  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)  
 [false](../../../csharp/language-reference/keywords/false.md)
