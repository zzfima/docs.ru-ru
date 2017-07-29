---
title: "Оператор ~ (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ~_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
caps.latest.revision: 18
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
ms.openlocfilehash: ffbfc379b7c021ccd8fbed9b796aa9fda6618b55
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Оператор ~ (справочник по C#)
Оператор `~` выполняет операцию поразрядного дополнения операнда, заключающуюся в инвертировании каждого бита. Операторы поразрядного дополнения предопределены для типов [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) и [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
> [!NOTE]
>  Символ `~` также используется для объявления методов завершения. Дополнительные сведения см. в разделе [Методы завершения](../../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
## <a name="remarks"></a>Примечания  
 Определяемые пользователем типы могут перегружать оператор `~`. Дополнительные сведения см. в статье [operator](../../../csharp/language-reference/keywords/operator.md). Операции с целыми типами обычно разрешены и для перечислений.  
  
## <a name="example"></a>Пример  
 [!code-cs[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)   
 [Методы завершения](../../../csharp/programming-guide/classes-and-structs/destructors.md)

