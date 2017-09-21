---
title: "Оператор == (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ==_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
caps.latest.revision: 14
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
ms.openlocfilehash: 0e3ba284bc700e943b108adfec89d14aba41851a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Оператор == (справочник по C#)
Для предопределенных типов значений оператор равенства (`==`) возвращает значение true, если значения его операндов равны, и `false` в любых остальных случаях. Для ссылочных типов (кроме [string](../../../csharp/language-reference/keywords/string.md)) оператор `==` возвращает `true`, если оба его операнда ссылаются на один и тот же объект. Для типа `string` оператор `==` сравнивает значения строк.  
  
## <a name="remarks"></a>Примечания  
 Определяемые пользователем типы значений могут вызвать перегрузку оператора `==` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)). Это справедливо и для определяемых пользователем ссылочных типов, хотя оператор `==` по умолчанию действует описанным выше способом и для предопределенных, и для определяемых пользователем ссылочных типов. В случае перегрузки `==` также необходимо перегружать [!=](../../../csharp/language-reference/operators/not-equal-operator.md). Операции с целыми типами обычно разрешены и для перечислений.  
  
## <a name="example"></a>Пример  
 [!code-cs[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)

