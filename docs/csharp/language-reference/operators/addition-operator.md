---
title: "+ Оператор + (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: 19
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
ms.openlocfilehash: 3c6ef1acc69fed1c43f0a249287ca8819c8f091c
ms.lasthandoff: 03/13/2017

---
# <a name="-operator-c-reference"></a>Оператор + (справочник по C#)
Оператор `+` может функционировать как унарный или как бинарный оператор.  
  
## <a name="remarks"></a>Примечания  
 Унарные операторы `+` предварительно определены для всех числовых типов. Результатом использования унарного оператора `+` для числового типа является просто значение операнда.  
  
 Бинарные операторы `+` предварительно определены для числовых и строковых типов. Для числовых типов оператор "+" вычисляет сумму двух его операндов. Если один или оба операнда имеют строковый тип, оператор "+" сцепляет строковые представления операндов.  
  
 Для типов делегатов также используется бинарный оператор `+`, который выполняет сцепление делегатов.  
  
 Пользовательские типы могут перегружать унарный оператор `+` и бинарный оператор `+`. Операции с целыми типами обычно разрешены и для перечислений. Дополнительные сведения см. в разделе [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md).  
  
## <a name="example"></a>Пример  
 [!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)   
 [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md)
