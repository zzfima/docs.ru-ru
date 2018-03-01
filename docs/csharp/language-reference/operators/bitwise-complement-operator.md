---
title: "Оператор ~ (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a9b0cabcb101fce8422b1390ec8c4cb3b3849631
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Оператор ~ (справочник по C#)
Оператор `~` выполняет операцию поразрядного дополнения операнда, заключающуюся в инвертировании каждого бита. Операторы поразрядного дополнения предопределены для типов [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) и [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
> [!NOTE]
>  Символ `~` также используется для объявления методов завершения. Дополнительные сведения см. в разделе [Методы завершения](../../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
## <a name="remarks"></a>Примечания  
 Определяемые пользователем типы могут перегружать оператор `~`. Дополнительные сведения см. в статье [operator](../../../csharp/language-reference/keywords/operator.md). Операции с целыми типами обычно разрешены и для перечислений.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)  
 [Методы завершения](../../../csharp/programming-guide/classes-and-structs/destructors.md)
