---
title: "Оператор / (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
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
ms.openlocfilehash: 2972261996467f987fa457213b1bcb482d9f1519
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Оператор / (Справочник по C#)
Оператор деления (`/`) делит первый операнд на второй. Все числовые типы имеют предопределенные операторы деления.  
  
## <a name="remarks"></a>Примечания  
 Определяемые пользователем типы могут вызвать перегрузку оператора `/` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) . Перегрузка оператора `/` неявно перегружает [ оператор /= ](division-assignment-operator.md).  
  
 При делении двух целых чисел результат всегда является целочисленным. Например, результат 7 / 3 равняется 2. Чтобы определить остаток от деления 7 / 3, используйте оператор остатка ([%](../../../csharp/language-reference/operators/modulus-operator.md)). Чтобы получить частное в виде рационального числа или дроби, задайте делителю или делимому тип `float` или `double`. Можно назначить тип неявно, если выразить делимое или делитель в десятичном формате, поместив цифру справа от десятичной запятой, как показано в следующем примере.  
  
## <a name="example"></a>Пример  
 [!code-cs[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)

