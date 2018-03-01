---
title: "Оператор / (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9e12e5c472266ea75d3f572a2091bd0784ea5dcf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Оператор / (Справочник по C#)
Оператор деления (`/`) делит первый операнд на второй. Все числовые типы имеют предопределенные операторы деления.  
  
## <a name="remarks"></a>Примечания  
 Определяемые пользователем типы могут вызвать перегрузку оператора `/` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) . Перегрузка оператора `/` неявно перегружает [ оператор /= ](division-assignment-operator.md).  
  
 При делении двух целых чисел результат всегда является целочисленным. Например, результат 7 / 3 равняется 2. Чтобы определить остаток от деления 7 / 3, используйте оператор остатка ([%](../../../csharp/language-reference/operators/modulus-operator.md)). Чтобы получить частное в виде рационального числа или дроби, задайте делителю или делимому тип `float` или `double`. Можно назначить тип неявно, если выразить делимое или делитель в десятичном формате, поместив цифру справа от десятичной запятой, как показано в следующем примере.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
