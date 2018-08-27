---
title: Оператор &gt;= (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
ms.openlocfilehash: 8749d1dc0670a5a76bda5ee0d69a4a142671c1e6
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43000289"
---
# <a name="gt-operator-c-reference"></a>Оператор &gt;= (справочник по C#)
Все числовые типы и типы перечисления определяют оператор отношения "больше или равно" (`>=`), который возвращает `true`, если первый операнд больше второго или равен ему. В противном случае возвращается `false`.  
  
## <a name="remarks"></a>Примечания  
 Определяемые пользователем типы могут перегружать оператор `>=`. Дополнительные сведения см. в статье [operator](../../../csharp/language-reference/keywords/operator.md). В случае перегрузки `>=` также необходимо перегружать [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md). Операции с целыми типами обычно разрешены и для перечислений.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
