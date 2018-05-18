---
title: Оператор &lt;&lt;= (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: 9e2dbf693f7bee16c2ce97ccc7d52a318b8a3906
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ltlt-operator-c-reference"></a>Оператор &lt;&lt;= (справочник по C#)
Оператор присваивания сдвига влево.  
  
## <a name="remarks"></a>Примечания  
 Выражение в формате  
  
```  
x <<= y  
```  
  
 вычисляется как  
  
```  
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
