---
title: "Оператор / (справочник по C#) | Документы Майкрософт"
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 387be8c240001557722b4a30b785637c72c9be37
ms.lasthandoff: 03/13/2017

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

