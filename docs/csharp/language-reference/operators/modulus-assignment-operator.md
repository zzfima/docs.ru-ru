---
title: "Оператор %= (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- modulus assignment operator (=%) [C#]
- '%= assignment operator (modulus assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
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
ms.openlocfilehash: 48484a0593102c92304803e5c0697501b0e26e0e
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Оператор %= (Справочник по C#)
Оператор присваивания остатка.  
  
## <a name="remarks"></a>Примечания  
 Выражение, использующее оператор присваивания `%=`, такое как  
  
```  
x %= y  
```  
  
 эквивалентно  
  
```  
x = x % y  
```  
  
 за исключением того, что `x` вычисляется только один раз. В числовых типах предварительно определенный [оператор %](../../../csharp/language-reference/operators/modulus-operator.md) используется для вычисления остатка от деления.  
  
 Оператор `%=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор %](../../../csharp/language-reference/operators/modulus-operator.md) (см. [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Пример  
 [!code-cs[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)

