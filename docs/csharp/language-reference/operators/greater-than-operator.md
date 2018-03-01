---
title: "Оператор &gt; (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>_CSharpKeyword'
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fc7c173ecc97bd3ca3b76a92ccbabc0f40062ac7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="gt-operator-c-reference"></a>Оператор &gt; (справочник по C#)
Все числовые типы и типы перечисления определяют оператор отношения "больше" (`>`), который возвращает `true`, если первый операнд больше второго. В противном случае возвращается `false`.  
  
## <a name="remarks"></a>Примечания  
 Определяемые пользователем типы могут вызвать перегрузку оператора `>` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) . В случае перегрузки `>` также необходимо перегружать [<](../../../csharp/language-reference/operators/less-than-operator.md). При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)  
 [explicit](../../../csharp/language-reference/keywords/explicit.md)
