---
title: "Оператор ? (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3e60516d1f443528c357eb12612b6149f34c1f7e
ms.lasthandoff: 03/13/2017

---
# <a name="-operator-c-reference"></a>Оператор ?: (справочник по C#)
Условный оператор (`?:`) возвращает одно из двух значений в зависимости от значения логического выражения. Для условного оператора используется следующий синтаксис.  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр `condition` должен иметь значение `true` или `false`. Если параметр `condition` имеет значение `true`, вычисляется выражение `first_expression` и итог этого вычисления становится результатом. Если параметр `condition` имеет значение `false`, вычисляется выражение `second_expression` и итог этого вычисления становится результатом. В любом случае вычисляется только одно из двух выражений.  
  
 Параметры `first_expression` и `second_expression` должны быть одинакового типа или должно существовать неявное преобразование из одного типа в другой.  
  
 Расчеты, которые в другом случае требовали бы уточнения конструкции `if-else`, можно выражать с помощью условного оператора. Например, в следующем коде сначала используется оператор `if`, а затем — условный оператор для классификации целого числа как положительного или отрицательного.  
  
```  
  
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
 [!code-cs[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)   
 [if-else](../../../csharp/language-reference/keywords/if-else.md)   
 [Операторы ?. и ?](../../../csharp/language-reference/operators/null-conditional-operators.md)   
 [?? Оператор](../../../csharp/language-reference/operators/null-conditional-operator.md)
