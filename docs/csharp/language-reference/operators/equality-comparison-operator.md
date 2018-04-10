---
title: Оператор == (справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ca22846325968519a1f7625461867c0d83a1a9f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Оператор == (справочник по C#)
Для предопределенных типов значений оператор равенства (`==`) возвращает значение true, если значения его операндов равны, и `false` в любых остальных случаях. Для ссылочных типов (кроме [string](../../../csharp/language-reference/keywords/string.md)) оператор `==` возвращает `true`, если оба его операнда ссылаются на один и тот же объект. Для типа `string` оператор `==` сравнивает значения строк.  
  
## <a name="remarks"></a>Примечания  
 Определяемые пользователем типы значений могут вызвать перегрузку оператора `==` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)). Это справедливо и для определяемых пользователем ссылочных типов, хотя оператор `==` по умолчанию действует описанным выше способом и для предопределенных, и для определяемых пользователем ссылочных типов. В случае перегрузки `==` также необходимо перегружать [!=](../../../csharp/language-reference/operators/not-equal-operator.md). Операции с целыми типами обычно разрешены и для перечислений.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
