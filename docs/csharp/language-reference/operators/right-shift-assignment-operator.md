---
title: "Оператор &gt;&gt;= (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>>=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 64f387e475681ffc76f113435ba090b40780dda3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="gtgt-operator-c-reference"></a>Оператор &gt;&gt;= (справочник по C#)
Оператор присваивания сдвига вправо.  
  
## <a name="remarks"></a>Примечания  
 Выражение в формате  
  
```  
x >>= y  
```  
  
 вычисляется как  
  
```  
x = x >> y  
```  
  
 за исключением того, что `x` вычисляется только один раз. [Оператор >>](../../../csharp/language-reference/operators/right-shift-operator.md) сдвигает `x` вправо на величину, указанную в `y`.  
  
 Оператор >>= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор >>](../../../csharp/language-reference/operators/right-shift-operator.md) (см. [оператор](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Пример  
 [!code-cs[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)

