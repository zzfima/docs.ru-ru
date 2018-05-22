---
title: Оператор &lt;&lt;= (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: e5f3886670baa34b0360501ee15280b93fac36bc
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
---
# <a name="ltlt-operator-c-reference"></a>Оператор &lt;&lt;= (справочник по C#)
Оператор присваивания сдвига влево.  
  
## <a name="remarks"></a>Примечания  
 Выражение в формате  
  
```csharp  
x <<= y  
```  
  
 вычисляется как  
  
```csharp  
x = x << y  
```  
  
 за исключением того, что `x` вычисляется только один раз. [Оператор <<](../../../csharp/language-reference/operators/left-shift-operator.md) сдвигает `x` влево на число битов, заданное в `y`.  
  
 Оператор `<<=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор <<](../../../csharp/language-reference/operators/left-shift-operator.md) (см. [оператор](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
