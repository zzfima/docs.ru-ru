---
title: Оператор != (справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b69d0b12734e690f0ba0209ccbbc7627ff92fe8a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Оператор != (справочник по C#)
Оператор неравенства (`!=`) возвращает значение false, если его операнды равны. В противном случае возвращается значение true. Операторы неравенства предопределены для всех типов, включая строки и объекты. Определяемые пользователем типы могут перегружать оператор `!=`.  
  
## <a name="remarks"></a>Примечания  
 Для предопределенных типов значений оператор неравенства (`!=`) возвращает значение true, если значения его операндов отличаются, и false в любых остальных случаях. Для ссылочных типов (кроме `string`) оператор `!=` возвращает значение true, если два его операнда ссылаются на разные объекты. Для типа `string` оператор `!=` сравнивает значения строк.  
  
 Определяемые пользователем типы значений могут вызвать перегрузку оператора `!=` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)). Это справедливо и для определяемых пользователем ссылочных типов, хотя оператор `!=` по умолчанию действует описанным выше способом и для предопределенных, и для определяемых пользователем ссылочных типов. В случае перегрузки `!=` также необходимо перегружать [==](../../../csharp/language-reference/operators/equality-comparison-operator.md). Операции с целыми типами обычно разрешены и для перечислений.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
