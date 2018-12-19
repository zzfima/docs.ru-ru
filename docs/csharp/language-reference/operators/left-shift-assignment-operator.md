---
title: Оператор &lt;&lt;=. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: f49c6360d6fee3f6d612aee51446545f25cd7d18
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239177"
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

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
