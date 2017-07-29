---
title: "Оператор /= (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: 17
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
ms.openlocfilehash: 5e105bf11f5413d77d62be4177ed22ba420312c3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Оператор /= (Справочник по C#)
Оператор присваивания деления.  
  
## <a name="remarks"></a>Примечания  
 Выражение, использующее оператор присваивания `/=`, такое как  
  
```  
x /= y  
```  
  
 эквивалентно  
  
```  
x = x / y  
```  
  
 за исключением того, что `x` вычисляется только один раз. В числовых типах [оператор /](../../../csharp/language-reference/operators/division-operator.md) используется для выполнения операций деления.  
  
 Оператор `/=` нельзя перегрузить напрямую, однако пользовательские типы могут перегрузить [оператор /](../../../csharp/language-reference/operators/division-operator.md) (см. [оператор](../../../csharp/language-reference/keywords/operator.md)). В случае всех составных операторов присваивания перегрузка двоичного оператора неявно перегружает эквивалентное составное назначение.  
  
## <a name="example"></a>Пример  
 [!code-cs[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)

