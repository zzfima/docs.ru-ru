---
title: Справочник по C#. Оператор ==
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: c6f93be4d422fe42787e36f5b86e2cccbfc645b7
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239018"
---
# <a name="-operator-c-reference"></a>Оператор == (справочник по C#)
Для предопределенных типов значений оператор равенства (`==`) возвращает значение true, если значения его операндов равны, и `false` в любых остальных случаях. Для ссылочных типов (кроме [string](../../../csharp/language-reference/keywords/string.md)) оператор `==` возвращает `true`, если оба его операнда ссылаются на один и тот же объект. Для типа `string` оператор `==` сравнивает значения строк.  
  
## <a name="remarks"></a>Примечания  
 Определяемые пользователем типы значений могут вызвать перегрузку оператора `==` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)). Это справедливо и для определяемых пользователем ссылочных типов, хотя оператор `==` по умолчанию действует описанным выше способом и для предопределенных, и для определяемых пользователем ссылочных типов. В случае перегрузки `==` также необходимо перегружать [!=](../../../csharp/language-reference/operators/not-equal-operator.md). Операции с целыми типами обычно разрешены и для перечислений.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
