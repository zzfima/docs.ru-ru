---
title: "Оператор ^= (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ^=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
caps.latest.revision: 16
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
ms.openlocfilehash: 33b0dccf5031809bb4fcb73d0f7d6a344accdea3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Оператор ^= (справочник по C#)
Оператор присваивания исключающего ИЛИ.  
  
## <a name="remarks"></a>Примечания  
 Выражение в формате  
  
```  
x ^= y  
```  
  
 вычисляется как  
  
```  
x = x ^ y  
```  
  
 за исключением того, что `x` вычисляется только один раз. [Оператор ^](../../../csharp/language-reference/operators/xor-operator.md) выполняет побитовую операцию исключающего ИЛИ в отношении целочисленных операндов и логическую операцию исключающего ИЛИ в отношении операндов типа [bool](../../../csharp/language-reference/keywords/bool.md).  
  
 Оператор ^= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор ^](../../../csharp/language-reference/operators/xor-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Пример  
 [!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)

