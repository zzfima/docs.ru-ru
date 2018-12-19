---
title: Оператор &lt;. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
ms.openlocfilehash: 3cc125471eee7bf0002e9844c2a1cdc05e8d4a03
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241240"
---
# <a name="lt-operator-c-reference"></a>Оператор &lt; (справочник по C#)
Все числовые типы и типы перечисления определяют оператор отношения "меньше" (`<`), который возвращает `true`, если первый операнд меньше второго. В противном случае возвращается `false`.  
  
## <a name="remarks"></a>Примечания  
 Определяемые пользователем типы могут вызвать перегрузку оператора `<` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) . В случае перегрузки `<` также необходимо перегружать [>](../../../csharp/language-reference/operators/greater-than-operator.md).
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
