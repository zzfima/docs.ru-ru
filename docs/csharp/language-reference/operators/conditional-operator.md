---
title: 'Оператор ?: (справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 1bfbe5257123438751592695f23fe24aeb7ccc2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>Оператор ?: (справочник по C#)
Условный оператор (`?:`), известный как тернарный условный оператор, возвращает одно из двух значений в зависимости от значения логического выражения. Для условного оператора используется следующий синтаксис.  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр `condition` должен иметь значение `true` или `false`. Если параметр `condition` имеет значение `true`, вычисляется выражение `first_expression` и итог этого вычисления становится результатом. Если параметр `condition` имеет значение `false`, вычисляется выражение `second_expression` и итог этого вычисления становится результатом. В любом случае вычисляется только одно из двух выражений.  
  
 Параметры `first_expression` и `second_expression` должны быть одинакового типа или должно существовать неявное преобразование из одного типа в другой.  
  
 Расчеты, которые в другом случае требовали бы уточнения конструкции `if-else`, можно выражать с помощью условного оператора. Например, в следующем коде сначала используется оператор `if`, а затем — условный оператор для классификации целого числа как положительного или отрицательного.  
  
```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```  
  
 Условный оператор имеет правую ассоциативность. Выражение `a ? b : c ? d : e` вычисляется как `a ? b : (c ? d : e)`, а не как `(a ? b : c) ? d : e`.  
  
 Условный оператор не может быть перегружен.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)  
 [if-else](../../../csharp/language-reference/keywords/if-else.md)  
 [Операторы ?. и ?](../../../csharp/language-reference/operators/null-conditional-operators.md)  
 [?? Оператор](../../../csharp/language-reference/operators/null-conditional-operator.md)
